Application of `SFEPRAPY`
=========================

Introduction
------------

The structural fire resistance of buildings is often determined through the application of guidance documents or defined in prescriptive requirements. Probabilistic risk assessment (PRA) provides an alternative framework within which it is possible to assess the appropriate fire resistance in terms of time-equivalence. Typically, PRA studies require several building specific stochastic parameters as inputs and involve a multitude of calculation iterations to assess an output variable distribution (in an un-biased manner). However, it can be difficult to adopt PRA in design due to limitations with the current available engineering tools. This paper describes a library of a probabilistic functions written in Python that can be used to estimate the distribution of fire severities expected within an enclosure for a given scenario. The application of the Python library is illustrated by an exemplar 18 m tall office building design case, where the required structural fire resistance is computed based upon the (conditional) reliability targets underpinning BS 9999.

The required fire resistance of a given structure is most commonly specified based upon contemporary guidance documents. In the UK, this could be applying BS 9991 or other guidance documents (xxx) depending on the building height, its use, etc. Such guidance provides a simple approach to determining the minimum required structural fire resistance. In BS 9999 the specific ventilation-dependant fire resistance period tables were derived from the time equivalence method, applied in a probabilistic framework based the works by Kirby et al5. However, limitations inherited from the studies underpinning the guidance in BS 9999 are often overlooked. For example, the corresponding background research5 notes that the recommendations for offices are only compatible with compartment sizes of up to 1,000 m² in floor area. In addition, the underlying fire models (i.e. the Eurocode parametric fire) are only readily applicable to fire compartment areas of up to 500 square metres. These limitations mean that building specific analyses are often required to realise the rationalisation opportunities provided by BS 9999 when buildings sit outside the noted limitations.

Probabilistic risk assessment (PRA), as documented in PD 7974-7:2019, provides an alternative framework within which to assess the appropriate fire resistance (e.g. in terms of time-equivalence) for a spectrum of building specific fire scenarios, adopting stochastic variables for key fire development inputs. Such methods have been documented in the literature and employed by others (xxx), and have been adopted on real world engineering projects (xxx). Since PRA can be building specific and apply fundamental methods, the limitations within the prescriptive methods as stated previously can be addressed.

Monte Carlo simulation (MCS) is one method of conducting a PRA. A general MCS procedure is shown in Figure 1. The MCS intake stochastic parameters, each defined as a probability distribution based upon statistics of historical data. Then several (equal to desired number of simulations to run) sets of parameters are randomly generated using the prescribed probability distributions. Finally, a calculation is carried out for each input parameter set. In this work this is the time-equivalence calculation.

Nevertheless, it is challenging to adopt PRA in engineering projects due to limitations in the current available engineering tools. A building specific PRA involves relatively complex calculation procedures and given the available timeframe in the realm of real-world engineering design, conducting a building specific PRA using custom made tools can lead to difficulties for reviewers in the reproduction of results.

Intention
---------

time equivalence probabilistic reliability assessment (TEQPRA or known as PRA to many) is one of the theoretical fundations to structural fire resistance (B3) recommendations in many design guidences in the UK (e.g. Approved Document B [1] and BS 9999 [2]). The fire resistance requirements that are given in the guidence are based on results of a generallised compartment and associated (also generallised) fire model parameters. This generalisation resulted in a simple-to-use fire resistance table which indicates a ‘required fire resistance rating’ for given building height and occupancy characteristics. Inavoidably, the base model that used for the study [3] that underpins the recommendations in the guidence imposes certain design limitations (i.e. building height, compartment size etc) which are not directly obvious to end users.

As such, additional fire engineering assessment is necessary for buildings with higher consequence class (greater than X as defined in [ref X]).

This note is intended to assist one to identify the value/benefit for carrying out a TEQPRA assessment for a specific project or building.

Process overview
----------------

The process to determine whether a TEQPRA assessment is necessary/benefitial brokes into the following three steps:

1. Check if ``additional fire safety engineering provisions`` are required for B3 other than following prescriptive guildence? This is normally defined in the guidence.

   Section 0.3 in BS 9999:2017 noted the following: > “However, the
   increased design demands on structural integrity, services, fire
   safety systems, means of fire-fighting and evacuation generated by
   buildings in excess of 50 m high might mean that specific evaluation
   of all fire safety provisions is needed using a qualitative design
   review in accordance with BS 7974.”

   PD 7974-6 [pd7974-6]

2. Is time equivalence hand calculation method adequate to address the
   above recommendation? A hand calculation method is available in PD
   6688-1-2 [pd6688] (originated from EC 1991-1-2). Similar to the fire
   resistance table, this hand calculation method is derived based on
   analysis of generallised fire and compartment parameters. Therefore,
   limitations detailed in PD 6688 and the parametric fire model should
   be followed.

3. If hand calculation method is not adequate (i.e. given building is
   outside of the limitations) then a detailed time equivalence
   assessment is necesary.

Considerations
--------------

-  1.1 Building height.

   -  is the building greater than 50 m? BS 9999, ADB and other
      guidances that share similar theoretical basis are not designed
      for high rise buildings over 50 m. These buildings will need to be
      engineered to make sure fire safety is appropriately applied. In
      this instance, PRA TEQ takes care of B3 to ensure appropriate
      level of structural stabi
