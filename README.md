# NapierOne: A Modern Mixed File Data Set

![NapierOne Title](img/NapierOne-title.jpg)

## Summary
A modern cybersecurity mixed file data set called ‘NapierOne’ is presented, primarily aimed at, but not limited to, ransomware detection and forensic analysis. NapierOne was designed to address the known deficiency in research reproducibility and improve consistency by facilitating research replication and repeatability. The methodology used in the creation of this data set is also described in detail. The data set was inspired by the Govdocs1 data set and it is intended that ‘NapierOne’ be used as a complement to this original data set.

An investigation was performed with the goal of determining the common files types currently in use. No specific research was found that explicitly provided this information, so an alternative consensus approach was employed. This involved combining the findings from multiple sources of file type usage into an overall ranked list. After which 5,000 real-world example files were gathered, and a specific data subset created, for each of the common file types identified. In some circumstances, multiple data subsets were created for a specific file type, each subset representing a specific characteristic for that file type. For example, there are multiple data subsets for the ZIP file type with each subset containing examples of a specific compression method. Ransomware execution tends to produce files that have high entropy, so examples of file types that naturally have this attribute are also present. The resulting entire data set comprises of more than 90 separate data subsets divided between 44 distinct file types, resulting in over 450,000 unique files in total.

## Data Sources
### File Selection
An important aspect of building a representative data set relates to file type usage and popularity. It is known that Google gathers statistics on file types while it performs its website indexing searches. However, the statistics are only gathered on a limited number of file types (https://
support.google.com/webmasters/answer/35287?hl=en http://
googlegsa.github.io/adaptor/index.html). 
While it was not possible to discover a definitive ranked list of files types currently in use, it was decided to adopt a consensus approach. This involved querying various sources of possible usage information and gathering approximate lists of up to their Top 40 file types. These lists were then compared and aggregated with the lists gathered from other sources, resulting in a fair representation of what are currently popular file types are in use today. The list produced is not proposed as definitive but rather a best guess consensus.
A list of the sources for file type usage information is discussed below. The alphabetical identification used for each data source is then repeated in the data set description shown in Table~\ref{tab:data-set-details}.

***A - VirusTotal*** Statistics taken from file submissions to this website~\cite{VirusTotal2019} during that past 12 months were recorded.

***B - W3Techs*** The website (http://w3techs.com/technologies/overview/) provides information about the usage of various types of technologies on the web. Statistics relating to the most popular images types were gathered from here.

***C - Search Engine Statistics*** Searches were performed for more than 100 different candidate file types. Search trends and statistics were also analysed and recorded in an attempt to identify the popularity of the file type. Although Google only index certain file types (https://
support.google.com/webmasters/answer/35287?hl=en), their justification for doing so could also be considered a reason to include these files types in the data set.

***D - File Preservation*** There exists research into the investigation of digital data preservation. One aspect of this research is to identify popular file formats. The findings from this research were also taken into account, as this research identifies certain files as being important and have the potential for remaining in active use for the foreseeable future.

***E - MIME Type Statistics*** A MIME type (https://www.doi.org/10.17487/RFC2046 https://www.doi.org/10.17487/RFC6838) is a standard label used to indicate the nature and format of a document, file, or assortment of bytes. It is mainly used in Internet-based technology so that software can know how to handle the data. It serves the same purpose on the Internet that file extensions do on Microsoft Windows. When crawling the internet, these labels may be recorded and the frequency of them can be used to identify the popularity of file formats. Statistics have thus been gained from the WayBackMachine (https://archive.org/web/) and for WebCrawler (https://commoncrawl.github.io/cc-crawl-statistics/plots/mimetypes), who record and publish monthly statistics on MIME types that are encountered.

***F - fileinfo.com*** This website (https://fileinfo.com/) performs research into file types and regularly publishes ranked lists of popular file types. These popularity lists are calculated from both the requests that the website receives and general web traffic analysis.

***G - Ransomware Targets*** One of the anticipated initial applications of this data set will be in the field of ransomware research. For the data set to be useful in this research, it should contain a good selection of file types that are regularly targeted by ransomware ( https://doi.org/10.1016/j.cose.2018.01.001 https://doi.org/10.1007/s00500-018-3257-z https://doi.ieeecomputersociety.org/10.
1109/SANER.2017.7884603), typical examples of which being DOCX and XLSX. This additional criterion did not impact the main goal of listing common file types as these file types appear in multiple lists.

***H - High Entropy*** As the data set will initially be used in ransomware detection testing, it was considered a benefit for the data set to contain files that had this attribute. One technique used to identify files that have been affected by ransomware is to test the file's entropy so including files that normally have this attribute, such as archive files, would provide realistic challenges in ransomware identification. This secondary consideration does not impact the overall goal of generating the file type popularity list.

***I - File-extension*** These are others websites (https://www.file-extension.info/top  https://www.file-extension.org/ )specialising in file type research and regularly publish file type usage statistics.

***J - OS Installation*** File type count statistics were gathered from clean windows installations (XP 2003 SP1, Vista 2006 and Windows 10 20H2) as well as four clean 64Bit Linux installations (MX Linux 19.4, Debian 5.9.1, Ubuntu 18.04.1, and Ubuntu 20.10).

***K - Govdocs1*** Inclusion of the file types in the original Govdocs1 data set (https:
//digitalcorpora.org/corpora/files) were also taken into consideration when deciding if they should appear in this data set. However, the actual files being sourced from elsewhere.

The results for all the sources were then sorted by popularity and aggregated into a list of approximately 40 file types. To encourage consensus, the file types needed to appear in at least two lists before they were considered in the final results. The following list describes the file types that were identified as being popular using the infoirmation gathered from the sources above.


| &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; |
| ------ | ------ | ------ | ------ | ------ | 
| APK    | BIN    | BMP    | CSS    | CSV    |     
| DOC    | DOCX   | DWG    | ELF    | EPS    |
| EPUB   | EXE    | GIF    | GZIP   | HTML   | 
| ICS    | JS     | JPG    | JSON   | MKV    | 
| MP3    | MP4    | ODS    | OXPS   | PDF    | 
| PNG    | PPT    | PPTX   | PS1    | RAR    |
| SVG    | TAR    | TIF    | TXT    | WEBP   | 
| XLS    | XLSX   | XML    | ZIP    | ZLIB   | 
|7Zip|||||




### Sources ###
The contents of the ***NapierOne*** new data set were generated in the following ways:
- Examples of files using the most commonly used document types such as DOC, DOCX, PDF, PPT, PPTX, XLS, and XLS  were be gathered from the UK government domain, ***gov.uk***. Files collected from this domain are covered by the 'Open Government License agreement for Public Sector Information' (http://www.nationalarchives.gov.uk/doc/open-government-licence/
version/3). This agreement allows for the free distribution of the documents as long as they are accompanied by the correct attribution.
- Image files in the TIF format were taken from the RAISE data set (https://doi.org/10.1145/2713168.2713194). This data set permits redistribution of its contents as long as it is accompanied by the correct attribution. Subsequent image file type data subsets, for example, BMP, EPS, GIF, ICO, JPG, PNG, SVG and WEBP were generated from this original TIF data set.
- Archive data subsets were generated using files from the documents subset.
- Audio files were gathered from the Free Music Archive (https://arxiv.org/abs/1612.01840). Its license permits free and unrestricted usage and distribution.
- Video files, in MP4, format, were gathered from the Kinetics-700 data set (https://arxiv.org/abs/2010.10864). Its license also allows free usage and distribution when using the correct attribution. Other video data sets in different formats were generated by transcoding this MP4 data set.
- Examples of files in the EPUB format were taken from Project Gutenberg (https://www.gutenberg.org), which is an online library of free eBooks.

A graphical representtaion of the dataset sources is shown below:

![Data Sources](img/sources3.png)


| File Type  | Size (MB) |  Files #  |  Min Size (KB)  |  Max Size (KB)  |  Average Size (KB)  |  σ (KB)  | Sub classifications | SubSub classifications | A | B | C | D | E | F | G | H | I | J | K |
|------------|-----------|-----------|-----------------|-----------------|---------------------|----------|---------------------|------------------------|---|---|---|---|---|---|---|---|---|---|---|
| APK        |  9,310    |  5,000    |  14             |  3,000          |  2,001              |  778     | APK                 | -                      | ✔ |   |   |   |   | ✔ |   |   | ✔ |   |   |
| BIN        |  3,346    |  5,000    |  10             |  164,411        |  669                |  5,512   | BIN                 | -                      |   |   |   |   |   | ✔ |   |   | ✔ | ✔ |   |
| BMP        |  208,000  |  5,000    |  18,099         |  48,306         |  44,845             |  5,711   | BMP                 | -                      |   | ✔ |   | ✔ |   |   | ✔ |   |   |   | ✔ |
| CSS        |  355      |  5,000    |  1              |  4,698          |  74                 |  234     | CSS                 | -                      |   |   |   | ✔ | ✔ |   |   |   |   | ✔ |   |
| CSV        |  3,503    |  5,000    | 1               |  192,472        |  701                |  7,637   | CSV                 | -                      |   |   |   | ✔ | ✔ | ✔ |   |   |   |   | ✔ |
| DLL        |  3,130    |  5,000    | 1               |  155,445        |  673                |  4,219   | DLL                 | -                      | ✔ |   |   |   |   |   |   |   | ✔ | ✔ | ✔ |
| DOC        |  1,320    |  5,000    |  20             |  13,822         |  290                |  763     | DOC                 | -                      | ✔ |   | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |   | ✔ |
|            |  1,320    |  5,000    |  20             |  13,822         |  282                |  746     | DOC-NOMAGIC         |                        | ✔ |   | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |   | ✔ |
|            |  1,170    |  5,000    |  23             |  13,411         |  251                |  649     | DOC-PASSWORD        | -                      | ✔ |   | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |   | ✔ |
| DOCX       |  1,420    |  5,000    |  11             |  14,580         |  303                |  866     | DOCX                | -                      | ✔ |   | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |   | ✔ |
|            |  1,420    |  5,000    |  11             |  14,580         |  303                |  866     | DOCX-NOMAGIC        | -                      | ✔ |   | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |   | ✔ |
|            |  1,590    |  5,000    |  18             |  14,707         |  311                |  872     | DOCX-PASSWORD       | -                      | ✔ |   | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |   | ✔ |
| DWG        |  9,720    |  5,000    |  1,023          |  6,447          |  2,088              |  714     | DWG                 | -                      |   |   | ✔ |   |   |   |   |   | ✔ |   |   |
| ELF        |  1,560    |  5,000    |  1              |  130,513        |  312                |  3,064   | ELF                 | -                      | ✔ |   |   |   |   |   |   |   | ✔ | ✔ |   |
| EPS        |  26,400   |  5,000    |  2,293          |  6,121          |  5,683              |  724     | EPS                 | -                      |   |   |   |   |   | ✔ |   |   |   |   | ✔ |
| EPUB       |  1,170    |  5,000    |  5              |  11,741         |  251                |  318     | EPUB                | -                      |   |   |   | ✔ | ✔ | ✔ |   |   | ✔ |   |   |
| EXE        |  8,950    |  5,000    |  1              |  243,770        |  1,924              |  10,685  | EXE                 |                        | ✔ |   |   |   |   | ✔ |   |   |   | ✔ | ✔ |
| GIF        |  3,030    |  5,000    |  108            |  1,172          |  650                |  141     | GIF                 | -                      |   | ✔ |   | ✔ | ✔ |   | ✔ |   |   | ✔ | ✔ |
| GZIP       |  18,200   |  5,000    |  6              |  59,749         |  3,909              |  4,858   | GZIP                | -                      | ✔ |   |   |   | ✔ |   |   | ✔ |   | ✔ | ✔ |
| HTML       |  303      |  5,000    |  1              |  6,804          |  64                 |  174     | HTML                | -                      | ✔ |   | ✔ | ✔ | ✔ |   | ✔ |   |   | ✔ | ✔ |
| ICS        |  16       |  5,000    |  1              |  6,785          |  17                 |  3       | ICS                 | -                      |   |   |   |   | ✔ | ✔ |   |   |   | ✔ |   |
| JAVASCRIPT |  86       |  5,000    |  1              |  6,785          |  17                 |  130     | JAVASCRIPT          | -                      | ✔ |   |   | ✔ | ✔ |   | ✔ |   |   | ✔ | ✔ |
| JPG        |  345      |  5,000    |  1              |  7,445          |  72                 |  318     | JPG-FROM-WEB        | -                      | ✔ | ✔ |   | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
|            |  666      |  5,000    |  47             |  423            |  138                |  36      | QUALITY-01-PERCENT  | -                      | ✔ | ✔ |   | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
|            |  3,220    |  5,000    |  79             |  2,012          |  692                |  308     | QUALITY-25-PERCENT  | -                      | ✔ | ✔ |   | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
|            |  5,270    |  5,000    |  129            |  2,999          |  1,131              |  448     | QUALITY-50-PERCENT  | -                      | ✔ | ✔ |   | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
|            |  8,380    |  5,000    |  285            |  4,479          |  1,799              |  594     | QUALITY-75-PERCENT  |                        | ✔ | ✔ |   | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
|            |  49,100   |  5,000    |  1,797          |  22,418         |  10,564             |  2,533   | QUALITY-100-PERCENT | -                      | ✔ | ✔ |   | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
| JSON       |  202      |  5,000    |  1              |  70,217         |  137                |  2,439   | JSON                |                        |   |   |   |   | ✔ | ✔ |   |   | ✔ | ✔ |   |
| MKV        |  7,530    |  5,000    |  81             |  6,830          |  1,616              |  906     | MKV                 | -                      |   |   |   |   |   | ✔ |   |   | ✔ |   |   |
| MP3        |  4,650    |  5,000    |  415            |  1,206          |  995                |  230     | MP3                 | -                      |   |   |   | ✔ | ✔ | ✔ | ✔ |   | ✔ |   |   |
| MP4        |  7,540    |  5,000    |  81             |  6,933          |  1,619              |  906     | MP4                 | -                      |   |   |   | ✔ | ✔ | ✔ | ✔ |   | ✔ |   |   |
| ODS        |  1,500    |  5,000    |  9              |  48,620         |  322                |  1,513   | ODS                 | -                      | ✔ |   | ✔ |   | ✔ |   |   |   | ✔ |   |   |
| OXPS       |  1,320    |  5,000    |  20             |  13,822         |  282                |  746     | OXPS                |                        | ✔ |   |   |   | ✔ |   |   |   | ✔ |   |   |
| PDF        |  4,510    |  5,000    |  3              |  56,986         |  968                |  2,799   | PDF                 | -                      | ✔ |   | ✔ | ✔ | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |
|            |  4,510    |  5,000    |  3              |  56,986         |  968                |  2,799   | PDF-NOMAGIC         | -                      | ✔ |   | ✔ | ✔ | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |
|            |  4,220    |  5,000    |  2              |  56,903         |  906                |  2,724   | PDF-PASSWORD        | -                      | ✔ |   | ✔ | ✔ | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |
| PNG        |  175,000  |  5,000    |  10,941         |  47,713         |  37,792             |  5,664   | LOSSLESS            | COMPRESSION-0          | ✔ | ✔ |   | ✔ | ✔ |   |   |   |   | ✔ | ✔ |
|            |  93,900   |  5,000    |  4,155          |  32,767         |  20,181             |  3,792   |                     | COMPRESSION-3          | ✔ | ✔ |   | ✔ | ✔ |   |   |   |   | ✔ | ✔ |
|            |  93,200   |  5,000    |  3,766          |  35,879         |  20,021             |  3,942   |                     | COMPRESSION-5          | ✔ | ✔ |   | ✔ | ✔ |   |   |   |   | ✔ | ✔ |
|            |  90,800   |  5,000    |  3,585          |  35,731         |  19,517             |  3,986   |                     | COMPRESSION-7          | ✔ | ✔ |   | ✔ | ✔ |   |   |   |   | ✔ | ✔ |
|            |  90,000   |  5,000    |  3,428          |  35,731         |  19,517             |  3,986   |                     | COMPRESSION-9          | ✔ | ✔ |   | ✔ | ✔ |   |   |   |   | ✔ | ✔ |
| PPT        |  5,050    |  2,105    |  15             |  20,087         |  2,576              |  3,056   | PPT                 | -                      |   |   | ✔ | ✔ | ✔ |   | ✔ |   |   |   | ✔ |
|            |  5,050    |  2,105    |  15             |  20,057         |  2,576              |  3,056   | PPT-NOMAGIC         | -                      |   |   | ✔ | ✔ | ✔ |   | ✔ |   |   |   | ✔ |
|            |  4,820    |  2,105    |  42             |  20,009         |  2,460              |  2,955   | PPT-PASSWORD        | -                      |   |   | ✔ | ✔ | ✔ |   | ✔ |   |   |   | ✔ |
| PPTX       |  10,300   |  4,215    |  39             |  118,293        |  2,634              |  4,005   | PPTX                | -                      |   |   | ✔ | ✔ | ✔ |   | ✔ |   |   |   | ✔ |
|            |  10,300   |  4,215    |  39             |  118,293        |  2,634              |  4,005   | PPTX-NOMAGIC        | -                      |   |   | ✔ | ✔ | ✔ |   | ✔ |   |   |   | ✔ |
|            |  10,100   |  4,215    |  46             |  119,254        |  2,576              |  3,993   | PPTX-PASSWORD       | -                      |   |   | ✔ | ✔ | ✔ |   | ✔ |   |   |   | ✔ |
| Powershell |  20       |  5,000    |  1              |  459            |  4                  |  12      | PS                  |                        | ✔ |   | ✔ | ✔ | ✔ |   |   |   |   |   | ✔ |
| RANDOM     |  17       |  5,000    |  1              |  2              |  1                  |  0       | PSEUDO              | -                      |   |   |   |   |   |   |   | ✔ |   |   |   |
|            |  17       |  5,000    |  1              |  640            |  1                  |  9       | PURE                | -                      |   |   |   |   |   |   |   | ✔ |   |   |   |
| RAR        |  17,600   |  5,000    |  6              |  59,321         |  3,793              |  4,750   | RAR                 | -                      | ✔ |   |   |   |   | ✔ |   | ✔ | ✔ |   |   |
| SVG        |  122,000  |  5,000    |  4,860          |  48,285         |  26,379             |  5,385   | SVG                 | -                      |   | ✔ | ✔ | ✔ | ✔ |   |   |   |   | ✔ |   |
| TAR        |  20,500   |  5,000    |  20             |  61,542         |  4,421              |  5,339   | TAR                 | -                      |   |   |   |   |   |   |   |   |   |   |   |
| TIF        |  127,000  |  5,000    |  4,149          |  42,664         |  22,900             |  5,019   | TIF                 | -                      |   |   |   | ✔ |   | ✔ |   |   |   |   | ✔ |
|            |  8,490    |  5,000    |  470            |  3,423          |  1,823              |  466     | TIF-RESIZED         | -                      |   |   |   | ✔ |   | ✔ |   |   |   |   | ✔ |
| TXT        |  1        |  5,000    |  1              |  231,094        |  5,109              |  28,617  | TXT                 |                        | ✔ |   | ✔ | ✔ | ✔ | ✔ | ✔ |   |   | ✔ | ✔ |
| WEBP       |  440      |  5,000    |  1              |  7,445          |  72                 |  318     | WEBP-FROMWEB        |                        |   | ✔ |   |   |   |   |   | ✔ |   |   |   |
|            |  5,650    |  5,000    |  344            |  2,460          |  1,214              |  281     | LOSSLESS            | COMPRESSION-0          |   | ✔ |   |   |   |   |   | ✔ |   |   |   |
|            |  5,540    |  5,000    |  336            |  2,450          |  1,188              |  280     |                     | COMPRESSION-2          |   | ✔ |   |   |   |   |   | ✔ |   |   |   |
|            |  5,540    |  5,000    |  327            |  2,450          |  1,188              |  281     |                     | COMPRESSION-4          |   | ✔ |   |   |   |   |   | ✔ |   |   |   |
|            |  5,490    |  5,000    |  327            |  2,450          |  1,179              |  280     |                     | COMPRESSION-6          |   | ✔ |   |   |   |   |   | ✔ |   |   |   |
|            |  555      |  5,000    |  9              |  331            |  114                |  56      | 50% QUALITY         | COMPRESSION-0          |   | ✔ |   |   |   |   |   | ✔ |   |   |   |
|            |  511      |  5,000    |  8              |  333            |  105                |  55      |                     | COMPRESSION-2          |   | ✔ |   |   |   |   |   | ✔ |   |   |   |
|            |  451      |  5,000    |  6              |  316            |  93                 |  52      |                     | COMPRESSION-4          |   | ✔ |   |   |   |   |   | ✔ |   |   |   |
|            |  423      |  5,000    |  6              |  310            |  87                 |  50      |                     | COMPRESSION-6          |   | ✔ |   |   |   |   |   | ✔ |   |   |   |
| XLS        |  2,370    |  5,000    |  5              |  55,651         |  509                |  1,632   | XLS                 | -                      |   |   | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |   | ✔ |
|            |  2,370    |  5,000    |  5              |  55,651         |  509                |  1,632   | XLS-NOMAGIC         | -                      |   |   | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |   | ✔ |
|            |  2,420    |  5,000    |  20             |  55,620         |  518                |  1,646   | XLS-PASSWORD        | -                      |   |   | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |   | ✔ |
| XLSX       |  2,660    |  5,000    |  8              |  93,930         |  570                |  2,769   | XLSX                | -                      |   |   | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |   | ✔ |
|            |  2,660    |  5,000    |  8              |  93,930         |  570                |  2,769   | XLSX-NOMAGIC        | -                      |   |   | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |   | ✔ |
|            |  2,700    |  5,000    |  15             |  96,190         |  578                |  2,815   | XLSX-PASSWORD       | -                      |   |   | ✔ | ✔ | ✔ |   | ✔ |   | ✔ |   | ✔ |
| XML        |  320      |  5,000    |  1              |  16,920         |  75                 |  708     | XML                 |                        | ✔ |   | ✔ | ✔ | ✔ |   | ✔ |   | ✔ | ✔ | ✔ |
| ZIP        |  18,200   |  5,000    |  7              |  59,865         |  3,912              |  4,852   | BZIP2               | -                      | ✔ |   |   |   | ✔ | ✔ | ✔ | ✔ |   |   | ✔ |
|            |  18,200   |  5,000    |  6              |  59,762         |  3,907              |  4,855   | DEFLATE             | -                      | ✔ |   |   |   | ✔ | ✔ | ✔ | ✔ |   |   | ✔ |
|            |  17,600   |  5,000    |  6              |  59,352         |  3,790              |  4,740   | LZMA                | -                      | ✔ |   |   |   | ✔ | ✔ | ✔ | ✔ |   |   | ✔ |
|            |  18,000   |  5,000    |  6              |  60,660         |  3,878              |  4,831   | PPMD                | -                      | ✔ |   |   |   | ✔ | ✔ | ✔ | ✔ |   |   | ✔ |
|            |  18,100   |  5,000    |  6              |  59,695         |  3,896              |  4,845   | HIGH-COMPRESSION    | -                      | ✔ |   |   |   | ✔ | ✔ | ✔ | ✔ |   |   | ✔ |
|            |  18,200   |  5,000    |  7              |  59,762         |  3,907              |  4,855   | ENCRYPTED           | -                      | ✔ |   |   |   | ✔ | ✔ | ✔ | ✔ |   |   | ✔ |
| ZLIB       |  18,200   |  5,000    |  6              |  59,762         |  3,912              |  4,860   | ZLIB                | -                      | ✔ |   |   |   |   |   |   | ✔ |   |   |   |
| 7Zip       |  18,200   |  5,000    |  7              |  59,864         |  3,915              |  4,852   | BZIP2               | -                      | ✔ |   |   |   |   | ✔ |   | ✔ |   |   |   |
|            |  17,600   |  5,000    |  6              |  59,351         |  3,785              |  4,738   | LZMA                | -                      | ✔ |   |   |   |   | ✔ |   | ✔ |   |   |   |
|            |  17,500   |  5,000    |  6              |  59,015         |  3,776              |  4,724   | LZMA2               | -                      | ✔ |   |   |   |   | ✔ |   | ✔ |   |   |   |
|            |  18,000   |  5,000    |  6              |  60,626         |  3,881              |  4,830   | PPMD                | -                      | ✔ |   |   |   |   | ✔ |   | ✔ |   |   |   |
|            |  17,500   |  5,000    |  6              |  58,790         |  3,775              |  4,721   | HIGH-COMPRESSION    | -                      | ✔ |   |   |   |   | ✔ |   | ✔ |   |   |   |
|            |  17,500   |  5,000    |  6              |  59,016         |  3,776              |  4,724   | ENCRYPTED           | -                      | ✔ |   |   |   |   | ✔ |   | ✔ |   |   |   |
| EXTRA      |  4,410    |  5,000    |  7              |  32,156         |  945                |  2,086   | RANSOMWARE          | NOTPETYA               |   |   |   |   |   |   |   | ✔ |   |   |   |
|            |  3,740    |  5,000    |  1              |  32,156         |  802                |  1,951   |                     | SODINOKIBI             |   |   |   |   |   |   |   | ✔ |   |   |   |
|            |  3,730    |  5,000    |  1              |  32,156         |  801                |  1,951   |                     | MAZE                   |   |   |   |   |   |   |   | ✔ |   |   |   |
|            |  4,190    |  5,000    |  1              |  44,381         |  954                |  2,283   |                     | PHOBOS                 |   |   |   |   |   |   |   | ✔ |   |   |   |
|            |  3,740    |  5,000    |  1              |  32,156         |  802                |  1,951   |                     | NETWALKER              |   |   |   |   |   |   |   | ✔ |   |   |   |
|            |  3,902    |  5,000    |  1              |  32,257         |  804                |  1,951   |                     | DHARMA                 |   |   |   |   |   |   |   | ✔ |   |   |   |
|            |  3,994    |  5,000    |  1              |  31,580         |  802                |  1,951   |                     | RYUK                   |   |   |   |   |   |   |   |   |   |   |   |
|            |           |           |                 |                 |                     |          |                     | MAMBA                  |   |   |   |   |   |   |   |   |   |   |   |
|            |           |           |                 |                 |                     |          |                     | SNATCH                 |   |   |   |   |   |   |   |   |   |   |   |
|            |           |           |                 |                 |                     |          |                     | LOCKBIT                |   |   |   |   |   |   |   |   |   |   |   |
|            |           |           |                 |                 |                     |          |                     | DEATHHIDDENTEAR        |   |   |   |   |   |   |   |   |   |   |   |


