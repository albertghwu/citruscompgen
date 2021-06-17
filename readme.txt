wrapper scripts for demographic inference using the python package moments

dependency:  
   moments.1.0.3,  a python package for demographic inference based on diffusion approximations to the allele frequency spectrum. 

instructions for installing moments are available at:
   https://bitbucket.org/simongravel/moments/src/master/



1) wrapper script for one-population size history inference with a 2-epoch model
 script name: moments_infer_1pop_pub.py 
 also included is an example usage:
    ./moments_infer_1pop_pub.py  folded.AFS -Bbounds.txt -i50 -oout.2epo
    where the input file folded.AFS contains the folded allele frequency spectrum,
          the input file bounds.txt contains the uppper bounds, lower bounds, initial values of the model parameters, 
               as well as maxium fold of perturbation around the initial values
          -i50: maximum number of 50 iteration in moments' optimization step
          -oout.2epo: out.2epo contains the results including the log-likelihood and parameter values
    Running time: each simulation takes a few seconds on a linux machine

2) wrapper script for four-population divergence inference
  script name: moments_infer_4pop_pub.py
  also included is an example usage:
    ./moments_infer_4pop_pub.py MPRS_4pop.folded -i40 -Bbounds_4pop.txt  -oout.4pop
    where the input file MPRS_4pop.folded contains the joint 4-population folded allele frequency spectrum
          the input file bounds_4pop.txt contains the uppper bounds, lower bounds, initial values of the model parameters, 
               as well as maxium fold of perturbation around the initial values
          -i40: maximum number of 40 iteration in moments' optimization step
          -oout.4pop: out.4pop contains the results including the log-likelihood and parameter values
    Running time: each simulation takes 3-5 minutes on a linux machine

