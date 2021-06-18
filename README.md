ECAL Local reconstruction in CMSSW for Phase 2
====

Where:

    /afs/cern.ch/user/a/amassiro/work/ECAL/Phase2/CMSSW_11_2_0/src
    
    /home/amassiro/Cern/Code/UniMiB/ECALLocalRecoPhase2
    
    
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
    

    
Details
====

    git-cms-addpkg  Configuration/PyReleaseValidation/
    git-cms-addpkg  SimCalorimetry/EcalSimProducers/

    
From Stefano's instructions

    cp /afs/cern.ch/user/a/argiro/public/ph2Reco/EcalLiteDTUPedestalsESProducer.cc SimCalorimetry/EcalSimProducers/    

    scramv1 b -j 20
    

Test
====
    
    runTheMatrix.py -w upgrade -l 28234.61
    
    cd 28234.61_TTbar_14TeV+2026D60_ecalDevel+TTbar_14TeV_TuneCP5_GenSimHLBeamSpot14+DigiTrigger+RecoGlobal+HARVESTGlobal/
    
    cmsRun TTbar_14TeV_TuneCP5_cfi_GEN_SIM.py

-> in step2_DIGI.py add 

        process.GlobalTag.toGet = cms.VPSet(
          cms.PSet(record = cms.string("EcalSimPulseShapeRcd"),
            tag = cms.string("EcalSimPulseShapePhaseII"),
            connect = cms.string("frontier://FrontierProd/CMS_CONDITIONS")
          )
        )

        
    cmsRun step2_DIGI.py
    
    cmsRun step3_RAW2DIGI_L1Reco_RECO_RECOSIM_PAT_VALIDATION_DQM.py
    
    
    
    
Reconstruction step
====

    git-cms-addpkg  RecoLocalCalo/EcalRecProducers
    git-cms-addpkg  RecoLocalCalo/EcalRecAlgos
    


    
Try simple max-amplitude algorithm.
Then move to weights based reconstruction.

 
    
    
    
    
    





    