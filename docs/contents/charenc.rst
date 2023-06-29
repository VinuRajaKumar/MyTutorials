==============
Character sets
==============
There are many encoding schemes such as ASCII, Latin-1 and Unicode to represent characters in computers. Often, the lack of accomodating new requirements in an existing encoding method leads to development of a new encoding sheme. This write-up attempts to provide some basic information as what they are and why do they exist.

ASCII
=====
*ASCII* (American Standard Code for Information Interchange), developed by American National Standards Institute (ANSI), is the most common format for encoding characters in a computer. This is a seven-bit encoding technique which assigns a number to each alphabetic, numeric, or special characters used most frequently in American English. 

.. note::

	ASCII extends from 0 to 127 only. The MSB is always 0.


.. table:: **ASCII CHART**
    :widths: 8 8 8 8 8 8 8 8 8 8 8 8
    :align: center

    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    | **CONTROL**                                               | **NUMBERS & SPECIAL (PRINTABLE)**                         |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |NUL      |0        |0        |DLE      |16       |10       |SP       |32       |20       |0        |48       |30       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |SOH      |1        |1        |DC1      |17       |11       |!        |33       |21       |1        |49       |31       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |STX      |2        |2        |DC2      |18       |12       |"        |34       |22       |2        |50       |32       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |ETX      |3        |3        |DC3      |19       |13       |#        |35       |23       |3        |51       |33       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |EOT      |4        |4        |DC4      |20       |14       |$        |36       |24       |4        |52       |34       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |ENQ      |5        |5        |NAK      |21       |15       |%        |37       |25       |5        |53       |35       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |ACK      |6        |6        |SYN      |22       |16       |&        |38       |26       |6        |54       |36       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |BEL      |7        |7        |ETB      |23       |17       |'        |39       |27       |7        |55       |37       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |BS       |8        |8        |CAN      |24       |18       |(        |40       |28       |8        |56       |38       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |HT       |9        |9        |EM       |25       |19       |)        |41       |29       |9        |57       |39       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |LF       |10       |A        |SUB      |26       |1A       |\*       |42       |2A       |:        |58       |3A       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |VT       |11       |B        |ESC      |27       |1B       |\+       |43       |2B       |;        |59       |3B       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |FF       |12       |C        |FS       |28       |1C       |\,       |44       |2C       |<        |60       |3C       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |CR       |13       |D        |GS       |29       |1D       |\-       |45       |2D       |=        |61       |3D       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |SO       |14       |E        |RS       |30       |1E       |.        |46       |2E       |>        |62       |3E       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |SI       |15       |F        |US       |31       |1F       |/        |47       |2F       |?        |63       |3F       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    | **UPPER CASE & SPECIAL (PRINTABLE)**                      | **LOWER CASE & SPECIAL (PRINTABLE)**                      |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |@        |64       |40       |P        |80       |50       |\`       |96       |60       |p        |112      |70       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |A        |65       |41       |Q        |81       |51       |a        |97       |61       |q        |113      |71       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |B        |66       |42       |R        |82       |52       |b        |98       |62       |r        |114      |72       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |C        |67       |43       |S        |83       |53       |c        |99       |63       |s        |115      |73       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |D        |68       |44       |T        |84       |54       |d        |100      |64       |t        |116      |74       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |E        |69       |45       |U        |85       |55       |e        |101      |65       |u        |117      |75       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |F        |70       |46       |V        |86       |56       |f        |102      |66       |v        |118      |76       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |G        |71       |47       |W        |87       |57       |g        |103      |67       |w        |119      |77       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |H        |72       |48       |X        |88       |58       |h        |104      |68       |x        |120      |78       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |I        |73       |49       |Y        |89       |59       |i        |105      |69       |y        |121      |79       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |J        |74       |4A       |Z        |90       |5A       |j        |106      |6A       |z        |122      |7A       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |K        |75       |4B       |[        |91       |5B       |k        |107      |6B       |{        |123      |7B       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |L        |76       |4C       |\        |92       |5C       |l        |108      |6C       |\|       |124      |7C       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |M        |77       |4D       |]        |93       |5D       |m        |109      |6D       |}        |125      |7D       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |N        |78       |4E       |^        |94       |5E       |n        |110      |6E       |~        |126      |7E       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+
    |O        |79       |4F       |_        |95       |5F       |o        |111      |6F       |DEL      |127      |7F       |
    +---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+---------+


ISO 8859
========
Normally, the computers store the information as a collection of 8 bits (1 Byte). Since the ASCII standard defines only 128 characters, people thought the remaining 128 characters can be used to represent characters from a different language family. *ISO-8859* is a family of single-byte encoding schemes used to represent alphabets that can be represented within the range of 127 to 255. This is an eight-bit extension to ASCII developed by ISO (the International Organization for Standardization). These various alphabets are defined as "parts" in the format ISO-8859-n, the most familiar of these likely being ISO-8859-1 aka 'Latin-1' , which contained characters sufficient for the most common Western European languages (191 characters) . Variations were standardized for other languages as well: ISO 8859-2 for Eastern European languages and ISO 8859-5 for Cyrillic languages, for example.

.. warning::

	Latin-1 is occasionally, though imprecisely, referred to as Extended ASCII. This is because the first 128 characters of its set are identical to the US ASCII standard. The remainder of the set contains accented characters and symbols. The most popular is ISO 8859-1, also called ISO Latin 1 

The drawback to this encoding scheme is its inability to accommodate languages comprised of more than 128 symbols, or to safely display more than one family of symbols at one time.

.. note::
	
	When a particular character of ASCII or ISO 8859 character set is represented in computers, the same assigned 8 bit value representing the character is used to store the character in computer.
	
Unicode & UCS
=============
ASCII, LATIN1 and SJIS are common encodings that cannot encode all characters of the world languages. In the late 1980s, there have been two independent attempts to create a single unified character set. One was the ISO 10646 project of the **International Organization for Standardization (ISO)**, the other was the **Unicode Project** organized by a consortium of (initially mostly US) manufacturers of multi-lingual software. Fortunately, the participants of both projects realized in around 1991 that two different unified character sets is not exactly what the world needs. They joined their efforts and worked together on creating a single code table. Both projects still exist and publish their respective standards independently, however the Unicode Consortium and ISO/IEC JTC1/SC2 have agreed to keep the code tables of the Unicode and ISO 10646 standards compatible and they closely coordinate any further extensions. Unicode 1.1 corresponded to ISO 10646-1:1993, Unicode 3.0 corresponded to ISO 10646-1:2000, Unicode 3.2 added ISO 10646-2:2001, and Unicode 4.0 corresponds to ISO 10646:2003, and Unicode 5.0 corresponds to ISO 10646:2003 plus its amendments 1–3. All Unicode versions since 2.0 are compatible, only new characters will be added, no existing characters will be removed or renamed in the future.

The international standard ISO 10646 defines the term Universal Character Set (UCS) and refers to the Unicode characters defined by the Unicode consortium.

.. note::

	UCS and Unicode only define code points, that is, a number which represents a character. How you store these code points in memory depends of the encoding that you are using.

Code Points and Encoding
========================
For Unicode text to be transmitted or stored, it must be encoded into a sequence of bytes. UCS and Unicode are first of all just code tables that assign integer numbers to characters. There exist several alternatives for how a sequence of such characters or their respective integer values can be represented as a sequence of bytes. The following are the different type of encoding schemes used to represent the UCS/Unicode characters in computer memory.

UTF
===
UTF is a family of multi-byte encoding schemes that can represent Unicode code points which can be reperesentative of up to 2^31 [roughly 2 billion] characters. UTF-8 is a flexible encoding system that uses between 1 and 4 bytes to represent the first 2^21 [roughly 2 million] code points.

UTF-8 and UTF-16 are common encodings that can handle the entire range of characters. Both are variable length encodings where some characters take more bytes than others. 

UTF-8
=====
UTF-8 (8-bit Unicode Transformation Format) is a variable width character encoding capable of encoding all 1,112,064[nb 1] valid code points in Unicode using one to four 8-bit bytes. The encoding is defined by the Unicode Standard, and was originally designed by Ken Thompson and Rob Pike.

*UTF-8* is a multibyte encoding that can represent any Unicode character. ISO 8859-1 is a single-byte encoding that can represent the first 256 Unicode characters. Former is a variable-length encoding, latter single-byte fixed length encoding. Latin-1 encodes just the first 256 code points of the Unicode character set, whereas UTF-8 can be used to encode all code points. At physical encoding level, only codepoints 0 - 127 get encoded identically; code points 128 - 255 differ by becoming 2-byte sequence with UTF-8 whereas they are single bytes with Latin-1.

As with UTF-8, 7-bit-safe ASCII remains unaffected regardless of the encoding family used. 

Long story short: any character with a code point/ordinal representation below 127, aka 7-bit-safe ASCII is represented by the same 1-byte sequence as most other single-byte encodings. Any character with a code point above 127 is represented by a sequence of two or more bytes, with the particular of encoding best explained here.

ASCII has the interesting property that all ASCII sequences are valid UTF-8 sequences and encode the same characters. 

The UTF-8 encoding defined in ISO 10646-1:2000 Annex D and also described in RFC 3629 as well as section 3.9 of the Unicode 4.0 standard does not have these problems. It is clearly the way to go for using Unicode under Unix-style operating systems.

UTF-8 has the following properties:

    * UCS characters U+0000 to U+007F (ASCII) are encoded simply as bytes 0x00 to 0x7F (ASCII compatibility). This means that files and strings which contain only 7-bit ASCII characters have the same encoding under both ASCII and UTF-8.
    * All UCS characters >U+007F are encoded as a sequence of several bytes, each of which has the most significant bit set. Therefore, no ASCII byte (0x00-0x7F) can appear as part of any other character.
    * The first byte of a multibyte sequence that represents a non-ASCII character is always in the range 0xC0 to 0xFD and it indicates how many bytes follow for this character. All further bytes in a multibyte sequence are in the range 0x80 to 0xBF. This allows easy resynchronization and makes the encoding stateless and robust against missing bytes.
    * All possible 231 UCS codes can be encoded.
    * UTF-8 encoded characters may theoretically be up to six bytes long, however 16-bit BMP characters are only up to three bytes long.
    * The sorting order of Bigendian UCS-4 byte strings is preserved.
    * The bytes 0xFE and 0xFF are never used in the UTF-8 encoding. 

The following byte sequences are used to represent a character. The sequence to be used depends on the Unicode number of the character:

======================= ======== ======== ======== ======== ======== ========
U-00000000 – U-0000007F 0xxxxxxx                                     
----------------------- -------- -------- -------- -------- -------- --------
U-00000080 – U-000007FF 110xxxxx 10xxxxxx                            
----------------------- -------- -------- -------- -------- -------- --------
U-00000800 – U-0000FFFF 1110xxxx 10xxxxxx 10xxxxxx                   
----------------------- -------- -------- -------- -------- -------- --------
U-00010000 – U-001FFFFF 11110xxx 10xxxxxx 10xxxxxx 10xxxxxx          
----------------------- -------- -------- -------- -------- -------- --------
U-00200000 – U-03FFFFFF 111110xx 10xxxxxx 10xxxxxx 10xxxxxx 10xxxxxx 
----------------------- -------- -------- -------- -------- -------- --------
U-04000000 – U-7FFFFFFF 1111110x 10xxxxxx 10xxxxxx 10xxxxxx 10xxxxxx 10xxxxxx
======================= ======== ======== ======== ======== ======== ========

The xxx bit positions are filled with the bits of the character code number in binary representation. The rightmost x bit is the least-significant bit. Only the shortest possible multibyte sequence which can represent the code number of the character can be used. Note that in multibyte sequences, the number of leading 1 bits in the first byte is identical to the number of bytes in the entire sequence.

Examples: The Unicode character U+00A9 = 1010 1001 (copyright sign) is encoded in UTF-8 as

    11000010 10101001 = 0xC2 0xA9

and character U+2260 = 0010 0010 0110 0000 (not equal to) is encoded as:

    11100010 10001001 10100000 = 0xE2 0x89 0xA0

The official name and spelling of this encoding is UTF-8, where UTF stands for UCS Transformation Format. Please do not write UTF-8 in any documentation text in other ways (such as utf8 or UTF_8), unless of course you refer to a variable name and not the encoding itself.

An important note for developers of UTF-8 decoding routines: For security reasons, a UTF-8 decoder must not accept UTF-8 sequences that are longer than necessary to encode a character. For example, the character U+000A (line feed) must be accepted from a UTF-8 stream only in the form 0x0A, but not in any of the following five possible overlong forms:

  0xC0 0x8A
  0xE0 0x80 0x8A
  0xF0 0x80 0x80 0x8A
  0xF8 0x80 0x80 0x80 0x8A
  0xFC 0x80 0x80 0x80 0x80 0x8A

Both the UCS and Unicode standards are first of all large tables that assign to every character an integer number. If you use the term “UCS”, “ISO 10646”, or “Unicode”, this just refers to a mapping between characters and integers. This does not yet specify how to store these integers as a sequence of bytes in memory.

ISO 10646-1 defines the UCS-2 and UCS-4 encodings. These are sequences of 2 bytes and 4 bytes per character, respectively.

http://www.fileformat.info/info/unicode/utf8.htm

    ASCII: 7 bits. 128 code points.

    ISO-8859-1: 8 bits. 256 code points.

    UTF-8: 8-32 bits (1-4 bytes). 1,112,064 code points.

Both ISO-8859-1 and UTF-8 are backwards compatible with ASCII, but UTF-8 is not backwards compatible with ISO-8859-1:

Latin-1, also called ISO-8859-1, is an 8-bit character set endorsed by the International Organization for Standardization (ISO) and represents the alphabets of Western European languages

UTF-8 Encoding
    UTF-8 is a compromise character encoding that can be as compact as ASCII (if the file is just plain English text) but can also contain any unicode characters (with some increase in file size).

UTF stands for Unicode Transformation Format. The '8' means it uses 8-bit blocks to represent a character. The number of blocks needed to represent a character varies from 1 to 4.

One of the really nice features of UTF-8 is that it is compatible with nul-terminated strings. No character will have a nul (0) byte when encoded. This means that C code that deals with char[] will "just work".

UCS and Unicode are first of all just code tables that assign integer numbers to characters. There exist several alternatives for how a sequence of such characters or their respective integer values can be represented as a sequence of bytes. The two most obvious encodings store Unicode text as sequences of either 2 or 4 bytes sequences. The official terms for these encodings are UCS-2 and UCS-4, respectively. Unless otherwise specified, the most significant byte comes first in these (Bigendian convention). An ASCII or Latin-1 file can be transformed into a UCS-2 file by simply inserting a 0x00 byte in front of every ASCII byte. If we want to have a UCS-4 file, we have to insert three 0x00 bytes instead before every ASCII byte. 

The official name and spelling of this encoding is UTF-8, where UTF stands for UCS Transformation Format.
Both the UCS and Unicode standards are first of all large tables that assign to every character an integer number. If you use the term “UCS”, “ISO 10646”, or “Unicode”, this just refers to a mapping between characters and integers. This does not yet specify how to store these integers as a sequence of bytes in memory.

ISO 10646-1 defines the UCS-2 and UCS-4 encodings. These are sequences of 2 bytes and 4 bytes per character, respectively.

In order to allow the automatic detection of the byte order, it has become customary on some platforms (notably Win32) to start every Unicode file with the character U+FEFF (ZERO WIDTH NO-BREAK SPACE), also known as the Byte-Order Mark (BOM). Its byte-swapped equivalent U+FFFE is not a valid Unicode character, therefore it helps to unambiguously distinguish the Bigendian and Littleendian variants of UTF-16 and UTF-32.

Unicode Private Use Areas (PUC) Range : U+E000 to U+F8FF

UCS
===
The two most obvious encodings store Unicode text as sequences of either 2 or 4 bytes sequences. The official terms for these encodings are UCS-2 and UCS-4, respectively. Unless otherwise specified, the most significant byte comes first in these (Bigendian convention). An ASCII or Latin-1 file can be transformed into a UCS-2 file by simply inserting a 0x00 byte in front of every ASCII byte. If we want to have a UCS-4 file, we have to insert three 0x00 bytes instead before every ASCII byte. 
Using UCS-2 (or UCS-4) under Unix would lead to very severe problems. Strings with these encodings can contain as parts of many wide characters bytes like “\0” or “/” which have a special meaning in filenames and other C library function parameters. In addition, the majority of UNIX tools expects ASCII files and cannot read 16-bit words as characters without major modifications. For these reasons, UCS-2 is not a suitable external encoding of Unicode in filenames, text files, environment variables, etc.

.. note::

	Mojibake (文字化け; IPA: [mod͡ʑibake]) is the garbled text that is the result of text being decoded using an unintended character encoding. The result is a systematic replacement of symbols with completely unrelated ones, often from a different writing system.
