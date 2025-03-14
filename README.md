![Version](https://img.shields.io/github/v/release/DCMLab/kleine_geistliche_konzerte?display_name=tag)
[![DOI](https://zenodo.org/badge/199447268.svg)](https://doi.org/10.5281/zenodo.14997003)
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/kleine_geistliche_konzerte)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/kleine_geistliche_konzerte](https://github.com/DCMLab/kleine_geistliche_konzerte) and the corresponding
* documentation page [https://dcmlab.github.io/kleine_geistliche_konzerte](https://dcmlab.github.io/kleine_geistliche_konzerte)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/kleine_geistliche_konzerte/introduction).

# Heinrich Schütz – Kleine Geistliche Konzerte (A corpus of annotated scores)

These "Small Sacred Concertos" are not virtuosic solo instrumental pieces with orchestral support like most concertos we
know. Rather, in early-seventeenth-century repertoire, "Concerto" means a short piece of indeterminate form for some
combination of voices and instruments: a mixture of contrasting timbres in concert. Schütz, whose music arguably sits
directly on the cusp of Renaissance and Baroque, found an immense variety of musical possibilities in this genre,
incorporating everything from virtuosic solo arias and imitative modal counterpoint to dramatic choruses. This is some
of the oldest music represented in the DCML corpora, so the harmonic successions found in the annotations do not often
reflect what we would today think of as conventional tonal syntax. There may be significant potential for future
research in quantitative investigation of the ways expected chord succession changed in the century or so after these
pieces were completed.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/kleine_geistliche_konzerte/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [kleine_geistliche_konzerte.zip](https://github.com/DCMLab/kleine_geistliche_konzerte/releases/latest/download/kleine_geistliche_konzerte.zip)
  * [kleine_geistliche_konzerte.datapackage.json](https://github.com/DCMLab/kleine_geistliche_konzerte/releases/latest/download/kleine_geistliche_konzerte.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/kleine_geistliche_konzerte.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first concerto, Eile mich, Gott, zu erretten, of the first volume, Op. 8 has the following files:

* `MS3/op08n01swv282_Eile_mich,_Gott,_zu_erretten.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/op08n01swv282_Eile_mich,_Gott,_zu_erretten.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/op08n01swv282_Eile_mich,_Gott,_zu_erretten.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/op08n01swv282_Eile_mich,_Gott,_zu_erretten.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/op08n01swv282_Eile_mich,_Gott,_zu_erretten.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/op08n01swv282_Eile_mich,_Gott,_zu_erretten.harmonies.tsv")
notes = ms3.load_tsv("notes/op08n01swv282_Eile_mich,_Gott,_zu_erretten.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/kleine_geistliche_konzerte/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/kleine_geistliche_konzerte/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). Heinrich Schütz – Kleine Geistliche Konzerte (A corpus of annotated scores) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.14997003

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)


## Pieces

### Volume 1

|no |                       title                       |SWV|voices|registers|
|--:|---------------------------------------------------|--:|-----:|---------|
|  1|Eile mich, Gott, zu erretten                       |282|     1|S        |
|  2|Bringt her dem Herren                              |283|     1|S        |
|  3|Ich danke dem Herrn von ganzem Herzen              |284|     1|A        |
|  4|O süsser, o freundlicher                           |285|     1|T        |
|  5|Der Herr ist gross                                 |286|     2|SS       |
|  6|O lieber Herre Gott                                |287|     2|SS       |
|  7|Ihr Heiligen, lobsinget dem Herren                 |288|     2|SS       |
|  8|Erhöre mich, wenn ich rufe                         |289|     2|SS       |
|  9|Wohl dem, der nicht wandelt im Rat der Gottlosen   |290|     2|SA       |
| 10|Schaffe in mir, Gott, ein reines Herz              |291|     2|ST       |
| 11|Der Herr schauet vom Himmel auf der Menschen Kinder|292|     2|SB       |
| 12|Lobet den Herren, der zu Zion wohnet               |293|     2|AA       |
| 13|Eins bitte ich vom Herren                          |294|     2|TT       |
| 14|O hilf, Christe Gottes Sohn                        |295|     2|TT       |
| 15|Fürchte dich nicht                                 |296|     2|BB       |
| 16|O Herr hilf                                        |297|     3|SST      |
| 17|Das Blut Jesu Christi                              |298|     3|SSB      |
| 18|Die Gottseligkeit ist zu allen Dingen nütz         |299|     3|SSB      |
| 19|Himmel und Erde vergehen                           |300|     3|BBB      |
| 20|Nun komm der Heiden Heiland                        |301|     4|SSBB     |
| 21|Ein Kind ist uns geboren                           |302|     4|SATB     |
| 22|Wir glauben all an einen Gott                      |303|     4|SSTB     |
| 23|Siehe, mein Fürsprecher im Himmel                  |304|     4|SATB     |
| 24|Ich hab mein Sach Gott heimgestellt                |305|     5|SSATB    |

### Volume 2

|no |                    title                    |SWV|voices|   registers   |
|--:|---------------------------------------------|--:|-----:|---------------|
|  1|Ich will den Herren loben allezeit           |306|     1|S              |
|  2|Was hast du verwirket                        |307|     1|A              |
|  3|O Jesu, nomen dulce                          |308|     1|T              |
|  4|O misericordissime Jesu                      |309|     1|T              |
|  5|Ich liege und schlafe                        |310|     1|B              |
|  6|Habe deine Lust an dem Herren                |311|     2|SS             |
|  7|Herr, ich hoffe darauf                       |312|     2|SS             |
|  8|Bone Jesu, verbum Patris                     |313|     2|SS             |
|  9|Verbum caro factum                           |314|     2|SS             |
| 10|Hodie Christus natus est                     |315|     2|ST             |
| 11|Wann unsre Augen schlafen ein                |316|     2|SB             |
| 12|Meister, wir haben die ganze Nacht gearbeitet|317|     2|TT             |
| 13|Die Furcht des Herren                        |318|     2|TT             |
| 14|Ich beuge meine Knie gegen dem Vater         |319|     2|BB             |
| 15|Ich bin jung gewesen und bin alt worden      |320|     2|BB             |
| 16|Herr, wenn ich nur dich                      |321|     3|SST            |
| 17|Rorate, rorate coeli                         |322|     3|SSB            |
| 18|Joseph, du Sohn David                        |323|     3|SSB            |
| 19|Ich bin die Auferstehung                     |324|     3|TTB            |
| 20|Die Seele Christi heilige mich               |325|     3|ATB            |
| 21|Ich ruf zu dir, Herr Jesu Christ             |326|     4|SSSB           |
| 22|Allein Gott in der Höh                       |327|     4|SSTT           |
| 23|Veni, Sancte Spiritus                        |328|     4|SSTT           |
| 24|Ist Gott für uns                             |329|     4|SATB           |
| 25|Wer will uns scheiden von der Liebe Gottes   |330|     4|SATB           |
| 26|Die Stimm des Herren gehet auf den Wassern   |331|     4|SATB           |
| 27|Jubilate Deo omnis terra                     |332|     4|SATB           |
| 28|Sei gegrüßet, Maria                          |333|     5|SSATB + SA soli|
| 29|Ave Maria, qualis est                        |334|     5|SSATB          |
| 30|Was betrübst du dich, meine Seele            |335|     5|SSATB          |
| 31|Quemadmodum desiderat cervus                 |336|     5|SATTB          |
| 32|Aufer immensam                               |337|     5|SATTB          |


## Scores

The files are taken from http://www1.cpdl.org/wiki/index.php/Kleine_geistliche_Konzerte_I,_Op._8_(Heinrich_Sch%C3%BCtz) and http://www1.cpdl.org/wiki/index.php/Kleine_geistliche_Konzerte_II,_Op._9_(Heinrich_Sch%C3%BCtz). Notes by transcriber James Gibb:
> Transcribed from the Spitta edition on IMSLP. Clefs modernised and note values halved in the triple-time sections. Musica ficta absorbed into staves.

CAPX files have been renamed and converted to MSCX using MuseScore 2.3.2

## File naming convention

```regexp 
op(?P<op>0[89])         # op 08 or 09
n(?P<number>\d{2})      # two-digit number between 1 and 32
swv(?P<catalog>\d{3})   # three-digit catalog number 282-337
_(?P<title>\w+)         # title
```

## Overview
|                            file_name                            |measures|labels|standard| annotators |
|-----------------------------------------------------------------|-------:|-----:|--------|------------|
|op08n01swv282_Eile_mich,_Gott,_zu_erretten                       |      68|    84|2.1.1   |Adrian Nagel|
|op08n02swv283_Bringt_her_dem_Herren                              |      89|   176|2.1.1   |Adrian Nagel|
|op08n03swv284_Ich_danke_dem_Herrn_von_ganzem_Herzen              |     114|   237|2.1.1   |Adrian Nagel|
|op08n04swv285_O_süsser,_o_freundlicher                           |     107|   193|2.1.1   |Adrian Nagel|
|op08n05swv286_Der_Herr_ist_gross                                 |      74|   139|2.1.1   |Adrian Nagel|
|op08n06swv287_O_lieber_Herre_Gott                                |      96|   199|2.1.1   |Adrian Nagel|
|op08n07swv288_Ihr_Heiligen,_lobsinget_dem_Herren                 |      81|   145|2.1.1   |Adrian Nagel|
|op08n08swv289_Erhöre_mich,_wenn_ich_rufe                         |      65|   128|2.1.1   |Adrian Nagel|
|op08n09swv290_Wohl_dem,_der_nicht_wandelt_im_Rat_der_Gottlosen   |     134|   242|2.1.1   |Adrian Nagel|
|op08n10swv291_Schaffe_in_mir,_Gott,_ein_reines_Herz              |      39|   104|2.1.1   |Adrian Nagel|
|op08n11swv292_Der_Herr_schauet_vom_Himmel_auf_der_Menschen_Kinder|      81|   135|2.1.1   |Adrian Nagel|
|op08n12swv293_Lobet_den_Herren,_der_zu_Zion_wohnet               |      80|   137|2.1.1   |Adrian Nagel|
|op08n13swv294_Eins_bitte_ich_vom_Herren                          |      86|   165|2.1.1   |Adrian Nagel|
|op08n14swv295_O_hilf,_Christe_Gottes_Sohn                        |      81|   121|2.1.1   |Adrian Nagel|
|op08n15swv296_Fürchte_dich_nicht                                 |      77|   167|2.1.1   |Adrian Nagel|
|op08n16swv297_O_Herr_hilf                                        |      61|   170|2.1.1   |Adrian Nagel|
|op08n17swv298_Das_Blut_Jesu_Christi                              |      38|     0|2.1.1   |Adrian Nagel|
|op08n18swv299_Die_Gottseligkeit_ist_zu_allen_Dingen_nütz         |      51|    73|2.1.1   |Adrian Nagel|
|op08n19swv300_Himmel_und_Erde_vergehen                           |      54|    91|2.1.1   |Adrian Nagel|
|op08n20swv301_Nun_komm_der_Heiden_Heiland                        |      90|   165|2.1.1   |Adrian Nagel|
|op08n21swv302_Ein_Kind_ist_uns_geboren                           |     125|   276|2.1.1   |Adrian Nagel|
|op08n22swv303_Wir_glauben_all_an_einen_Gott                      |     120|   281|2.1.1   |Adrian Nagel|
|op08n23swv304_Siehe,_mein_Fürsprecher_im_Himmel                  |      93|   172|2.1.1   |Adrian Nagel|
|op08n24swv305_Ich_hab_mein_Sach_Gott_heimgestellt                |     299|   573|2.1.1   |Adrian Nagel|
|op09n01swv306_Ich_will_den_Herren_loben_allezeit                 |      85|   218|2.1.1   |Adrian Nagel|
|op09n02swv307_Was_hast_du_verwirket                              |      82|   184|2.1.1   |Adrian Nagel|
|op09n03swv308_O_Jesu,_nomen_dulce                                |      66|   149|2.1.1   |Adrian Nagel|
|op09n04swv309_O_misericordissime_Jesu                            |      92|   181|2.1.1   |Adrian Nagel|
|op09n05swv310_Ich_liege_und_schlafe                              |      86|   179|2.1.1   |Adrian Nagel|
|op09n06swv311_Habe_deine_Lust_an_dem_Herren                      |     141|   351|2.1.1   |Adrian Nagel|
|op09n07swv312_Herr,_ich_hoffe_darauf                             |      78|   167|2.1.1   |Adrian Nagel|
|op09n08swv313_Bone_Jesu,_verbum_Patris                           |     124|   268|2.1.1   |Adrian Nagel|
|op09n09swv314_Verbum_caro_factum                                 |     121|   260|2.1.1   |Adrian Nagel|
|op09n10swv315_Hodie_Christus_natus_est                           |      99|   241|2.1.1   |Adrian Nagel|
|op09n11swv316_Wann_unsre_Augen_schlafen_ein                      |      76|   170|2.1.1   |Adrian Nagel|
|op09n12swv317_Meister,_wir_haben_die_ganze_Nacht_gearbeitet      |      46|    86|2.1.1   |Adrian Nagel|
|op09n13swv318_Die_Furcht_des_Herren                              |      66|   118|2.1.1   |Adrian Nagel|
|op09n14swv319_Ich_beuge_meine_Knie_gegen_dem_Vater               |      95|   215|2.1.1   |Adrian Nagel|
|op09n15swv320_Ich_bin_jung_gewesen_und_bin_alt_worden            |      65|   150|2.1.1   |Adrian Nagel|
|op09n16swv321_Herr,_wenn_ich_nur_dich                            |      78|   187|2.1.1   |Adrian Nagel|
|op09n17swv322_Rorate,_rorate_coeli                               |      64|   190|2.1.1   |Adrian Nagel|
|op09n18swv323_Joseph,_du_Sohn_David                              |      77|   170|2.1.1   |Adrian Nagel|
|op09n19swv324_Ich_bin_die_Auferstehung                           |      99|   234|2.1.1   |Adrian Nagel|
|op09n20swv325_Die_Seele_Christi_heilige_mich                     |     114|   217|2.1.1   |Adrian Nagel|
|op09n21swv326_Ich_ruf_zu_dir,_Herr_Jesu_Christ                   |      85|   180|2.1.1   |Adrian Nagel|
|op09n22swv327_Allein_Gott_in_der_Höh                             |     148|   352|2.1.1   |Adrian Nagel|
|op09n23swv328_Veni,_Sancte_Spiritus                              |     122|   259|2.1.1   |Adrian Nagel|
|op09n24swv329_Ist_Gott_für_uns                                   |      76|   192|2.1.1   |Adrian Nagel|
|op09n25swv330_Wer_will_uns_scheiden_von_der_Liebe_Gottes         |      79|   178|2.1.1   |Adrian Nagel|
|op09n26swv331_Die_Stimm_des_Herren_gehet_auf_den_Wassern         |     138|   237|2.1.1   |Adrian Nagel|
|op09n27swv332_Jubilate_Deo_omnis_terra                           |     130|   351|2.1.1   |Adrian Nagel|
|op09n28swv333_Sei_gegrüßet,_Maria                                |     220|   376|2.1.1   |Adrian Nagel|
|op09n29swv334_Ave_Maria,_qualis_est                              |     215|   376|2.1.1   |Adrian Nagel|
|op09n30swv335_Was_betrübst_du_dich,_meine_Seele                  |      87|   194|2.1.1   |Adrian Nagel|
|op09n31swv336_Quemadmodum_desiderat_cervus                       |     189|   478|2.1.1   |Adrian Nagel|
|op09n32swv337_Aufer_immensam                                     |     165|   428|2.1.1   |Adrian Nagel|


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
