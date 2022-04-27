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
- PCR free libraries for 30x coverage, it’s enough DNA (1ug of human DNA)


#### NexTera DNA Flex lib prep kit:
<img width="500" alt="image" src="https://user-images.githubusercontent.com/78726635/165444861-0932bef3-513f-46de-9dd6-4ee9b4fcee49.png">
- DNA not fragmented (mega bp), the longer DNA you retain, the better coverage you’ll get
- Illumina à 150bp longest read on each strand (total of 250-300bp, only ~50bp overlap)

#### Fragmentation of DNA aka tagmentation: 
#### Enzyme (cuts DNA down to 200-400bp) and incorporates general adaptors in one step, during PCR amplification indexes
<img width="400" alt="image" src="https://user-images.githubusercontent.com/78726635/165445241-01dec428-6914-4534-be55-7b001e818e1e.png">

- Sequencing
- PCR free
- Sanger

## 4 - Library Enrichment Methods

**Library Capture** - refers to the actual process of capturing specific regions of interest \
**Enrichment** - refers to the preferential acquisition of regions of interest as opposed to other regions. 

In most cases you can use these terms pretty interchangeably. The main concept of these methods involves amplifying specific regions of the genome, while disregarding regions that are not of interest

### Doing a capture involves: 
- Designing baits (aka probes) for specific regions, based on specific mitochondrial regions (for mito capture) or a particular panel based on reference genome
- Using a pull-down method to grab only sequences the probes are designed for (usually via magnetic beads)
- If you don’t have a reference, you need to design them based on common regions between sister species. 
- It’s also important to note that there will always be ascertainment bias for what you design the baits on 

### Why do we want to perform a capture?
- Ancient DNA has a huge majority of microbial contamination - so we want to fish out the endogenous content
- For humans, the 1240k bait set is biased towards African + European populations, as it was designed using those references. The 2.2M capture set is better because it includes more Oceanian populations (and also includes 1240K)
- However, when using the 2.2M capture, you don’t have as much previous data to compare to, since it was only released in 2022 and previous captures have all been done using 1240K

### Overall flow of capture protocol:
First, all DNA fragments in a library have Illumina adapters added to them. Blockers are then added, which bind to the adapters to prevent them all sticking to each other when denatured. Probes (made up of DNA designed for the regions of interest, or targets, attached to biotin molecules) are then added and left to hybridise to target fragments for a few hours. Next, probe-target hybrids bind to streptavidin-coated magnetic beads (via strong biotin-streptavidin binding) and off-target DNA is washed off. After several washes you have the remaining enriched library which you then PCR amplify either on-bead or off-bead (some protocols you just leave the beads in the PCR reaction and the will detach during denaturing. 

<img width="744" alt="image" src="https://user-images.githubusercontent.com/78726635/163918023-1d68d7e2-a20c-4501-a9c3-597b45a9f43b.png">


#### A few notes about this process:

- During the washing steps, some off-target DNA can remain with the targets, and you can also lose some target regions in washes, especially if your capture is not efficient/there is no reference panel on which you designed your probes
- Legend has it that you can retrieve target DNA that has seeped into your non-target washes, so always keep these. However, these washes comprise supernatant with binding buffer, blockers, non-target and other reagents. Xavi tried very hard to clean this supernatant to extract DNA for another round of capture, but it was not possible despite his legendary skills. There are whispers of someone who has managed to do it but they might have been using the dark arts. Who knows! You are better off using fresh library for another capture round if you can. For the current human protocol we use, you have to do TWO captures - if you only do one you get weird fragments sizes. Robbi has tested all the reagents for contamination but couldn’t find anything, she also did one round of capture on water and still got the same weird results. However, with two rounds of capture this was solved. 
- So all you have to do is two captures! HOW?? IT'S MAGIC!! Evelyn has a hypothesis that maybe the blocker concentration is not high enough and only reaches enough concentration on the second round which could explain the weird fragment sizes from daisy-chaining (from lack of blocking). 
- It’s recommended not to pool more than 4 samples for modern and not to pool at all for ancient DNA, but we do it anyway to save time and money. This does run the risk of one sample at high endogenous content and/or concentration taking over and winning the competition for enrichment with poorer quality samples, so you could lose reads from those. 
- Here is DIY bait creation in 3 easy steps with Xavi: First amplify your fragments. Then ampure purify them, nanodrop (to determine conc) and pool (to get equimolar quantities). Then we do in vitro DNA to RNA transcription. Then clean up fragments using an enzyme, and biotinylate your fragments with UV (crosslink them together)...and VOILA BON APPETIT!!

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

