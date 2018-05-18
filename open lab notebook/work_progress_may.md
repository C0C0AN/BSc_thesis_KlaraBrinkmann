# 07.05. 2018 - 11.05.2018
## Monday
- free

## Tuesday
- lab meeting
- translated the questionnaire into english again (corrected some things)
- checked questionnaires and put them into json files
- to do: discuss with Mirjam and Marie about Music Feature Extraction --> come to a conclusion!!

## Wednesday
- to do: discuss with Mirjam, Michael and Marie about the analysis of the questionnaire
conclusions: we were not sure if we want to calculate the absolute frequency or do some weighted frequencies
therefore, we wanted to talk to Herr Lemmer about that problem
- searched for new people who completed our questionnaire
--> wrote the output of those people into a json file
--> documented the name of the json file in a spreadsheet
- began to convert the json file in a csv file 
- did some corrections on the function for converting json files into csv files
--> created a sheet for errors: where the error of one subject is precisely defined as "XY is missing" or "XY is not complete"
this is done by a 'if, else command'

## Thursday
- reading of "A multi level tonal interval space for modelling pitch relatedness and musical consonance" by Gilberto Bernardes, Diogo Cocharro, Marcelo Caetano, Carlos Guedes & Matthew E.P. Davies (2016)

## Friday
- talked to Herr Lemmer about the analysis of the questionnaire: documented solutions in a file and sent it to group
- searched for new people who completed our questionnaire
--> wrote them into json files
- did some corrections on the function for converting json files into csv files because there was always the error "missing values for chills often" for every subject
--> 'auschließlich' to 'ausschliesslich'
- wrote the for loop so that the loop will go through every file in my order where the json files are and convert them into csv files
- to do: Essentia --> audio analysis
        look at Michaels proposals for analysing questionnaire

## Saturday
- checked the error files for missing values and wrote that into the spreadsheet
- marked "no missing values" and "missing value for active music cur dur" as green
- marked columns as yellow when there was more missing than stated above
- marked columns red when "sortables" were missing

## Sunday
- reading "The capacity of music: What is it? And what is special about it?" by Lerdahl and Jackendorff in 2006

# 14.05. - 18.05.2018

## Monday
- analyzed all csv files with Michael's Script for the full dataset 
- plotted the results in a presentation on Google Drive

## Tuesday
- lab meeting
- worked on music feature extraction in Bregman
--> got the error: couldn't find wavread
- read the introduction part of "Python for everybody"

## Wednesday
- discussion with Mirjam and Marie about Music Feature Extraction
- showed Essentia Tutorials to them
- explained them that we can also use scikitlearn to estimate distances
- Mirjam showed Pliers: advantage: it is easier to use than Essentia    disadvantage: has only 1 rhythm extractor
- overall discussion with Peer: Pliers is using Librosa
- found out that Librosa has more than one rhythm extractor
- decided to use Librosa and decided which features we want to extract with Librosa
- to do: for paper: report of the results and methods of the questionnaire
- Feature Extraction of all 200 music stimuli with Essentia and Librosa
- for thesis: Feature Extraction of 20 most representative stimuli with Librosa
- general: find out which hop size & frame size & window type to chose for spectral & temporal features
- keep in mind that spectral features have less time bins and temporal features should have more time bins
- DONE: reading about window size and hop size 

## Thursday
- reading about window size and hop size

## Friday
- tried to solve the script problem for our analysis of our validation survey
--> couldn't find a resolution until now
- read "Audio properties of perceived boundaries in music"
