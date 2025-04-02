# Repository for the publication: DID YOU UNDERSTAND THE PROBLEM? – EVALUATING FINE-TUNED LANGUAGE MODELS FOR IDENTIFYING AI-RELATED TASKS IN PRODUCT DEVELOPMENT
## Abstract
Recent advancements in machine learning (ML) offer significant potential to support product development. However, adoption in industry remains limited due to challenges in the initial step of translating domain-specific product development problems into ML-related tasks. This process requires domainspecific knowledge in both product development and ML, which is often lacking. Prior research investigated the use of large language models (LLMs) as recommender systems for suggesting suitable ML algorithms based on product development-related problem formulations. However, the results indicated only moderate success, primarily due to a lack of understanding of the underlying product development tasks, which often led to incorrect identification of the corresponding ML problem types. Therefore, this study investigates the use of small, fine-tuned language models (LMs) for classifying product development-related problem formulations into ML problem types as a preliminary step toward identifying suitable ML algorithms for the respective task. A curated dataset of 400 problem statements, extracted from abstracts of peer-reviewed publications identified through a systematic literature review, was expanded to 2,400 entries using lexical and semantic data augmentation. This dataset was subsequently used to fine-tune and evaluate both encoder-only and decoder-only models. The findings indicate that decoder-only models surpass encoder-only models in performance, reaching F1-scores of up to 83.9% on the augmented dataset. However, performance drops significantly when controlled data splits are applied, indicating a tendency toward overfitting rather than generalization. Future research should focus on expanding the dataset and exploring prompt engineering techniques to enhance model performance

## Repository Content
This repository includes the following files, created as part of the publication:
1. **Documentation of the systematic literature review (TXT)**
2. **Literature data (BibTeX Files)**
3. **Created dataset (JSON)**

### Documentation of the systematic literature review (TXT)
The literature review, aimed at identifying publications that address the application of machine learning algorithms to product development-related problems, was conducted following the PRISMA 2020 guidelines. A detailed documentation of the review process is provided in the accompanying text file, which includes:
- The definition of topic groups containing synonyms related to the subject, used as keywords
- The search strings applied
- The inclusion and exclusion criteria
- The restrictions implemented in the Scopus and Web of Science databases during the search process

### Literature data (BibTeX Files)
The publications identified through the systematic literature review have been categorized based on the type of machine learning problem they aim to address, referred to as machine learning problem types. The four primary categories considered are: Classification (Cla), Regression (Re), Clustering (Clu), and Association Rules (Ar). These categorized publications form the foundation of the dataset and are provided in separate BibTeX files. The naming convention for the files is as follows:
- Classification (Cla): *Cla_Publications_identified_as_suitable*
- Regression (Re): *Re_Publications_identified_as_suitable*
- Clustering (Clu): *Clu_Publications_identified_as_suitable*
- Association rules (Ar): *Ar_Publications_identified_as_suitable*
  
### Created dataset (JSON)
In order to fine-tune and evaluate the performance of the language models (LMs), three different dataset variants were created, each consisting of a training, validation, and test set:
1. The **original dataset**, containing 400 non-augmented entries
2. The **randomly split augmented dataset**, comprising 2,400 entries generated through data augmentation
3. The **controlled-split augmented dataset**, also comprising 2,400 entries, in which original entries and their augmented versions were strictly separated across splits to prevent data leakage

Each dataset contains two key elements:
- **Product development-related problem formulations**, extracted from the identified publications
- **Machine learning problem type**, serving as labels that indicate the type of ML problem addressed in the formulation
