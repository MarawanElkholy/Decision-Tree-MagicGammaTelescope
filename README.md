# Decision-Tree-MagicGammaTelescope

1. Title of Database: MAGIC gamma telescope data 2004

2. Sources:

   (a) Original owner of the database:

       R. K. Bock
       Major Atmospheric Gamma Imaging Cherenkov Telescope project (MAGIC)
       http://wwwmagic.mppmu.mpg.de
       rkb@mail.cern.ch

   (b) Donor:

       P. Savicky
       Institute of Computer Science, AS of CR
       Czech Republic
       savicky@cs.cas.cz

   (c) Date received: May 2007

3. Past Usage:

   (a) Bock, R.K., Chilingarian, A., Gaug, M., Hakl, F., Hengstebeck, T.,
       Jirina, M., Klaschka, J., Kotrc, E., Savicky, P., Towers, S.,
       Vaicilius, A., Wittek W. (2004).
       Methods for multidimensional event classification: a case study
       using images from a Cherenkov gamma-ray telescope.
       Nucl.Instr.Meth. A, 516, pp. 511-528.

   (b) P. Savicky, E. Kotrc.
       Experimental Study of Leaf Confidences for Random Forest.
       Proceedings of COMPSTAT 2004, In: Computational Statistics.
       (Ed.: Antoch J.) - Heidelberg, Physica Verlag 2004, pp. 1767-1774.

   (c) J. Dvorak, P. Savicky.
       Softening Splits in Decision Trees Using Simulated Annealing.
       Proceedings of ICANNGA 2007, Warsaw, (Ed.: Beliczynski et. al),
       Part I, LNCS 4431, pp. 721-729.

4. Relevant Information:

   The data are MC generated (see below) to simulate registration of high energy
   gamma particles in a ground-based atmospheric Cherenkov gamma telescope using the
   imaging technique. Cherenkov gamma telescope observes high energy gamma rays,
   taking advantage of the radiation emitted by charged particles produced
   inside the electromagnetic showers initiated by the gammas, and developing in the
   atmosphere. This Cherenkov radiation (of visible to UV wavelengths) leaks
   through the atmosphere and gets recorded in the detector, allowing reconstruction
   of the shower parameters. The available information consists of pulses left by
   the incoming Cherenkov photons on the photomultiplier tubes, arranged in a
   plane, the camera. Depending on the energy of the primary gamma, a total of
   few hundreds to some 10000 Cherenkov photons get collected, in patterns
   (called the shower image), allowing to discriminate statistically those
   caused by primary gammas (signal) from the images of hadronic showers
   initiated by cosmic rays in the upper atmosphere (background).

   Typically, the image of a shower after some pre-processing is an elongated
   cluster. Its long axis is oriented towards the camera center if the shower axis
   is parallel to the telescope's optical axis, i.e. if the telescope axis is
   directed towards a point source. A principal component analysis is performed
   in the camera plane, which results in a correlation axis and defines an ellipse.
   If the depositions were distributed as a bivariate Gaussian, this would be
   an equidensity ellipse. The characteristic parameters of this ellipse
   (often called Hillas parameters) are among the image parameters that can be
   used for discrimination. The energy depositions are typically asymmetric
   along the major axis, and this asymmetry can also be used in discrimination.
   There are, in addition, further discriminating characteristics, like the
   extent of the cluster in the image plane, or the total sum of depositions.

   The data set was generated by a Monte Carlo program, Corsika, described in 
      D. Heck et al., CORSIKA, A Monte Carlo code to simulate extensive air showers,
      Forschungszentrum Karlsruhe FZKA 6019 (1998).
   The program was run with parameters allowing to observe events with energies down
   to below 50 GeV.

5. Number of Instances: 19020

6. Number of Attributes: 11 (including the class)

7. Attribute information:

    1.  fLength:  continuous  # major axis of ellipse [mm]
    2.  fWidth:   continuous  # minor axis of ellipse [mm] 
    3.  fSize:    continuous  # 10-log of sum of content of all pixels [in #phot]
    4.  fConc:    continuous  # ratio of sum of two highest pixels over fSize  [ratio]
    5.  fConc1:   continuous  # ratio of highest pixel over fSize  [ratio]
    6.  fAsym:    continuous  # distance from highest pixel to center, projected onto major axis [mm]
    7.  fM3Long:  continuous  # 3rd root of third moment along major axis  [mm] 
    8.  fM3Trans: continuous  # 3rd root of third moment along minor axis  [mm]
    9.  fAlpha:   continuous  # angle of major axis with vector to origin [deg]
   10.  fDist:    continuous  # distance from origin to center of ellipse [mm]
   11.  class:    g,h         # gamma (signal), hadron (background)

8. Missing Attribute Values: None

9. Class Distribution:

   g = gamma (signal):     12332
   h = hadron (background): 6688

   For technical reasons, the number of h events is underestimated.
   In the real data, the h class represents the majority of the events.

   The simple classification accuracy is not meaningful for this data, since
   classifying a background event as signal is worse than classifying a signal
   event as background. For comparison of different classifiers an ROC curve
   has to be used. The relevant points on this curve are those, where the
   probability of accepting a background event as signal is below one of the
   following thresholds: 0.01, 0.02, 0.05, 0.1, 0.2 depending on the required
   quality of the sample of the accepted events for different experiments.


