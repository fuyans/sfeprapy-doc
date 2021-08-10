Input parameters
================

The following table summarises the parameters that are required by
``sfeprapy.mcs0`` module.


Non-Optional Miscellaneous Parameters
-------------------------------------

``case_name``: str

	| A name for the case/compartment. Should be unique
	| among all cases. This may be used in post-processing when combining time
	  equivalence results.

``fire_mode``: int

	| Should be an integer from 0 to 4, inclusive. To define what design fires to use:
	| 0 - EC parametric fire only;
	| 1 - Travelling fire only;
	| 2 - EC parametric fire, German Annex;
	| 3 - Option 0 and 1 as above; or
	| 4 - Option 2 and 1 as above.

``n_simulations``: int

	| Should be an integer greater or equal to 1.
	| The number of simulations that will be running. A sensitivity analysis
	  should be carried out to determine the appropriate number of
	  simulations.

``probability_weight``: float

	| Should be a real number between 0 and 1, inclusive.
	| The fire occurrence probability weight of this specific
	  case (i.e. compartment) among all cases (i.e. entire building).
	| This parameter is not used in any calculation. ``sfeprapy.mcs0`` reference
	  this parameter in its output for each single iteration and can be used
	  during post-processing to combine time equivalence curves based on their
	  probability weight to the entire building.

Compartment Parameters
----------------------

``room_breadth``: float 

	| [m]
	| Breadth of room (the shorter dimension).

``room_depth``: float

	| [m]
	| Depth of room (the greater dimension).

``room_height``: float

	| [m]
	| Height of room (floor slab to ceiling slab).

``room_wall_thermal_inertia``: float 

	| [J/m²/K/√s]
	| Compartment lining thermal inertia.

``window_width``: float 

	| [m]
	| Total width of all opening areas for a compartment.

``window_height``: float

	| [m]
	| Weighted height of all opening areas.

``beam_position_vertical`` : float

	| [m]
	| Height of test structure element within the compartment for TFM.
	 This can be altered to assess the influence of height in tall
	 compartments. Need to assess worst case height for columns.

``beam_position_horizontal``: float

	| [m]
	| Minimum beam location relative to compartment length for TFM -
	 Linear distribution.

Windows/Natural Vent
--------------------

``window_open_fraction``: float

	| Dimensionless.
	| Glazing fall-out fraction.

``window_open_fraction_permanent``: float

	| Dimensionless.
	| Use this to force a ratio of open windows. If there is a vent to
	 the outside this can be included here.

Design Fire Parameters
----------------------

``fire_tlim``: float 

	| [hour]
	| Time for maximum gas temperature in case of fuel-controlled fire,
	  value options can be found in Annex A EN 1991-1-2.
	  Slow: 25/60
	  Medium: 20/60
	  Fast: 15/60

``fire_time_step``: float

	| [s]
	| Time step used for the model, all fire time-temperature curves and
	  heat transfer calculation. This is recommended to be less than 30s.

``fire_time_duration``: float 

	| [s]
	| End of simulation. This should be set so that output data is
	  produced allowing the target reliability to be determined. Normally
	  set it to 4 hours and longer period of time for greater room length in
	  order for travelling fire to propagate the entire room.

``fire_load_density``: float

	| [MJ/m²]
	| Fire load density. This should be selected based on occupancy
	  characteristics. See literature for typical values for different
	  occupancies.

``fire_hrr_density``: float

	| [MW/m²]
	| Heat release rate. This should be selected based on the fuel. See
	  literature for typical values for different occupancies.

``fire_spread_speed``: float

	| [m/s]
	| Min spread rate for travelling fire.

``fire_nft_limit``: float

	| [K]
	| TFM near field temperature.

``fire_combustion_efficiency``: float

	| Dimensionless.
	| Combustion efficiency.

``fire_gamma_fi_q``: float

	| Dimensionless.
	| The partial factor for EC fire (German Annex).

``fire_t_alpha``: float

	| [s]
	| The fire growth factor.

Structural Element Section Properties
-------------------------------------

``beam_cross_section_area``: float,

	| [m²]
	| Cross sectional area of the section.

``beam_rho``: float

	| [kg/m³]
	| Density of the structural member.

``beam_temperature_goal``: float

 	| [K]
	| Structural element (steel) failure temperature in Kelvin for goal
	  seek.

``protection_protected_perimeter``: float

	| [m]
	| Heated perimeter.

``beam_protection_thickness``: float

	| [m]
	| Thickness of protection.

``protection_k``: float

	| [W/m/K]
	| Protection conductivity.

``protection_rho``: float


	| [kg/m³]
	| Density of protection to beam.

``protection_c``: float

	| [J/kg/K]
	| Specific heat of protection

Solver Settings (for Time Equivalence)
--------------------------------------

``solver_temperature_goal``: float

	| [K]
	| The temperature to be solved for. This is critical temperature of
	  the beam structural element, i.e. 550 or 620 °C.

``solver_max_iter``: float

	| Dimensionless.
	| The maximum iteration for the solver to find convergence. Suggest
	  20 as most (if not all) cases converge in less than 20 iterations.

``solver_thickness_lbound``: float

	| [m]
	| The smallest value that the protection thickness can be. This is
	  used to solve the maximum steel temperature at
	  ``solver_temperature_goal``.

``solver_thickness_ubound``: float

	| [m]
	| The greatest value that the protection thickness can be. This is
	  used to solve the maximum steel temperature at
	  ``solver_temperature_goal``.

``solver_tol``: float

	| [K]
	| Tolerance of the temperature to be solved for. Set to 1 means
	  convergence will be satisfied when the solved value is greater than
	  ``solver_temperature_goal-1`` and less than
	  ``solver_temperature_goal+1``.

``phi_teq``: float

	| Dimensionless.
	| Model uncertainty factor multiplied with the evaluated
	  characteristic time equivalence value to get the design time
	  equivalence value.

Timber Properties
-----------------

``timber_exposed_area``: float 

	| [m²]
	| Exposed timber surface within the compartment. Set
	  ``timber_exposed_area`` to ‘0’ to omitt timber involvement.

``timber_charring_rate``: float

	| [mm/min]
	| Timber constant charring rate. This is currently independent of
	  temperature or heat flux.

``timber_hc``: float 

	| [MJ/kg]
	| Heat of combustion of timber.

``timber_density``: float

	| [kg/m³]
	| Density of timber.

``timber_solver_ilim``: float

	| Dimensionless.
	| The maximum number of iterations that the solver can run.
	  ``timber_solver_iter`` in the output file should be inspected to
	  determine appropriate value for ``timber_solver_ilim``. Consider to
	  increase ``timber_solver_ilim`` (or increase ``timber_solver_tol``) if
	  many solved values have ``timber_solver_iter`` ==
	  ``timber_solver_ilim``.

``timber_solver_tol``: float

	| [s]
	| Tolerance of the solver. Convergence is sought if change in time
	  equivalence is less than ``timber_solver_tol``.