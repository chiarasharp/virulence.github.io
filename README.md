# Virulence

## Table of Contents

1. [Introduction](#introduction)
2. [Scenario](#scenario)
3. [Original Datasets and Mashup](#original-datasets-and-mashup)
    1. [Original Datasets](#original-datasets)
    2. [Mashup Dataset](#mashup-dataset)
4. [Data Analysis](#data-analysis)
    1. [Quality Analysis](#quality-analysis)
    2. [Legal Analysis](#legal-analysis)
    3. [Technical Analysis](#technical-analysis)
    4. [Sustainability](#sustainability)
5. [Website and Data Visualization](#website-and-data-visualization)
6. [Conclusion](#conclusion)

## <a name="#introduction"> 1. Introduction</a>
The goal of this website is to explain, in a comprehensible way, the evolution of the disease COVID-19 in Italy in the first wave of the pandemic (february to may 2020), focusing our attention on the causes that made our country one of the most affected by the pandemic, and how these causes influenced each other in the process, all of this by looking at 2019 data. We took into consideration many aspects of the virus that have probably been underestimated or ignored at first, in order to provide people a clear idea of what COVID-19 is and which countermeasures could be adopted to deal with it. Virulence (that's the name of the project) aims to tell this story through a proper use of legal and ethical analysis, metadata exploitation and datasets cleaning, in order to provide a neat mashup of all the information sources gathered during the research steps. For convenience, the work has been split into 4 parts:

- Metadata, featuring the metadata of Virulence dataset and the datasets from the primary sources;
- Visualization, where data results are represented through comprehensible maps and graphs;
- Documentation, where every step of the research is explained and where we analyze the collected data;
- License, the license of our project.

## <a name="#scenario"> 2. Scenario</a>
Why did COVID-19 spread so rapidly in Italy, making us reach one of the highest death rates in the world? There was the need to look at the conditions that made it possible, gathering information through data and articles from multiple sources. It is often demonstrated that the most relevant events may originate from the most unexpected causes. We will indeed have the chance to look at them carefully.

Now we are gonna discuss the many aspects taken into consideration during the research. The following list has been considered for all the 20 italian regions:

- Air pollution due to PM10;
- Temperatures;
- Density of population;
- Age of population;
- Number of hospitals.

All these factors have been considered only within 2019, that is shortly before the official appearance of COVID-19. We did so in order to have an idea of ​​how much Italy was actually predisposed for an extensive spread of the virus.

## <a name="#original-datasets-and-mashup">3. Original Datasets and Mashup</a>


### <a name="#original-datasets">3.1 Original Datasets</a>

The datasets used for our project. In the next sections we are going to analyze them from various points of view.


|ID|FILE|DESCRIPTION|DATASET|CATALOGUE|URI|LICENSE|LAST UPDATE|DOWNLOADED|
|--|--|--|--|--|--|--|--|--|
|1:COVID|dpc-covid-19-ita-regioni.csv|COVID-19 data for every italian region. We took the cases and deaths of the first pandemic wave (february to may 2020).|COVID-19 Monitoraggio situazione Italia (RNDT - Serie) - Versione 2.0|RNDT - Repertorio Nazionale dei Dati Territoriali - Servizio di ricerca|https://github.com/pcm-dpc/COVID-19/blob/master/dati-regioni/dpc-covid19-ita-regioni.csv|https://creativecommons.org/licenses/by/4.0/|December 10, 2021|January 12, 2022|
|2:POP|DCIS_POPORESBIL1_12012022143315331.csv|Population of every italian region in 2019. We only took the ‘popolazione inizio periodo’ row from the database.|Popolazione residente - bilancio|I.Stat|http://dati.istat.it/viewhtml.aspx?il=blank&vh=0000&vf=0&vcq=1100&graph=0&view-metadata=1&lang=it&QueryId=18461&metadata=DCIS_POPORESBIL1|https://creativecommons.org/licenses/by/3.0/it/||February 8, 2022|
|3:PM10|DataExtract.csv|PM10 mean level of 2019 for every italian station that measure it. We calculated the mean of all the values of the stations in the same italian region and created a single value for every italian region.|Air quality annual statistics calculated by the EEA|Air Quality e-Reporting (AQ e-Reporting)|https://discomap.eea.europa.eu/App/AirQualityStatistics/index.html?Country=Italy&AirPollutant=PM10&DataAggregationProcess=Annual%20mean%20/%201%20calendar%20year&ReportingYear=2019|https://creativecommons.org/licenses/by/4.0/|February 18, 2022|March 10, 2022|
|4:SUP|DCCV_CARGEOMOR_ST_COM_27032022165808849.csv|The total area of land for every italian region calculated at the beginning of 2020. We used it, together with the data about the population, to calculate the population density.|Superfici territoriali|I.Stat|http://dati.istat.it/Index.aspx?DataSetCode=DCCV_CARGEOMOR_ST_COM#|https://creativecommons.org/licenses/by/3.0/it/||March 27, 2022|
|5:AGE|DCIS_INDDEMOG1_28032022142732546.csv|The age mean of the population of every italian region in 2019.|Indicatori demografici|I.Stat|http://dati.istat.it/Index.aspx?DataSetCode=DCIS_INDDEMOG1#|https://creativecommons.org/licenses/by/3.0/it/||March 28, 2022|
|6:HOSP|C_17_dataset_68_0_upFileUTF8CODREG.csv|The list of hospital in the italian country in 2019. We grouped and count them by region. Information about Valle d'Aosta, Trentino Alto Adige, Molise and Abruzzo is missing from the original dataset.|Aziende Ospedaliere, Aziende Ospedaliere Universitarie e IRCCS pubblici (anche costituiti in fondazione)|Open Data Ministero della Salute|http://www.dati.salute.gov.it/dataset/aziende_ospedaliere_e_aziende_ospedaliere_universitarie.jsp|https://www.dati.gov.it/content/italian-open-data-license-v20|2019-12-31|2022-05-12|
|7:TEMP|Tavole_dati_meteo_2019_capoluoghi-provincia.xlsx|The tables show information about temperatures and rainfalls in 2019 for every capital of the provinces of italian regions. We only took the informations about the temperatures and we grouped and counted by region.|TEMPERATURA E PRECIPITAZIONE NELLE CITTÀ CAPOLUOGO DI PROVINCIA|Istat|https://www.istat.it/it/files//2020/12/Tavole_dati_meteo_2019_capoluoghi-provincia.xlsx|https://creativecommons.org/licenses/by/4.0/||2022-05-15|


### <a name="#mashup-dataset">3.2 Mashup Dataset</a>

*0:VIR*:
* **Formats**: we decided to publish the data in CSV, GEOJSON and RDF format;
* **Metadata**: we paired the data with RDF metadata in DCAT-AP IT standard;
* **Last update**: 2022-06-02;
* **Description**: for each italian region the dataset contains: region name, region istat code, covid-19 cases at the beginning of the pandemic, covid-19 deaths at the beginning of the pandemic, covid-19 cases at the beginning of the pandemic for every 100.000 people, covid-19 deaths at the beginning of the pandemic for every 100.000 people, pm10 level mean of 2019, the population density in 2019, the average age of the population in 2019, the average temperature in 2019, the number of hospitals in 2019;
* **Methodology**: we manipulated and merged the data coming from the previously described datasets and followed the [italian guidelines for the enhancement of public information assets](https://docs.italia.it/italia/daf/lg-patrimonio-pubblico/it/bozza/index.html), pairing our merged data with the appropriate metadata about both the original and mashup datasets.


## <a name="#data-analysis"> 4. Data Analysis</a>
### <a name="#quality-analysis"> 4.1 Quality Analysis</a>

<!-- Linee guida valorizzazione patrimonio informativo pubblico. Accuracy, coherence, completeness, currentness -->
The initial datasets have been subjected to a quality analysis, following the principles indicated in the "<a href="https://docs.italia.it/italia/daf/lg-patrimonio-pubblico/it/stabile/index.html" rel="nofollow">linee guida nazionali per la valorizzazione del patrimonio informativo pubblico</a>":

<table>
<tr><td></td><td>Completeness</td><td>Accuracy</td><td>Coherence</td><td>Currentness</td></tr>
<tr><td>1:COVID</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr>
<tr><td>2:POP</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr>
<tr><td>3:PM10</td><td>No</td><td>Yes</td><td>Yes</td><td>Yes</td></tr>
<tr><td>4:SUP</td><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td></tr>
<tr><td>5:AGE</td><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td></tr>
<tr><td>6:HOSP</td><td>No</td><td>Yes</td><td>Yes</td><td>No</td></tr>
<tr><td>7:TEMP</td><td>No</td><td>Yes</td><td>Yes</td><td>Yes</td></tr>
</table>

Below we justify our assessments for every dataset:

- 1:COVID - The dataset shows plenty of information divided by date, region code, latitude/longitude, and many other details regarding the patients' conditions, so it's way more than we actually needed to extrapolate. The whole dataset is updated to 2022, but we considered only the period between February and May 2020, because we wanted to focus on the first months of COVID-19's spread.
- 2:POP - Provided by ISTAT, this dataset, like the previous one, is constantly updated, and it doesn't show any issue related to the aspects considered in the table above.
- 3:PM10 - Some information like "city", "city code" and "city population" are missing in almost every line, but the "air quality station name" often compensates for this lack. It's updated to 2022.
- 4:SUP - Updated to the beginning of 2020, this dataset provides the total surface of every italian region, represented in hectares (ha) and square kilometers (kmq).
- 5:AGE - Updated to 2021, the dataset features information about life expectation in Italy, depending on the age group, and the percentage of the same groups in the peninsula.
- 6:HOSP - The dataset covers only a period between 2010 and 2017, besides it lacks data about some regions (the most absent ones result to be Molise, Basilicata, Valle d'Aosta and Trentino-Alto Adige). Anyway, this information doesn't show accuracy or coherence issues.
- 7:TEMP - Updated to 2019, this dataset deals only with provincial capital municipalities and regional capital municipalities (comuni capoluogo di provincia e comuni capoluogo di regione). However, it is exhaustive in every other aspect.

### <a name="#legal-analysis"> 4.2 Legal Analysis</a>

<!-- privacy, license -->
- 1:COVID - Provided by the RNDT (Repertorio Nazionali dei Dati Territoriali), this dataset is subjected to a "<a href="https://creativecommons.org/licenses/by/4.0/deed.it" rel="nofollow">Creative Commons Attribution 4.0 International (CC BY 4.0).</a>" license: those who find it can host, modify and share its information, even for commercial use.
- 2:POP - This dataset, provided by ISTAT, is subjected to a "<a href="http://creativecommons.org/licenses/by/3.0/it/" rel="nofollow">Creative Commons – Attribution – version 3.0.</a>" license. Hence, data is available for reproduction, distribution and broadcasting, without needing permission to create hypertext links to this site itself. The only condition is the source's citation.
- 3:PM10 - This dataset is under an "<a href="https://www.eea.europa.eu/code/gis" rel="nofollow">EEA (European Environment Agency) standard re-use policy</a>": this means that this content is freely available either for commercial and non-commercial use, as long as the source is acknowledged. This is possible thanks to "<a href="https://discomap.eea.europa.eu/Index/" rel="nofollow">Discomap</a>", a website that allows the re-use of map services created by developers and GIS (Geographic Information System) experts.
- 4:SUP - Same as the 2:POP dataset.
- 5:AGE - Same as the 2:POP dataset.
- 6:HOSP - Provided by the website of the Ministry of Health, this dataset is tutelated by an "<a href="https://www.dati.gov.it/iodl/2.0/" rel="nofollow">Italian Open Data Licence 2.0</a>": data under this policy can be freely downloaded, consulted and shared. Besides, users have the possibility to merge this data with further information, in order to obtain a mashup for a product or an application. The only requirement is to mention the source and to include, if possible, a link to the license.
- 7:TEMP - Same as the 2:POP dataset.

### <a name="#technical-analysis"> 4.3 Technical Analysis</a>

<!-- Formats, metadata, uris, provenance -->

* *1:COVID*:
    * **Formats**: [CSV](https://raw.githubusercontent.com/pcm-dpc/COVID-19/master/dati-regioni/dpc-covid19-ita-regioni.csv);

    * **Provenance**: the [COVID-19 Github repository](https://github.com/pcm-dpc/COVID-19) made available by the italian Protezione Civile;

    * **Metadata**: we first found the metadata available in the same repository (this [XML file](https://raw.githubusercontent.com/pcm-dpc/COVID-19/master/metadata/covid-19-monitoraggio.xml)), which was not in the DCAT-AP standard but in the RNDT standard, which is a standard used for territorial data in Italy.


        Then, in this [md file](https://github.com/pcm-dpc/COVID-19/blob/master/dati-andamento-covid19-italia.md) of the description of the dataset we found [this link](https://geodati.gov.it/geoportale/visualizzazione-metadati/scheda-metadati/?uuid=PCM%3ACOVID-19%3A05032020%3A093000) to the metadata in the [geodati.gov.it](http://geodati.gov.it) site. Ignoring the fact that it is not possible to access to the actual RDF file of this metadata, we realized that it was more updated than the github one. So the github XML file was old and not updated metadata.

        Doing more research we found [this manual](https://geodati.gov.it/geoportale/images/struttura/documenti/GeoDCAT-AP_IT-v1.0.pdf), which explains that the territorial data which is also open can be “translated” to the DCAT-AP IT standard through the GeoDCAT-AP IT specific. And that the version of the metadata in the DCAT-AP IT standard could be found at [dati.gov.it](http://dati.gov.it).

        So we searched for the dataset in [dati.gov.it](http://dati.gov.it) catalogue and we found [this](https://www.dati.gov.it/view-dataset/dataset?id=327cbe0a-4737-4e2c-9567-c7d90f69570b), once again it was not possible to access the actual metadata file in RDF. Browsing the site more carefully we found [this page](https://dati.gov.it/elenco-harvest-sources) and  finally found the [download URL](https://geodati.gov.it/geodcat-ap_it/index.php?outputTransformation=dcatap_it&inputFormat=CSW&outputFormat=XML&src=request%3DGetRecords%26service%3DCSW%26version%3D2.0.2%26resultType%3Dresults%26outputSchema%3Dhttp%3A%2F%2Fwww.isotc211.org%2F2005%2Fgmd%26outputFormat%3Dapplication%2Fxml%26typeNames%3Dcsw%3ARecord%26elementSetName%3Dfull%26constraintLanguage%3DFilter%26constraint_language_version%3D1.1.0%26startPosition%3D1%26maxRecords%3D6000%26Constraint%3D%3CFilter%3E%3CPropertyIsLike%20wildCard%3D%22*%22%20singleChar%3D%22_%22%20escapeChar%3D%22%2F%22%3E%3CPropertyName%3EOpenData%3C%2FPropertyName%3E%3CLiteral%3Etrue%3C%2FLiteral%3E%3C%2FPropertyIsLike%3E%3C%2FFilter%3E) of the RDF metadata of all the datasets in the [geodati.gov.it](http://geodati.gov.it) catalogue, including the COVID-19 one.

        Concluding, finding the right metadata for a government dataset should not be this complicated and long search and it should have been made available in the Github repository;

* *2:POP*:

    * **Formats**: Excel, CSV, PC-Axis, SDMX. There is no real download URI for any of the formats;

    * **Provenance**: [I.Stat](http://dati.istat.it), the ISTAT database;

    * **Metadata**: there is some [metadata](http://dati.istat.it/OECDStat_Metadata/ShowMetadata.ashx?Dataset=DCIS_POPORESBIL1&Lang=it) next the data presented in the tool, but it follows no official standard. So we made it ourselves, gathering information from the ISTAT site and following the DCAT-AP IT standard;

* *3:PM10*:

    * **Formats**: CSV, TSV, JSON. There is no real download URI for any format;
    * **Provenance**: [Air Quality e-Reporting](https://www.eea.europa.eu/data-and-maps/data/aqereporting-9) by the European Environment Agency;
    * **Metadata**: there is some [metadata](https://www.eea.europa.eu/data-and-maps/data/aqereporting-9) but it doesn’t follow the DCAT-AP standard and there is no download URL. So we decided to translate the information in the DCAT-AP IT standard;

* *4:SUP*:

    * **Formats**: Excel, CSV, PC-Axis, SDMX. There is no real download URI for any format;

    * **Provenance**: [I.Stat](http://dati.istat.it), the ISTAT database;

    * **Metadata**: there is some [metadata](http://dati.istat.it/OECDStat_Metadata/ShowMetadata.ashx?Dataset=DCIS_POPORESBIL1&Lang=it) next the data presented in the tool, but it follows no official standard. So we made it ourselves, gathering information from the ISTAT site and following the DCAT-AP IT standard;

* *5:AGE*:

    * **Formats**: Excel, CSV, PC-Axis, SDMX. There is no real download URI for any format;

    * **Provenance**: [I.Stat](http://dati.istat.it), the ISTAT database;

    * **Metadata**: there is some [metadata](http://dati.istat.it/OECDStat_Metadata/ShowMetadata.ashx?Dataset=DCIS_POPORESBIL1&Lang=it) next the data presented in the tool, but it follows no official standard. So we made it ourselves, gathering information from the ISTAT site and following the DCAT-AP IT standard;

* *6:HOSP*:

    * **Formats**: [CSV](https://www.dati.salute.gov.it/imgs/C_17_dataset_68_0_upFile.csv);

    * **Provenance**: the [Open Data Ministero della Salute](http://www.dati.salute.gov.it/dataset/aziende_ospedaliere_e_aziende_ospedaliere_universitarie.jsp) catalogue site;

    * **Metadata**: we found the metadata through the same way that we used for the 1:COVID dataset: in this [dati.gov.it page](https://dati.gov.it/elenco-harvest-sources), where we found [this link](http://www.dati.salute.gov.it/imgs/C_17_paginaDataset_10_0_file.rdf) that contained the RDF metadata in the DCAT-AP IT standard for the catalogue and the dataset that we used;

* *7:TEMP*:

    * **Formats**: [XLSX](https://www.istat.it/it/files//2020/12/Tavole_dati_meteo_2019_capoluoghi-provincia.xlsx);

    * **Provenance**: in this [Istat archive page](https://www.istat.it/it/archivio/251803);

    * **Metadata**: there is no RDF metadata, just this pdfs file: [tables index](https://www.istat.it/it/files//2020/12/Indice-delle-tavole-statistiche_Dati-meteoclimatici_Anno2019.pdf), [methodology note](https://www.istat.it/it/files//2020/12/Nota-metodologica_Dati-meteoclimatici_capoluoghi-provincia_Anno2019.pdf), [glossary](https://www.istat.it/it/files//2020/12/Glossario_Dati-meteoclimatici_capoluoghi-provincia_Anno2019.pdf). So we made it ourselves, gathering information from the ISTAT site and following the DCAT-AP IT standard.


### <a name="#sustainability"> 4.4 Sustainability</a>

The Virulence datasets contains informations concerning the factors that could have impacted the first wave of the COVID-19 pandemic in the italian regions. The catalog was created for the Open Access and Digital Ethics course at the University of Bologna and will not be actively mantained in the future.
But all of our datasets and scripts are openly available with the CC-BY-4.0 license here on Github to be used, reproduced and updated.

## <a name="#website-and-data-visualization"> 5. Website and Data Visualization</a>

In this section we present how we decided to visualize the data and metadata that compose our project, and the external resources used to do so.

Some libraries that we used throughout the whole developing of the website process:

- [Bootstrap](https://getbootstrap.com) 5, the world’s most popular front-end open source toolkit;
- [jQuery](https://jquery.com), a JavaScript library designed to simplify HTML DOM tree traversal and manipulation, event handling, and more;
- [FontAwesome](https://fontawesome.com), Internet's icon library and toolkit;
- [pandas](https://pandas.pydata.org), a fast, powerful, flexible and easy to use open source data analysis and manipulation tool for [Python](https://www.python.org/);
- [rdflib](https://rdflib.readthedocs.io/en/stable/), a pure Python package for working with [RDF](http://www.w3.org/RDF/);
- [urllib](https://docs.python.org/3/library/urllib.html), a package that collects several modules for working with URLs.

We decided to visually represent the data we gathered in a Visualization page. There, the user can explore the datasets with an interactive map and graph.

For the Map section we used the following libraries and data:

- [Leaflet](https://leafletjs.com/SlavaUkraini/index.html), an open-source JavaScript library for mobile-friendly interactive maps, for the map interactions;
- [OpenStreetMap](https://www.openstreetmap.org/copyright), for the map data;
- [Mapbox](https://www.mapbox.com), for the map style;
- Openpolis geojson-italy repository, in particular the [geojson file](https://github.com/openpolis/geojson-italy/blob/master/geojson/limits_IT_regions.geojson) of the italian regions, based on [ISTAT data](https://www.istat.it/it/archivio/222527) (both under [CC BY 4.0 license](https://github.com/openpolis/geojson-italy/blob/master/LICENSE));
- we loosely followed [this](https://leafletjs.com/SlavaUkraini/examples/choropleth/) Leaflet tutorial.

For the Graph section we used [Chart.js](https://www.chartjs.org), a library for simple, clean and engaging HTML5 based JavaScript charts.

## <a name="#conclusion"> 6. Conclusion</a>
It's been difficult to try our hand at this field, since many different factors needed to be considered in order to have even a vague idea of ​​the work done by the italian public authorities in the last 2 years. On the other side, having so much material available made the research easier and challenging. It wasn't always possible to obtain exhaustive details about metadata, while datasets needed a bit of maintenance before their actual use. Nonetheless, the website is able to provide a broad vision of the Italian situation between 2019 and 2020. Although certainly perfectible, the project has been completed in full compliance with web standards and the intellectual property of data, and we are quite happy and proud of the result.