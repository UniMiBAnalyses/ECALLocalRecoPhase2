To commit
====

Create a branch in:

    https://github.com/UniMiBAnalyses/cmssw

    
    cd /afs/cern.ch/user/a/amassiro/work/ECAL/Phase2/ToCommit
    cmsrel  CMSSW_11_2_0
    cd CMSSW_11_2_0/src/
    cmsenv
    git cms-init
    
    
    
    git remote add origin git@github.com:UniMiBAnalyses/cmssw

    git fetch origin

    git checkout -b  BiancaPinolini-ecal-reco-phase2-commit-unimib
       
    git-cms-addpkg  RecoLocalCalo/EcalRecProducers
    git-cms-addpkg  RecoLocalCalo/EcalRecAlgos

    
Now write code or copy code from another folder if it was devleoped somewhere else.
Test the code, both in compilation and in execution (cmsRun).
Then:
    
    git add ...
    
    git commit ...
    
    git push -u origin  BiancaPinolini-ecal-reco-phase2-commit-unimib


To see via web:

    https://github.com/UniMiBAnalyses/cmssw/tree/BiancaPinolini-ecal-reco-phase2-commit-unimib

Then make PR, into CMSSW_11_2_X :

    https://github.com/UniMiBAnalyses/cmssw/compare/CMSSW_11_2_X...UniMiBAnalyses:BiancaPinolini-ecal-reco-phase2-commit-unimib?expand=1
    
Then make PR, into CMSSW_11_2_X in official cmssw (from a recent night built release):


    cd /afs/cern.ch/user/a/amassiro/work/ECAL/Phase2/ToCommit
    cmsrel CMSSW_12_0_X_2021-07-13-2300
    cd CMSSW_12_0_X_2021-07-13-2300/src/
    cmsenv
    git cms-init
    
    git remote add origin git@github.com:UniMiBAnalyses/cmssw

    git fetch origin

    git checkout -b  BiancaPinolini-Ecal-reco-phase2-12_0
       
    git-cms-addpkg  RecoLocalCalo/EcalRecProducers
    git-cms-addpkg  RecoLocalCalo/EcalRecAlgos
    

    // make changes, add, commit and push

    git add ...
    
    git commit ...
    
    git push -u origin  BiancaPinolini-Ecal-reco-phase2-12_0

    
    // then ...    
    
    https://github.com/cms-sw/cmssw/compare/master...UniMiBAnalyses:BiancaPinolini-Ecal-reco-phase2?expand=1
    