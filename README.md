ECAL Local reconstruction in CMSSW for Phase 2
====

Instructions to install CMSSW, prepare code, make PRs, ...


Install, after logging to lxplus

    cmsrel  CMSSW_11_2_0

cmsrel installs cmssw, and the needed links, but it does not actually downloads packages. 
they will be needed to be downloaded later on.

    cd CMSSW_11_2_0/src/
    
Code goes to "src" folder.

    cmsenv
    
cmsenv allows you to compile and run code in *this* selected cmssw release

    git-cms-addpkg  Configuration/PyReleaseValidation/

git-cms-addpkg downloads in local that package.
Then you can modify that package and compile

To compile, always go to the main "src" folder and run

    scramv1 b -j 20
    

    
    