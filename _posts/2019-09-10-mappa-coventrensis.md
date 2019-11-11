---
layout: post
title:  "Mappa Coventrensis"
date:   2019-09-10 12:55:00 +0100
categories: data
---

## Data visualization for the city of Coventry, UK  

___

# Datasets  
- Geospatial data (LSOA in England and Wales) from [Office of National
  Statistics](http://geoportal.statistics.gov.uk/datasets/90e15daaaeef4baa877f4bffe01ebef0_0?geometry=-122.695%2C-29.382%2C98.965%2C29.382&page=585)
- [Geo coordinates of postcode in the UK](https://www.getthedata.com/open-postcode-geo) (redirected from [data.gov.uk](https://data.gov.uk/dataset/091feb1c-aea6-45c9-82bf-768a15c65307/open-postcode-geo))
- Shapefiles for UK postcodes: Pope, Addy. (2017). GB Postcode Area, Sector, District, [Dataset]. University of Edinburgh. [https://doi.org/10.7488/ds/1947](https://doi.org/10.7488/ds/1947).
- [UK school census](https://www.gov.uk/school-performance-tables)


# Further sources  
- [The Coventry Society](http://www.coventrysociety.org.uk)
- Lower Layer Super Output Areas (LSOAs)
  - [data.gov.uk](https://data.gov.uk/dataset/c481f2d3-91fc-4767-ae10-2efdf6d58996/lower-layer-super-output-areas-lsoas)
  - [wikipedia](https://en.wikipedia.org/wiki/ONS_coding_system#Neighbourhood_Statistics_Geography)
  - [NHS data dictionary](https://www.datadictionary.nhs.uk/data_dictionary/nhs_business_definitions/l/lower_layer_super_output_area_de.asp?shownav=1)

___

### Geography: LSOAs and postcodes


# Coventry LSOAs
Lower Layer Super Output Areas (LSOAs) are are a geographic hierarchy designed
to improve the reporting of small area statistics in England and
Wales. 
<p align="center">
<img src="{{site.baseurl}}/assets/mappa-coventrensis/coventry-lsoas.png"
alt="Coventry LSOAs"/>
</p>

# The postal area `CV`  
Postal areas are the geographical areas corresponding to the first two
letters of postcodes.  
The postal area `CV` covers an area much larger than Coventry itself.  
<p align="center">
<img
src="{{site.baseurl}}/assets/mappa-coventrensis/postal-area-cv.png"
alt="Coventry and postal area CV"/>
</p>

# Postal districts in the city of Coventry  
A postal area is divided into postal districts, which are the
geographical areas corresponding to the first half of the postcode
also known as the outward code.  

Postal districts and LSOAs do not align exactly.  Postal districts
`CV1` through `CV6` roughly cover the city of Coventry.  


<p align="center">
<img
src="{{site.baseurl}}/assets/mappa-coventrensis/coventry-postal-districts-lsoas.png"
alt="Postal districts and LSOAs in the city of Coventry"/>
</p>


<figure>
<img 
src="{{site.baseurl}}/assets/mappa-coventrensis/coventry-lsoa-postal-district-intersection-count.png"
>
<figcaption>
In the figure above, the postal districts CV1 through CV6 are
delineated in red.  The postal districts in dark blue are contained in
a single post district; those in light blue intersect two postal
districts; and those in white intersect three postal districts.  
</figcaption>
</figure>


# Postal sectors in the city of Coventry  
A postal district is subdivided into postal sectors.  A postal sector
is the geographical area corresponding to the second part of the
postcode with the last two letters removed.  

<p align="center">
<img
src="{{site.baseurl}}/assets/mappa-coventrensis/coventry-postal-districts-and-sectors.png"
>
</p>


Postal sectors and LSOAs do not align exaclty.  

<figure>
<img
src="{{site.baseurl}}/assets/mappa-coventrensis/coventry-postal-sectors-lsoas.png"
>
<figcaption>
In the figure above, postal sectors are delineated in read.  LSOAs are
in blue, with their boundaries in black.
</figcaption>
</figure>



# Coventry's neighbourhoods  
In the dataset [GB Postcode Area](https://doi.org/10.7488/ds/1947),
sectors are assigned a "locale", which broadly coincide with the
notion of neighbourhoods, at least in comparison to
[those listed by the Coventry Society](http://www.coventrysociety.org.uk).  

<p align="center">
<img
src="{{site.baseurl}}/assets/mappa-coventrensis/coventry-postal-sector-locales.png"
>
</p>


___

### Schools in Coventry  
In the year 2017-2018, Coventry counted:  
- `111` primary schools, of which `98` within postal districts
`CV1`--`CV6`;  and  
- `32` secondary schools, of which `28` within postal districts
  `CV1`--`CV6`.  

<figure>
<img
src="{{site.baseurl}}/assets/mappa-coventrensis/coventry-schools.png"
>
<figcaption>
In the figure above, primary schools are depicted in circles,
secondary schools not offereing post-16 education are depicted in
unfilled squares, and secondary schools offering post-16 education are
depicted in solid squares.
</figcaption> </figure>


<figure>
<img
src="{{site.baseurl}}/assets/mappa-coventrensis/coventry-school-count-per-postal-district.png"
>
<figcaption>
The figure above shows the distribution of schools across postal districts
in Coventry.  
</figcaption>
</figure>
