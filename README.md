# Connecticut Zip to School District Crosswalk

The `data/zip2secondary.csv` file contains a crosswalk between CT zipcodes and
secondary school districts in CT.

To prevent Excel from transforming zipcodes to numbers automatically
(which leads to losing 0s from zipcodes), do the following:

1. Open Excel, New workbook
1. Go to File > Import > CSV file
1. Choose file, and select "text" as type of zip5 column


### How it was generated
In QGIS, open zipcode boundaries, calculate their centroids, and perform nearest neighbor spatial join
(NNJoin plugin) to assign the closest secondary school district. All centroids fall within one
school district, so the generated `distance` column will have all 0s.

### Source datasets

* Connecticut secondary school districts: http://magic.lib.uconn.edu/connecticut_data.html#education
* Connecticut zipcode boundaries: https://data.ct.gov/Government/Zip-Code-Tabulation-Area-Boundaries/n7kw-xx5z
