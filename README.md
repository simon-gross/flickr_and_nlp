# Matching Flickr Photos to City Districts in Vienna

[Flickr](https://www.flickr.com/) is an easy-to-access data source for user-generated pictures. The pictures contain textual data, e.g. the title, a description or comments. Furthermore, using the transformer package and a huggingface model, it is possible to generate a short description of a picture.

Apart from that, districts in Vienna also have associated textual data. This could be for example their wikipedia entries or descriptions of points of interest in each district.

Using spacy and gensim Doc2Vec, we can use all of these textual clues to create an embedding space. Then for each pictures texts the district with the highest similarity associated with the picture. We can verify the experiment by using the geographic coordinates associated with the pictures.

A more complex apporach with using a random subset of the geotagged pictures as training data first is explored at the end.

# See the Jupyter Notebook for a guide through the code

# Data Sources

Viennese boundaries and the POI information is from data.gv.at.
- [top-locations-wien.csv](https://www.data.gv.at/katalog/dataset/45d684ca-6ad7-4c5e-a721-64aa31795824#resources)
- [District Boundaries](https://www.data.gv.at/katalog/dataset/2ee6b8bf-6292-413c-bb8b-bd22dbb2ad4b#additional-info)

Pictures are from [Flickr](https://www.flickr.com/), queried via API.

The model to generate image captions is from [huggingface](https://huggingface.co/)
- The concrete model is [Salesforce/blip-image-captioning-large](https://huggingface.co/Salesforce/blip-image-captioning-large)
