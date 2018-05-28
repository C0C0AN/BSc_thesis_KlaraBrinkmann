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

## Saturday
- continue reading on "Audio properties of perceived boundaries in music"

## Sunday
- continue reading on "Audio properties of perceived boundaries in music"

# 21.05.2018 - 27.05.2018

## Monday
- read about Euclidean distance and Mahalanobis distance

## Tuesday
- lab meeting
- validation survey: collected the last participants together; wrote them into json file; wrote them into csv files; concatenated csv files; created full dataset and posted it on slack (33 participants)
- pycharm: tried to do genre_weights_sum with the validation survey data but it didn't work out because the python interpreter was wrong; changed python interpreter to 3.6; pycharm still works with old script? Error running 'genre_weights_sum': Cannot run program "/tmp/genre_weights_final.py/venv/bin/python" (in directory "/home/klara/Dokumente/7/Bachelorarbeit/Fragebogen"): error=2, Datei oder Verzeichnis nicht gefunden --> solved that problem: deleted venv folder and set the python interpreter 3.6 in the folder where the genre_weights_sum is

## Wednesday
- calculated Chroma_cqt in Pliers for music stimuli of my study
- read again about Mahalanobis distance: measures distance in relation to a centroid (point in a multidimensional space where all variable means cut themselves; the larger the MD the further away is the data point from the centroid)
- tried to estimate distance bettween two examples
- tried the experiment in matlab: baroque 2 and renaissance 1 are the same stimuli; two objects will move at the same time when clicking on them after one another; there should be an instruction for the participant that listening to the stimuli requires a click on right mouse side and quit listening requires a press on space bar and moving the item requires a click on the left mouse side

## Thursday
- talked with Mirjam about stimuli in Renaissance: decided to take the second representative which is renaissance4
- did the multi arrangement experiment in Matlab and completed it

## Friday
- tried to compute tempogram of my stimuli with librosa (used the example on this page for that: https://librosa.github.io/librosa/generated/librosa.feature.tempogram.html#librosa.feature.tempogram

- what works:
- uploading the audio file and defining it's hop length
- compute the onset strength
- compute the tempogram
- compute the tempo

- Problems:
- it is possible to compute the global autocorrelation but it is not possible to display it in a graph
- the error for that is:
- ValueError: x and y must have same first dimension, but have shapes (384,) and (259,) in line 18: plt.plot(x, ac_global, '--', alpha=0.75, label='Global autocorrelation')
- I am not sure what the global autocorrelation measures (correlation of the signal with a delayed copy of itself over time in a spatial space?
to find repeated patterns? means if the rhythm is repeating and when it is repeating?)

## Sunday
- read 'onsets, tempo and beats' in http://conference.scipy.org/proceedings/scipy2015/pdfs/brian_mcfee.pdf to understand how I can compute rhythm features in librosa
- read https://domino.mpi-inf.mpg.de/intranet/ag4/ag4publ.nsf/0/94779f9f00f541a7c12577540055b43d/$FILE/2010_GroscheMuellerKurth_TempogramCyclic_ICASSP.pdf to understand the cyclic tempogram of librosa/pliers
- read 

# 28.05.2018 - 01.06.2018

## Monday
- extracted tempo and beat in librosa for one example (alternative)
- find this easier to understand than the tempogram, moreover there are no errors while computing it
- what is the advantage of a tempogram? what is the advantage of having an autocorrelation?


