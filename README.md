# Milestone 1 (a Data Collection, Manipulation, Analysis, Visualization & Classification project)
# Exploring-drug-targets-and-their-effect-on-drug-approval
By Sharadwata Ganguli and Sandro Bruno

## <a href="https://github.com/s-ganguli/Exploring-drug-targets-and-their-effect-on-drug-approval/blob/main/17-sganguli-brunosa.pdf"> Project report here</a>


## Project Summary
Drug development is a resource and time intensive venture requiring decades and billions of dollars in investment. Most drug failures happen at late stage – often due to adverse safety findings or lack of efficacy. This project consists of Phase1 and Phase2. In Phase1, relationship between efficacy and safety parameters with drug approval was explored. In Phase 2, prediction models were evaluated to predict drug approval based on efficacy and safety data.

5 different data sources (1 efficacy, 1 ground truth label and 3 safety) were used – having different formats (JSON, txt, tsv, gmt), sizes (0.17 MB to 21GB) and access
methods (wget, direct download). The data collected covered 96% of all currently known human protein coding genes.

We have used google colab with google Drive as file system. The individual datasets were both quantitatively as well as visually explored to identify the need for any
cleaning/manipulation/new feature generation. Datasets were relatively clean. Post manipulation to generate new features, intermediate data files (not the initial raw data) were saved for further processing. These intermediate files are present in this repo.

At Phase 2, we found target class data to be imbalanced, 4 different approaches were applied to model the imbalance dataset (up/down-sampling, cost-sensitive training, adapt scoring metric). Various machine learning models were compared, GradientBoosting was the best performing classifier showing generalizability on the validation set (0.89). Safety features found to improve the classification AUROC. The top 3 performing classifiers were explored using model agnostic methods such as SHAP. These
uncovered the inverted directionality of 2 out of 3 hypothesized safety features.13.4% of all genes under investigation are predicted to make it on the market.


## Project Steps
* Phase 1 Step 1: Load the datasets in individual notebooks
* Phase 1 Step 2: Change gene/ protein keys to ‘gene symbols’ for JOIN keys
* Phase 1 Step 3: Explore the dataset quantitatively
* Phase 1 Step 4: Explore the dataset visually
* Phase 1 Step 5: Manipulate the dataset as needed 
* Phase 1 Step 6: Save intermediate datasets for later analysis
* Notebooks required for above steps --> <a href="https://github.com/s-ganguli/Exploring-drug-targets-and-their-effect-on-drug-approval/blob/main/01_association.ipynb">01_association.ipynb</a> , <a href="https://github.com/s-ganguli/Exploring-drug-targets-and-their-effect-on-drug-approval/blob/main/02_Centrality_score.ipynb">02_Centrality_score.ipynb</a> , <a href="https://github.com/s-ganguli/Exploring-drug-targets-and-their-effect-on-drug-approval/blob/main/03_baseline.ipynb">03_baseline.ipynb</a> , <a href="https://github.com/s-ganguli/Exploring-drug-targets-and-their-effect-on-drug-approval/blob/main/04_onco.ipynb">04_onco.ipynb</a> , <a href="https://github.com/s-ganguli/Exploring-drug-targets-and-their-effect-on-drug-approval/blob/main/05_ground_truth.ipynb">05_ground_truth.ipynb</a>
* Phase 2 Step 1: Integrating Data Sets 
* Phase 2 Step 2: Building and Evaluating Classification Models 
* Notebooks required for above steps --> <a href="https://github.com/s-ganguli/Exploring-drug-targets-and-their-effect-on-drug-approval/blob/main/07.1_dataset_integration.ipynb">07.1_dataset_integration.ipynb</a>  , <a href="https://github.com/s-ganguli/Exploring-drug-targets-and-their-effect-on-drug-approval/blob/main/07.2_dataset_integration_relationship_visualization.ipynb">07.2_dataset_integration_relationship_visualization.ipynb</a>


## Data Sets used
1. Efficacy –  association	https://storage.googleapis.com/open-targets-data-releases/21.02/output/21.02_association_data.json.gz
2. Safety – protein  network	https://version-10-5.string-db.org/download/protein.links.v10.5/9606.protein.links.v10.5.txt.gz
3. Safety – baseline	https://storage.googleapis.com/open-targets-data-releases/21.02/input/annotation-files/baseline_expression_counts-2020-05-07.tsv
4. Safety –  Onco genes	http://www.gsea-msigdb.org/gsea/msigdb/genesets.jsp?collection=C6
5. Ground truth	http://db.idrblab.net/ttd/sites/default/files/ttd_database/P2-01-TTD_uniprot_all.txt
