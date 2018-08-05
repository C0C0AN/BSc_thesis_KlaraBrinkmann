# 02.07. - 06.07.2018

## Monday
- continued with introduction (pitch and pitch perception)
- checked the experiment on Mac for testing on Tuesday: everything is working
- sent new e-mail to subject distributor

## Tuesday
- office meeting
- recruited 3 persons
- found paper of Kohlrausch et al. for introduction "Perceptual evaluation of music similarity"

## Wednesday
- recruited 2 persons
- worked on introduction
- read paper of Kohlrausch et al. in depth

## Thursday
- recruited one person, one person cancelled appointment and asked for an appointment next week
- worked on introduction
- wrote points of Kohlrausch Paper down

## Friday
- recruited one person, one person cancelled appointment and asked for an appointment next week
- worked on introduction
- read Experiment 1 and 2 of "An Empirically Derived Measure of Melodic Similarity" by Russo et al. 

# 09.07. - 13.07.2018

## Monday
- Peer explained the overall procedure in analysis of the behavioral data
- Marie created a google docs sheet for that
- converted files in matlab from 1x190 vectors into 20x20 matrices by the command 'behav_RDM_square=squareRDM(estimate_dissimMat_ltv)'
- created a structure for all files in matlab with columns 'RDM', 'name' and 'musician'
- computed average for musicians and non-musicians in Matlab (Matlab needs specific naming for 'nme' column
in name column there has to be 'subject' 
- average function is named 'averageRDMs_subjectSession.m'
TO DO: concatenate RDMs, create MDS of RDMs, create models of music features

## Tuesday
- recruited 2 subjects
- created conceptual models with Marie (allequal-model, allunequal-model, randomization-model, maingenre-model)

## Wednesday
- recruited 2 subjects

## Thursday
- converted matfiles into csv files
- created RDMs

# 16.07. - 22.07.2018

## Monday
- created conceptual models for musicians and non-musicians
- remade conceptual models (allUnequal, allEqual, mainGenres & randomization) so that they are available in csv format
- visualized them in jupyter notebook --> good cmap to visualize: Spectral_r
- failed at creating MDS plots because there is no input in concatenating function (after concatenating there is no data in "asdfasdfadsf.pkl")
- uploaded all conceptual models in Google Drive
- uploaded all RDMs of musicians and non-musicians in Google Drive

## Tuesday
- wrote down the procedure of computing the results
- created RDMs for music feature models

## Wednesday
- created average_RDM and average_MDS of musicians and all again because I included the two outliers on monday
- created second_order MDS of all and musicians
- uploaded everything on google drive
- tried to do a MDS for every single person (Error: ValueError: Length mismatch: Expected axis has 20 elements, new values have 19 elements)
- concatenating function doesn't work when it is run as a whole --> only seperate parts of that should be run and with this part of the script it works: 
- global dict_rdms
- global DefaultListOrderedDict
- from os.path import join as opj
- import sys
- from glob import glob
- from scipy.io.matlab import loadmat
- import pandas as pd
- from collections import OrderedDict
- import pickle

- class DefaultListOrderedDict(OrderedDict):
    - def __missing__(self,k):
        - self[k] = []
        - return self[k]
- path='/home/...'
- list_rdms=glob(path + '*.csv')
- keys=['id','rdm']
- id = []
- rdms =[]
- for file in list_rdms:
    - id.append(file[(file.rfind('/') + 1):file.rfind('.')])
    - rdms.append(pd.read_csv(file))
- global dict_rdms
- dict_rdms = DefaultListOrderedDict()
- for key in keys:
    - for id_rdm in enumerate(id):
        - if key == 'id':
            - dict_rdms[key].append(id[id_rdm[0]])
        - elif key == 'rdm':
            - dict_rdms[key].append(rdms[id_rdm[0]])
- pkl_rdm = open("rdm.pkl", "wb")
- pickle.dump(dict_rdms, pkl_rdm)
- pkl_rdm.close()

*
- wrote a description of the average_RDM for all subjects, for musicians only and for non-musicians only
- looked up which part of the songs we use in our study (if intro, chorus or verse)

## Sunday
- reading for introduction 

# 24.07. - 27.07.2018

## Monday
- created a data sheet where all data is stored together for all participants

## Tuesday
- filled in the last participants in data sheet where all participants data is stored together
- prediction of groups by matrices: 
    - therefore, I converted the matrices into vectors
    - command for that: 
        - import nilearn
        - from nilearn import connectome
        - import pandas as pd
        - data_sub01 = pd.read_csv('copy path of csv-file')
        - matrix_sub01=data_sub01.as_matrix()
        - vector_sub01 = nilearn.connectome.sym_matrix_to_vec(matrix_sub01, discard_diagonal=True)
    - then the vectors have to be put together in one nested array
    - command for that:
        - imds = np.array([vector_sub01, vector_sub02, vector_sub03, vector_sub04, vector_sub05, vector_sub06, vector_sub07, vector_sub08, vector_sub09, vector_sub10, vector_sub11, vector_sub13, vector_sub15, vector_sub16, vector_sub17, vector_sub18, vector_sub19, vector_sub20, vector_sub21])
    - another array is necessary where every subject gets a group name (group names are in order of vectors --> vector_sub01 is non-musician in 0 index in classes array
        - classes = np.array(['non-musician', 'musician', 'musician', 'musician', 'musician', 'musician', 'musician', 'non-musician', 'musician', 'non-musician', 'musician', 'non-musician', 'non-musician', 'non-musician', 'non-musician', 'non-musician', 'non-musician', 'musician', 'musician'])
    - cross-validation of subjects
        - import numpy as np
        - from sklearn.model_selection import StratifiedShuffleSplit

        - n_iter = 10000
        - _, classes_binary = np.unique(classes, return_inverse=True)
        - cv = StratifiedShuffleSplit(n_splits=n_iter, test_size=0.5, random_state=0)
    - prediction of groups by several classifiers
        - from sklearn.model_selection import cross_val_score
        - from sklearn.svm import LinearSVC
        - svc = LinearSVC(penalty='l2', random_state=0)

        - from sklearn.naive_bayes import GaussianNB
        - gnb=GaussianNB()

        - from sklearn.ensemble import RandomForestClassifier
        - rfc=RandomForestClassifier()

        - from sklearn.neighbors import KNeighborsClassifier
        - knc = KNeighborsClassifier()


        - iter_for_prediction = cv.split(imds, classes_binary)
        - scores = []
        - # Try cv.get_n_splits()
        - for index, (train_index, test_index) in enumerate(iter_for_prediction):
        -  prediction_scores = cross_val_score(
        - estimator=svc,  # classifier
        - X=imds,  # Data to fit
        - y=classes_binary,  # Target variables
        - scoring='roc_auc',  # scoring
        - cv=[(train_index, test_index)],
        )
        - scores.append(prediction_scores)  # for each split we gather scores

        - scores = np.asarray(scores)
        - print(" -- Support Vector Classification -- ")
        - print("Classification scores '%s': %1.2f +/- %1.2f" % ('correlation',
                                                       scores.mean(),
                                                       scores.std()))
    - all code is taken from https://github.com/KamalakerDadi/Tutorial/blob/master/BrainHack/Paris_2017/plot_cobre_connectivity_analysis.ipynb

## Wednesday
- data analysis

## Thursday
- writing on methods part

## Friday
- writing on methods part

# 30.07. - 03.08.2018

holidays

