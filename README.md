# Finding-Similar-Clinical-Trials


## **Background:**

The ability to search for clinical trials that are similar to an index trial can be very useful for trial participants, investigators as well as researchers interested in synthesizing medical evidence. For instance, participants can search for a trial similar to the one they were no longer able to enroll in. Locating past or ongoing trials that are similar to their own, can help investigators connect with fellow-investigators that are enrolling similar patients and make informed site-selection decisions. Searching for similar trials is also of interest to medical researchers interested in synthesizing evidence from trials that address similar research questions.

Chimeric Antigen Receptor (CAR) T Cell therapy has emerged as a miracle cure for patients with hematologic cancers and has witnessed rapid advancements in the design and manufacture of novel CAR constructs, in-vivo persistence, safety and response duration. Currently over a 1000 interventional trials evaluating CAR T cell therapies are registered on ClinicalTrials.gov. Our goal is to group (cluster) CAR T cell trials on the basis of attributes available in the respective study records on ClinicalTrial.gov.

## **Goals:**

To cluster the CAR T cell clinical trials using the aforementioned attributes from their respective records. Visualize and describe the clusters identified (using enrichment analysis or similar methods).

## **Data availability:**

ClinicalTrials.gov is a publicly accessible registry of clinical trials wherein a record for each registered trial is maintained. Each record captures key attributes pertaining to the trialâ€™s objectives, design, start date, medical interventions, eligibility criteria and outcomes. Study records contain both structured (eg. start date, NCT id, target enrollment, sponsor etc) as well as unstructured (e.g. eligibility criteria) fields. A Postgres database maintained and updated daily by the clinical trials transformation initiative (CTTI) contains study records indexed by a unique identifier (NCT id). A local instance of this database has already been created and can be accessed by students working on this project. Additionally, NCT ids for trials on CAR T cell therapies have also been compiled and are available as a CSV file.

## **Additional resources:**

Each clinical trial defines eligibility criteria for patients that may enroll for the trial. Eligibility criteria usually consist of a set of inclusion and a set of exclusion criteria based on considerations such as age, gender, race, medical and treatment history, and are written as free-text. We have identified medical concepts contained in the eligibility criteria of 1036 CAR T cell clinical trials and have mapped these to their respective concept identifiers and text labels as specified in the Unified Medical Language System (UMLS). Therefore, associated with each of the aforementioned 1036 CAR T cell clinical trials, we have a 'bag of medical concepts' drawn from its inclusion criteria and another one drawn from its exclusion criteria.

## **Evaluation:**

Evaluation of clustering performance will be based on 1) Sillhoutte score (scikit-learn Python library supports this) 2) Callinski-Harabasz Index (see this article on clustering analysis metrics. scikit-learn supports all those metrics).

We propose to use the following approach to assess cluster stability

Resample from the given dataset and apply the clustering algorithm to the resampled data
For each cluster in the original clustering find the most similar cluster in the clusters produced from the resampled data
Repeat K times and compute the mean simalirity across all resampled sets for each cluster
Teams will be required to provide cluster performance and stability evaluation code chunks as part of their submissions
