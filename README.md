# NapierOne: A Modern Mixed File Data Set

![NapierOne Title](img/NapierOne-title.jpg)

## Summary
A modern cybersecurity mixed file data set called ‘NapierOne’ is presented, primarily aimed at, but not limited to, ransomware detection and forensic analysis. NapierOne was designed to address the known deficiency in research reproducibility and improve consistency by facilitating research replication and repeatability. The methodology used in the creation of this data set is also described in detail. The data set was inspired by the Govdocs1 data set and it is intended that ‘NapierOne’ be used as a complement to this original data set.

An investigation was performed with the goal of determining the common files types currently in use. No specific research was found that explicitly provided this information, so an alternative consensus approach was employed. This involved combining the findings from multiple sources of file type usage into an overall ranked list. After which 5,000 real-world example files were gathered, and a specific data subset created, for each of the common file types identified. In some circumstances, multiple data subsets were created for a specific file type, each subset representing a specific characteristic for that file type. For example, there are multiple data subsets for the ZIP file type with each subset containing examples of a specific compression method. Ransomware execution tends to produce files that have high entropy, so examples of file types that naturally have this attribute are also present. The resulting entire data set comprises of more than 90 separate data subsets divided between 44 distinct file types, resulting in over 450,000 unique files in total.

## Data Sources
### File Selection}
An important aspect of building a representative data set relates to file type usage and popularity. It is known that Google gathers statistics on file types while it performs its website indexing searches. However, the statistics are only gathered on a limited number of file types~\cite{Google2015,Google2016}. 
While it was not possible to discover a definitive ranked list of files types currently in use, it was decided to adopt a consensus approach. This involved querying various sources of possible usage information and gathering approximate lists of up to their Top 40 file types. These lists were then compared and aggregated with the lists gathered from other sources, resulting in a fair representation of what are currently popular file types are in use today. The list produced is not proposed as definitive but rather a best guess consensus.
A list of the sources for file type usage information is discussed below. The alphabetical identification used for each data source is then repeated in the data set description shown in Table~\ref{tab:data-set-details}.

***A - VirusTotal*** Statistics taken from file submissions to this website~\cite{VirusTotal2019} during that past 12 months were recorded.\\
***B - W3Techs*** This website~\cite{W3Techs2014} provides information about the usage of various types of technologies on the web. Statistics relating to the most popular images types were gathered from here.\\
\noindent\textbf{C - Search Engine Statistics} Searches were performed for more than 100 different candidate file types. Search trends and statistics were also analysed and recorded in an attempt to identify the popularity of the file type. Although Google only index certain file types~\cite{Google2015}, their justification for doing so could also be considered a reason to include these files types in the data set.\\
\noindent\textbf{D - File Preservation} There exists research into the investigation of digital data preservation. One aspect of this research is to identify popular file formats. The findings from this research~\cite{dpconline,libraryofcongress,smithsonian,Jackson2012,Ryan2014} were also taken into account, as this research identifies certain files as being important and have the potential for remaining in active use for the foreseeable future.\\
\noindent\textbf{E - MIME Type Statistics} A MIME type~\cite{Freed1996,Freed2013} is a standard label used to indicate the nature and format of a document, file, or assortment of bytes. It is mainly used in Internet-based technology so that software can know how to handle the data. It serves the same purpose on the Internet that file extensions do on Microsoft Windows. When crawling the internet, these labels may be recorded and the frequency of them can be used to identify the popularity of file formats. Statistics have thus been gained from the WayBackMachine~\cite{wayback} and for WebCrawler~\cite{CommonCrawl2021}, who record and publish monthly statistics on MIME types that are encountered.\\
\noindent\textbf{F - fileinfo.com} This website~\cite{fileinfo} performs research into file types and regularly publishes ranked lists of popular file types. These popularity lists are calculated from both the requests that the website receives and general web traffic analysis.\\
\noindent\textbf{G - Ransomware Targets} One of the anticipated initial applications of this data set will be in the field of ransomware research. For the data set to be useful in this research, it should contain a good selection of file types that are regularly targeted by ransomware~\cite{Al-rimy2018,Jung2018,Kharraz2016}, typical examples of which being DOCX and XLSX. This additional criterion did not impact the main goal of listing common file types as these file types appear in multiple lists.\\
\noindent\textbf{H - High Entropy} As the data set will initially be used in ransomware detection testing, it was considered a benefit for the data set to contain files that had this attribute. One technique used to identify files that have been affected by ransomware is to test the file's entropy so including files that normally have this attribute, such as archive files, would provide realistic challenges in ransomware identification. This secondary consideration does not impact the overall goal of generating the file type popularity list.\\
\noindent\textbf{I - File-extension} These are others websites~\cite{fileextension,File-extensions.org2021} specialising in file type research and regularly publish file type usage statistics.\\
\noindent\textbf{J - OS Installation} File type count statistics were gathered from clean windows installations (XP 2003 SP1, Vista 2006 and Windows 10 20H2) as well as four clean 64Bit Linux installations (MX Linux 19.4, Debian 5.9.1, Ubuntu 18.04.1, and Ubuntu 20.10).\\
\noindent\textbf{K - Govdocs1} Inclusion of the file types in the original Govdocs1 data set~\cite{govdocs} were also taken into consideration when deciding if they should appear in this data set. However, the actual files being sourced from elsewhere.\\

The results for all the sources were then sorted by popularity and aggregated into a list of approximately 40 file types. To encourage consensus, the file types needed to appear in at least two lists before they were considered in the final results.


The contents of the new data set were generated in the following ways:
\begin{itemize}
    \item Examples of files using the most commonly used document types such as DOC, DOCX, PDF, PPT, PPTX, XLS, and XLS  were be gathered from the UK government domain, \emph{gov.uk}. Files collected from this domain are covered by the 'Open Government License agreement for Public Sector Information'~\cite{OGL}. This agreement allows for the free distribution of the documents as long as they are accompanied by the correct attribution.
    \item Image files in the TIF format were taken from the RAISE data set~\cite{Dang-Nguyen2015}. This data set permits redistribution of its contents as long as it is accompanied by the correct attribution. Subsequent image file type data subsets, for example, BMP, EPS, GIF, ICO, JPG, PNG, SVG and WEBP were generated from this original TIF data set.
    \item Archive data subsets were generated using files from the documents subset.
    \item Audio files were gathered from the Free Music Archive~\cite{Defferrard2017}. Its license permits free and unrestricted usage and distribution.
    \item Video files, in MP4, format, were gathered from the Kinetics-700 data set~\cite{Carreira2020}. Its license also allows free usage and distribution when using the correct attribution. Other video data sets in different formats were generated by transcoding this MP4 data set.
    \item Examples of files in the EPUB format were taken from Project Gutenberg~\cite{Hart2021}, which is an online library of free eBooks.
\end{itemize}

