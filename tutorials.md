![NapierOne Title](img/NapierOne-title.jpg)
# Table of contents
1. [Compression analysis](#CompressionAnalysis)
2. [Encryption analysis](#EncryptionAnalysis)
3. [Password protection analysis](#PasswordProtectionAnalysis)
4. [Image encoding analysis](#ImageEncodingAnalysis>

# Compression analysis <a name="CompressionAnalysis"></a>
The following data sub sets, of the NapiertOne data set, are all examples of archives: 7Zip, GZIP, TAR, RAR, ZIP and ZLIB.

All these archive data subsets were created from the same source folders. A consquence of this being that content of each archive data subset are releated. The relation is provided by the sequence number of the data subset file. For eample the files in the data subset of 7Zip, GZIP,TAR, RAR, ZIP and ZLIB that have the sequence number 0001 were all created from the same source files, the same goes for sequence number 0002, 0003... and so on.

Due to this relationship, it is possible to compare the different archiving methods and efficiencies by comparing archives files from different archive data subsets. The archives are linked using the sequence number.

For example the following data set files all contain archives of the same files, but were created using the different archiving methods.
|File Name | Data Set | Type | Comment|
|--------- | -------- | ---- | ------|
|0001-7z-bzip2.7Z         | BZIP2             | 7Zip| Created using the 7Zip tool|
|0001-7z-encrypted.7Z     | Password protected| 7Zip| Created using the 7Zip tool|
|0001-7z-highcompress.7Z  | High Compression  | 7Zip| Created using the 7Zip tool|
|0001-7z-lzma.7Z          | LZMA compression  | 7Zip| Created using the 7Zip tool|
|0001-7z-LZMA2.7Z         | LZMA2 compression | 7Zip| Created using the 7Zip tool|
|0001-7z-ppmd.7Z          | PPMD compression  | 7Zip| Created using the 7Zip tool|
|0001-gz.gz               | Gzip compression  | GZip| Created using the default configuration of Gzip tool|
|0001-rar.rar             | RAR archive       | RAR | Created using the default configuration of RAR. Archive but no compression|
|0001-tar.tar             | TAR archive       | TAR | Created using the default configuration of TAR. Archive but no compression|
|0001-zip-bzip2.zip       | BZIP2             | Zip | Created using the Zip tool|
|0001-zip-deflate.zip     | DEFLATE           | Zip | Created using the Zip tool|
|0001-zip-encrypted.zip   | Password protected| Zip | Created using the Zip tool|
|0001-zip-highcompress.zip| High Compression  | Zip | Created using the Zip tool|
|0001-zip-lzma.zip        | LZMA compression  | Zip | Created using the Zip tool|
|0001-zip-ppmd.zip        | PPMD compression  | Zip | Created using the Zip tool|
|0001-zlib.zlib           | Zlib              | Zlib | Created using the ZLIB tool|

Data set properies such as file size, entropy, file contents and compression efficiency can then be analysed for each of the archiving techniques.


# Encryption analysis <a name="EncryptionAnalysis"></a>


# Password protection analysis <a name="PasswordProtectionAnalysis"></a>
Microsoft Office format files present in the NapierOne data set include the following formats: DOC, DOCX, PPT, PPTX, XLS and XLSX
Copies of these files were then saved using the password protection functionality provided by Microsift Office tools. The password being used was ***NapierOne***
Again these files were linked using the sequence number.

So for eample:
- the file NapierOne\DOC\DOC\0001-doc.doc has the same content as the file NapierOne\DOC-PASSWORD\0001-doc-password.doc, except it is password protected (encrypted)
- the file NapierOne\DOCX\DOCX\0001-docx.docx has the same content as the file NapierOne\DOCX-PASSWORD\0001-docx-password.docx, except it is password protected (encrypted)
- the file NapierOne\PPT\PPT\0001-ppt.ppt has the same content as the file NapierOne\PPT-PASSWORD\0001-ppt-password.ppt, except it is password protected (encrypted)
- the file NapierOne\PPTX\PPTX\0001-pptx.pptx has the same content as the file NapierOne\PPTX-PASSWORD\0001-pptx-password.pptx, except it is password protected (encrypted)
- the file NapierOne\XLS\XLS\0001-xls.xls has the same content as the file NapierOne\XLS-PASSWORD\0001-xls-password.xls, except it is password protected (encrypted)
- the file NapierOne\XLSX\XLSX\0001-xlsx.xlsx has the same content as the file NapierOne\XLSX-PASSWORD\0001-xlsx-password.xlsx, except it is password protected (encrypted)

These data subsets could then be analysed and compared as we we have examples of the same files in plain text and encrypted. Examples of analasys could be:
- Encryption strength.
- File size changes due to encryption.
- Entropy changes due to encryption.
- 

# Image encoding analysis <a name="ImageEncodingAnalysis"></a>
The following data sub sets, of the NapiertOne data set, are all examples of archives: 7Zip, GZIP, TAR, RAR, ZIP and ZLIB.

All these archive data subsets were created from the same source folders. A consquence of this being that content of each archive data subset are releated. The relation is provided by the sequence number of the data subset file. For eample the files in the data subset of 7Zip, GZIP,TAR, RAR, ZIP and ZLIB that have the sequence number 0001 were all created from the same source files, the same goes for sequence number 0002, 0003... and so on.

Due to this relationship, it is possible to compare the different archiving methods and efficiencies by comparing archives files from different archive data subsets. The archives are linked using the sequence number.

For example the following data set files all contain archives of the same files, but were created using the different archiving methods.
|File Name | Data Set | Type | Comment|
|--------- | -------- | ---- | ------|
|0001-7z-bzip2.7Z         | BZIP2             | 7Zip| Created using the 7Zip tool|
|0001-7z-encrypted.7Z     | Password protected| 7Zip| Created using the 7Zip tool|
|0001-7z-highcompress.7Z  | High Compression  | 7Zip| Created using the 7Zip tool|
|0001-7z-lzma.7Z          | LZMA compression  | 7Zip| Created using the 7Zip tool|
|0001-7z-LZMA2.7Z         | LZMA2 compression | 7Zip| Created using the 7Zip tool|
|0001-7z-ppmd.7Z          | PPMD compression  | 7Zip| Created using the 7Zip tool|
|0001-gz.gz               | Gzip compression  | GZip| Created using the default configuration of Gzip tool|
|0001-rar.rar             | RAR archive       | RAR | Created using the default configuration of RAR. Archive but no compression|
|0001-tar.tar             | TAR archive       | TAR | Created using the default configuration of TAR. Archive but no compression|
|0001-zip-bzip2.zip       | BZIP2             | Zip | Created using the Zip tool|
|0001-zip-deflate.zip     | DEFLATE           | Zip | Created using the Zip tool|
|0001-zip-encrypted.zip   | Password protected| Zip | Created using the Zip tool|
|0001-zip-highcompress.zip| High Compression  | Zip | Created using the Zip tool|
|0001-zip-lzma.zip        | LZMA compression  | Zip | Created using the Zip tool|
|0001-zip-ppmd.zip        | PPMD compression  | Zip | Created using the Zip tool|
|0001-zlib.zlib           | Zlib              | Zlib | Created using the ZLIB tool|

Data set properies such as file size, entropy, file contents and compression efficiency can then be analysed for each of the archiving techniques.
