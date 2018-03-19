# Mr-WW
Mass Regression WW for VBS

Setup:

    . /afs/cern.ch/sw/lcg/external/gcc/4.9/x86_64-slc6-gcc49-opt/setup.sh
    . /afs/cern.ch/sw/lcg/app/releases/ROOT/6.04.10/x86_64-slc6-gcc49-opt/root/bin/thisroot.sh

    
Add gen variables:

    /eos/cms/store/group/phys_higgs/cmshww/amassiro/Full2016_Apr17/Apr2017_summer16/lepSel__MCWeights__bSFLpTEffMulti__cleanTauMC__l2loose__hadd__l2tightOR__LepTrgFix__formulasMC/latino_WpWmJJ_EWK.root
    
    cd ../../CMSSW_8_0_26_patch1/src/
    cmsenv
    cd -
    
    gardener.py  genvariablesfiller  /eos/cms/store/group/phys_higgs/cmshww/amassiro/Full2016_Apr17/Apr2017_summer16/lepSel__MCWeights__bSFLpTEffMulti__cleanTauMC__l2loose__hadd__l2tightOR__LepTrgFix__formulasMC/latino_WpWmJJ_EWK.root   /tmp/amassiro/latino_WpWmJJ_EWK.root    
    
    latino->Draw("lhe_mlvlv")
    
    
How:

    r99t TrainRegression.cxx\(\"BDT\"\)
    r99t TrainRegression.cxx\(\"MLP\"\)

    r99t TMVAGui.C\(\"TMVAReg.root\"\)

    

    
Where:

    /afs/cern.ch/user/a/amassiro/work/Latinos/Framework/Mr-WW/VBS

    


    
    