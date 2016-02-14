# Mr-WW
Mass Regression WW

Setup:

    . /afs/cern.ch/sw/lcg/external/gcc/4.9/x86_64-slc6-gcc49-opt/setup.sh
    . /afs/cern.ch/sw/lcg/app/releases/ROOT/6.04.10/x86_64-slc6-gcc49-opt/root/bin/thisroot.sh

How:

    r99t TrainRegression.cxx\(\"BDT\"\)

    r99t TMVAGui.C\(\"TMVAReg.root\"\)

    
Input:

    /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_GluGluHToWWTo2L2Nu_M650.root

    hadd /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_MassSoup.root  /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_GluGluHToWWTo2L2Nu_M400.root      /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_GluGluHToWWTo2L2Nu_M500.root   /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_GluGluHToWWTo2L2Nu_M650.root 

    target: higgsLHEmass


Apply:

     gardener.py  mrWWvarfiller \
                /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_MassSoup.root  \
                /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_MassSoup_filled.root

Test:

    r99t /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_MassSoup_filled.root
    latino->Draw("mrww1:higgsLHEmass")
    
    
Where:

    /afs/cern.ch/user/a/amassiro/Framework/Mr-WW
