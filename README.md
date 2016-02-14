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

    hadd /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_MassSoup.root \
       /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_GluGluHToWWTo2L2Nu_M400.root    \
       /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_GluGluHToWWTo2L2Nu_M500.root  \
       /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_GluGluHToWWTo2L2Nu_M650.root 

    target: higgsLHEmass

    
Make input flat:

    TH1F h("h","",50,300,1000);
    latino->Draw("higgsLHEmass >> h");
    for (int i=0; i<h.GetNbinsX(); i++) std::cout << " (higgsLHEmass <  " <<  h.GetBinCenter(i+1)+7 << " && higgsLHEmass >= " << h.GetBinCenter(i+1)-7 << ") * (1./" << h.GetBinContent(i+1) << " ) + ";
    
    + remember to set by hand the overflow and underflow
    
    
    
    gardener.py adder \
      -v 'weightMHflat/F= (higgsLHEmass <  300 ) * (1./22) +     (higgsLHEmass >  1000 ) * (1./18 ) +       (higgsLHEmass <  314 && higgsLHEmass >= 300) * (1./22 ) +  (higgsLHEmass <  328 && higgsLHEmass >= 314) * (1./29 ) +  (higgsLHEmass <  342 && higgsLHEmass >= 328) * (1./51 ) +  (higgsLHEmass <  356 && higgsLHEmass >= 342) * (1./115 ) +  (higgsLHEmass <  370 && higgsLHEmass >= 356) * (1./235 ) +  (higgsLHEmass <  384 && higgsLHEmass >= 370) * (1./670 ) +  (higgsLHEmass <  398 && higgsLHEmass >= 384) * (1./1952 ) +  (higgsLHEmass <  412 && higgsLHEmass >= 398) * (1./2644 ) +  (higgsLHEmass <  426 && higgsLHEmass >= 412) * (1./1228 ) +  (higgsLHEmass <  440 && higgsLHEmass >= 426) * (1./615 ) +  (higgsLHEmass <  454 && higgsLHEmass >= 440) * (1./362 ) +  (higgsLHEmass <  468 && higgsLHEmass >= 454) * (1./228 ) +  (higgsLHEmass <  482 && higgsLHEmass >= 468) * (1./215 ) +  (higgsLHEmass <  496 && higgsLHEmass >= 482) * (1./193 ) +  (higgsLHEmass <  510 && higgsLHEmass >= 496) * (1./202 ) +  (higgsLHEmass <  524 && higgsLHEmass >= 510) * (1./199 ) +  (higgsLHEmass <  538 && higgsLHEmass >= 524) * (1./213 ) +  (higgsLHEmass <  552 && higgsLHEmass >= 538) * (1./209 ) +  (higgsLHEmass <  566 && higgsLHEmass >= 552) * (1./280 ) +  (higgsLHEmass <  580 && higgsLHEmass >= 566) * (1./373 ) +  (higgsLHEmass <  594 && higgsLHEmass >= 580) * (1./356 ) +  (higgsLHEmass <  608 && higgsLHEmass >= 594) * (1./437 ) +  (higgsLHEmass <  622 && higgsLHEmass >= 608) * (1./559 ) +  (higgsLHEmass <  636 && higgsLHEmass >= 622) * (1./616 ) +  (higgsLHEmass <  650 && higgsLHEmass >= 636) * (1./684 ) +  (higgsLHEmass <  664 && higgsLHEmass >= 650) * (1./686 ) +  (higgsLHEmass <  678 && higgsLHEmass >= 664) * (1./634 ) +  (higgsLHEmass <  692 && higgsLHEmass >= 678) * (1./543 ) +  (higgsLHEmass <  706 && higgsLHEmass >= 692) * (1./456 ) +  (higgsLHEmass <  720 && higgsLHEmass >= 706) * (1./374 ) +  (higgsLHEmass <  734 && higgsLHEmass >= 720) * (1./293 ) +  (higgsLHEmass <  748 && higgsLHEmass >= 734) * (1./227 ) +  (higgsLHEmass <  762 && higgsLHEmass >= 748) * (1./163 ) +  (higgsLHEmass <  776 && higgsLHEmass >= 762) * (1./136 ) +  (higgsLHEmass <  790 && higgsLHEmass >= 776) * (1./111 ) +  (higgsLHEmass <  804 && higgsLHEmass >= 790) * (1./77 ) +  (higgsLHEmass <  818 && higgsLHEmass >= 804) * (1./79 ) +  (higgsLHEmass <  832 && higgsLHEmass >= 818) * (1./77 ) +  (higgsLHEmass <  846 && higgsLHEmass >= 832) * (1./63 ) +  (higgsLHEmass <  860 && higgsLHEmass >= 846) * (1./46 ) +  (higgsLHEmass <  874 && higgsLHEmass >= 860) * (1./31 ) +  (higgsLHEmass <  888 && higgsLHEmass >= 874) * (1./42 ) +  (higgsLHEmass <  902 && higgsLHEmass >= 888) * (1./25 ) +  (higgsLHEmass <  916 && higgsLHEmass >= 902) * (1./31 ) +  (higgsLHEmass <  930 && higgsLHEmass >= 916) * (1./24 ) +  (higgsLHEmass <  944 && higgsLHEmass >= 930) * (1./19 ) +  (higgsLHEmass <  958 && higgsLHEmass >= 944) * (1./10 ) +  (higgsLHEmass <  972 && higgsLHEmass >= 958) * (1./10 ) +  (higgsLHEmass <  986 && higgsLHEmass >= 972) * (1./12 ) +  (higgsLHEmass <  1000 && higgsLHEmass >= 986) * (1./18 ) ' \
    /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_MassSoup.root \
    /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_MassSoup_flat.root 
    
    

Apply:

     cp /afs/cern.ch/user/a/amassiro/Framework/Mr-WW/weightsMassVariable0Jet/TMVARegression_BDT.weights.xml Gardener/python/data/mrww/
     
     gardener.py  mrWWvarfiller \
                /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_MassSoup.root  \
                /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_MassSoup_filled.root

     gardener.py  mrWWvarfiller \
                /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_MassSoup_flat.root  \
                /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_MassSoup_filled.root

Test:

    r99t /media/data/amassiro/LatinoTrees/MrWW/MCl2loose__hadd__l2tight/latino_MassSoup_filled.root
    latino->Draw("mrww1:higgsLHEmass")
    latino->Draw("mrww1:higgsLHEmass","weightMHflat")
    latino->Draw("mrww1*mll:higgsLHEmass","weightMHflat")
    latino->Draw("mrww1*mll:higgsLHEmass","weightMHflat","colz")
    latino->Draw("mrww1:higgsLHEmass","weightMHflat","colz")
    
    
Where:

    /afs/cern.ch/user/a/amassiro/Framework/Mr-WW
