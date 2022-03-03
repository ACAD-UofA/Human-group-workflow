# Human-group-workflow
A philosophical overview of everything technical that we do from lab to bioinformatics (discussions from 2022 humans group)

## 1 - From Bone to DNA
### Lab
This is pre-PCR work, done in ancient DNA lab with following anti-contamination protocols.

<img width="200" alt="image" src="https://user-images.githubusercontent.com/78726635/150440157-78745565-d057-449b-bc4e-3a72c987af44.png">

### Bones
- Most often teeth are used, usually the roots
- petrous bone (dense bone with good DNA preservation, part of the inner ear structure) 
- humerous, rib or other bones are less common but can be used.

<img height="350" alt="tooth" src="https://user-images.githubusercontent.com/78726635/150442139-0fc1f26f-d41b-4b74-bb40-6c22d14193d3.png"> <img height="350" alt="petrous" src="https://user-images.githubusercontent.com/78726635/150442000-eda707b9-cade-43f6-9e15-a9519b97e625.jpg">


Bone extraction is messy, so must be careful not to cross-contaminate. Change gloves and clean a lot etc. 

1. Clean with bleach & alcohol (only teeth)
2. scraping off the surface
3. Cut crown away from the root with disk dremel (in laminar flow hood) or cut the part of the cochlea 
4. Try to get rid of dental pulp (the part where blood goes and most bactieria are). 
5. Pulverise into powder at room temperature and use powder for DNA extraction


### DNA Extraction 
Two day protocol
Day One:
1. Input 0.1g bone powder to extraction & keep the rest as backup powder. more powder could result in more quantity of DNA and better complexity theoretically.
2. Pre-digestion with EDTA 
3. EDTA (breaks calcium) + proteinase K (degrade protein) - overnight incubation.

Day Two:
1. Add silica in tube and spin down, remove supernatant 
2. Silica binds DNA (Silica is broad range so good for capturing short molecules, like aDNA)
3.  with binding buffer
4. Many ethanol washes
5. Elute DNA from silica with TLE and 50°C heat
6. Result = "Stock solution" and "working solution"
7. Quantify

For every extraction batch, do an EBC or Extraction Blank Control, to test underlying contamination of the lab \
- Scoop air from the hood into empty tube, treat as if it is a sample following the same protocol

## 2 - Library Preparation Methods - Ancient DNA

### Jena Protocol

DNA Post-Mortem Damage can happen very fast but still depends on the environmental condition such as temp, humidity, and age of the remains. 
 - Deaminated Cytosines into Uracil 
 - Extensive fragmentatio (endup with sticky end fragment and uracil at the end of hanging)

Due nature of deamination, there is an effort to polish the DNA
 - Make 5’ and 3’ blunt end using polymerase, sticky end (Uracil end will have A complement)
 - T4 PNK (Polynucleotide Phospatase) —> add Phosphate groups on 5’ so the ligation can be performed between adapter and “Insert” 
 - Ligate the adapter. In the adapter, we add some unique identifier (index) to differentiate between samples. However , there is absent of ligation in 3’
 - Add Bst (sort of Polymerase) to add complement from adapter which ligate to 5’. Here is the template for the library  
 - During the amplification, we will have T (Thymine) - A (Adenine) on each 5’ and 3’ instead of Uracil (U)

Treatment to remove single stranded hang of uracil (Full UDG Repair ) -
 - Add T4 PNK to add phosphoriulate your DNA
 - USERS (Commercial reagent with UDG and EndoVIII) will recognise U and create abasic site to cut the segment with uracil and phosphorilates both ends
 - T4 PNK will create OH on 3’
 - Polymerase will ligate the fragment.
 - Follow protocol 4-5 in upper.

Half UDG repair will gave one of the end Uracil intact by adding UGI after add USERS reagen which block the UDG on one of the sticky end. 


## 3 - Library Preparation Methods - Modern DNA

## 4 - Library Enrichment Methods

## 5 - Other pre-sequencing methods 

## 6 - Sequencing Methods

## 7 - SeqData Processing I (Raw data --> mapping)

## 8 - SeqData Processing II (Mapped data --> Variant Calling)

## 9 - Popgen I (admixture and ancestry)

## 10 - Popgen II (F-statistics)

## 11 - Popgen III (Mitochondrial data and other specific markers)

## 12 - Selection

## 13 - Gene annotation/pathways

## 14 - General Statisitcs

## 15 - Modelling

