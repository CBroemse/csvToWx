# csvToWx
###### Content: 
######      1.'writePatternfile_____2.'aMemoryRAW'________3.'aMemoryRAW'_______4.'aOsZilloskop1RAW'
   ######      modes of Files: 1- WX 2- TXT
Setup: Three modi  
- 1. A GHC GUI
- 2. Automatic (the same as above avoiding GUI's UNDERCONSTRUCTION )
- 3. Easy Acces (quickly read a csv file and process...)

i. will open a simpel Graphical User Interface (GUI) in the Glasgow Haskell Compiler (GHC)
   the aim is to automate reading of csv data and of long number streams 
   converting them and changing them via predefined functions. The whole program
   is derived from four main functions.
   
ii. Runs all functions as i. but avoiding the GUI...(realisation under construction 23-09-19)
    of 4 main functions some can be completly controlled just via Global-Variables*.
    which are ...aMemoryRAW  !! so far

iii. Quick and easy access to read csv -> write patternfile.txt
##### Main
- 1. A GHC GUI
enter> main
  ![alt tag](https://github.com/CBroemse/cvsToWx/blob/master/Manual1.png)
  
    The advantage of using Global Variables, the stream-crypt program can be fully automated which helps
    overseing bigger longer files and keeping an eye on the real aim of the Wx-Maxima application.
    
    The disadvantage of using Global Variables is that we can lose track of which functions we just
    applied to our data, getting no visiual feedback, both sides can be avoided be directly calling
    the "PatternfileRAW' functions that need more variables but can be easily be called via your own batch/bat
    files or any other program. 

##### Four functions to use   
The whole stream-crypt revolves around four functions that do the 'dirty' work. 
The easiest and almost laziest way is by utiliesing commandline and directly typ in
the function plus variabes.
   #### 1. 'writePatternfile' 
   via 'Patternfile.hs' read a csv file from disc and export it as aPatternfile.txt
   e.g enter: 'writePatternfile x nF'
   
   ###### x="fileTorRead.csv" ; nF = "fileToWrite.txt"
       writePatternfile x nF => format [val,year,month,day]
   fire up your Editor and jump to line :858
   below the mentioned code and the GHC GUI are pictured to compare
   Enable 'writePatternfile' to read other csv formats!
   ![alt tag](https://github.com/CBroemse/cvsToWx/blob/master/Manual2.png)

  #### 2. 'aMemoryRAW'  
  writes screen1.txt statistical data about the data set
          autoInputII:String; e.g "1" if ==1 -> hide output ?!
        => opens menu: Options : POINTCLOUD 1..4,6: Pointcloud
                             CLOSE 5
                              
        => maybe writes: "lala.wxm" filled with  1 or 2 ..or 4 or 6
                 content: if 1 or 2 or 3 or 4 or 6 == True -> do P.aMemoryRAW autoInputII file22writ file33writ
                 with: autoInputII = "1"; file22writ; file33writ;
                          else do P.aMemoryRAW "2" file22writ file33writ
                          
        => writes: "screenI.txt" --a crude statistical overview of the set 
        => proceed: start a second Computation from the same source
        => reads: fileToread.txt (same as step above)
        => order: applies predefiend function to the value 
        =>        [MQ3,MQ4,MQ5,MQ6] -- group of sin functions (periodic)
        => do Wx.WriteMQScreenI && Wx.WriteMQ6ScreenII
        => load: if  then 'WriteWXmaximafile.hs* -> do writeMQ6SCREENI
                 else 'WriteWXmaximafile.hs* -> do writeMQ6SCREENII
  select any String you to import as as line into Wx-Maxima, 'aMemory' will convert it
  to WX.maxima format. Set to a random pointcloud while a myriad other settings are out there.
  
  ![alt tag](https://github.com/CBroemse/cvsToWx/blob/master/Manual3.png)  
  
        => function: aMemoryRAW outputOrnot fileToread fileTowrite 
                             String       String    String
        => :*Patternfile>aMemoryRAW "1" "seniot.txt" "seniot7.txt"             
   
  #### 3. 'aOsZilloskop1RAW'
  will prepare real vals and simu vals, apply a set of fourier6-set-functions* to
  it. will exportDATA.txt in first run (simu vals for reimport)
  exportDATA2.txt cleaned just vals [String]
  
    => writes: exportDatat1,exportData2,HTML
    => function: aOsZilosko1 outputOrnot fileToread   fileTowrite   howMAny   crit   foHans   fun1 fun2
    => types:  String     String         String  String  String   Int  Int
    => *Patternfile>aMemoryRAW "1" "seniot.txt" "seniot7.txt"
  #### 4.'aCrunchlist1RAW'
  UNDERDEVELOPMENT
  most basic HTA/HTML plotter can be easily changed from hta to html by 
  just typing differet format afile.hta <=> afile.html, 
  u,
  Hello Microsoft ;), the hta runs 
  Haskell generated VB.script that cannot be displayed in (firefox,..)
  
  writes senio, writes Html, using global variables   
       => writes: TESTGuiVal.hta 
  



Patternfile.hs
'writePatternFile "fileToRead.csv" "fileToWrite.txt"'
 Reads a CSV file e.g: "durble.csv"
 Writes a a file with line format (val,year,month,day) a file called 'Patternfile.txt'

'aMemory '
Reads 'Patternfile.txt'
Turns it into a String will plot some statistic about the given DATA Set.

Write a WX.Maxima file

## Nexus: Armchair-hillosohy ,what ia good about the code
   ### The stuff is without any blows ad witshles, like 'sohisticated Hasekell'
   One of the most remarkable sentences abt. Haskell ,to me, that I heard is that to keep it 
   rather simple more functional with less fancy code that will blow number theorisists minds
   but not be easy for simple prgram tasks, such as the aim without much prior knowledge.




