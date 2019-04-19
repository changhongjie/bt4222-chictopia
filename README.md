# bt4222-chictopia
Group Project for BT4222 on image-based fashion auto-tagger.

The objective is to simplify the manual tagging of style categories when users share images on Chictopia (http://www.chictopia.com/),  through the use of Machine Learning techniques and models to understand fashion semantics from images of people. This automation provides both better User Experience as well as consistency of tags.

Links to [presentation slides](https://docs.google.com/presentation/d/1nBkYq5ItAoaFNd3p6EdxdFOlYmV60QmifROt3JFnAbU/edit?usp=sharing), 
[report](https://docs.google.com/document/d/1R2MiG0BAvXMWWo6ca8vRD92-3tDowzkcMbZIoWE_CDo/edit?usp=sharing).

## Directory Structure
```
.
├── Processed_data                    # datasets used
│   ├── dress_info.csv
│   └── ...                 
├── cropped                        			# folder of cropped images
│   └── ...                 
├── images                         			# raw images scraped
│   └── ...                 
├── Background Removal.ipynb      	   # NNs for removing background
├── Data Collection.ipynb      			    # Scraping Chictopia
├── Tags NLP.ipynb      					         # NLP algorithms for preprocessing labels
├── Simple CNN model.ipynb      	     # CNN model for predicting tags on images
├── requirements.txt 				     	       # Pip requirements file
├── conda_env.yaml				      	         # Anaconda env YAML file
└── README.md
```

## Requirements

Recommend setting up the Anaconda environment using conda_env.yaml. There are some conflicting version dependencies for Numpy across the libraries used, but no known errors with using numpy=v1.16.
Pip's requirements.txt provided as well.


## Description of Notebooks

* `Data Collection.ipynb`: 
  * Purpose - Notebook to Scrape dress photos and data from Chictopia
  * Output - `dress_info.csv`
* `Background Removal.ipynb`:
  * Purpose - Automated cropping of photo backgrounds using pre-trained Object Detection networks
  * Output - images in `./cropped/`
* `Tags NLP.ipynb`: 
  * Purpose - Preprocess Tag labels using various NLP algorithms
  * Output - `<algorithm>_<drop_threshold>.csv`, e.g. `combine_10.csv`
* `Simple CNN model.ipynb`:
  * Purpose - Model for predicting style tags on images, used to compare against AutoML results
  * Output - `None`

## Notes & Credits
__Things to note:__
* Anaconda v4.5.11 was used to build and test the notebooks
* AutoML was used in building the final models. We compare its performance in our report above.

__Credits:__
* Zhao Yiliang, for his advice and guidance
* Project Team members - You Yin & Gan Hui Kang
* Chictopia, for the images we scraped - http://www.chictopia.com/
* Google AutoML for building the final model - https://cloud.google.com/automl/
