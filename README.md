# RFCXML
This repository is for files associated with the RFCXML language.  For more information on RFCXML see the [authors.ietf.org](https://authors.ietf.org) site, particularly [RFCXML Overview and Background](https://authors.ietf.org/en/rfcxml-overview) and [RFCXML Vocabulary Reference](https://authors.ietf.org/en/rfcxml-vocabulary).

When raising issues, please add appropriate labels:
* **bug**, **enhancement** or **question** for the type of issue
* **RFCXML**, **grammar files** or **templates** for the subject of the issue.  Use **RFCXML** when talking about the language itself, not any instantiation of it.

Issues with [xml2rfc](https://github.com/ietf-tools/xml2rfc) should be reported in that repository. 

## Current grammar files
RFCXML is defined in two RelaxNG Compact (RNC) schema files:
* **rfc7991bis.rnc** is the RelaxNG Compact schema for the current version of RFCXML. XML editors that validate against a schema and which support schema-aware editing, require a local copy of this schema and the following processing instruction in the RFCXML file:
```xml
<?xml-model href="rfc7991bis.rnc"?>
```
* **SVG-1.2-RFC.rnc** is the RelaxNG Compact schema for the subset of SVG allowed in RFCXML documents (SVG 1.2 RFC). This schema is referenced in rfc7991bis.rnc and so no specific processing instruction is required to include it but a local copy must be present.

The files in the root of this repository are the latest versions of those files.

## Templates
The current official templates and schema files for RFCXML can be found in the `templates` folder:
* **draft-rfcxml-general-template-standard-00.xml** is an RFCXML template that includes examples of the most commonly used features of RFCXML with comments explaining how to customise them. This template can be quickly turned into an I-D by editing the examples provided.
* **draft-rfcxml-general-template-bare-00.xml** is an RFCXML template for experienced authors who want to start from the barest template possible. This template validates correctly but is not a valid I-D as many key sections are missing.
* **draft-rfcxml-general-template-annotated-00.xml** is an RFCXML template that includes examples for almost all of the features of RFCXML and many examples of how to achieve specific formatting, along with ample comments to explain the examples.

All of the templates above include the RFCXML processing instruction and so will support schema validation and schema-aware editing out of the box provided that the two grammar files above are in the validation path (generally in the same directory).

See [Templates and Schemas](https://authors.ietf.org/en/templates-and-schemas) for more details.

## Old versions of the grammar files
Old versions of the RFCXML grammar file (not the SVG grammar file) can be found in the `old` folder. This includes both .rnc (RelaxNG Compact) and .rng (RelaxNG) versions.  Note that in [xml2rfc](https://github.com/ietf-tools/xml2rfc), the main tool for processing RFCXML files, these files are named v3.rnc and v3.rng though only the .rnc file is used. These files were never assigned a version number when created and so the snapshots here have been renamed by appending the version number of the [xml2rfc](https://github.com/ietf-tools/xml2rfc) release that first introduced the change (e.g. the version of v3.rnc that was released with v2.32.0 of xml2rfc has been renamed v3-2.32.0.rnc).

Changes to the grammar were initially frequent and then in recent years have become infrequent and so there are normally multiple versions of [xml2rfc](https://github.com/ietf-tools/xml2rfc) that use the same grammar.  The table below lists the versions of the grammar and the versions of xml2rfc that used each version.

| .rnc file | released | changes                             | xml2rfc versions that use this file |
| --------- | -------- | ----------------------------------- | --------------- |
| v3-3.30.0.rnc | 2025-07-17 | - Allow **\<blockquote>** inside **\<dd>** | 3.30.0 onwards
| v3-3.16.0.rnc | 2023-01-18 | - Add ```editorial``` to "submissionType" inside **\<rfc>**<br> - Add ```editorial``` to **\<stream>**<br> - Add ```editorial``` to "stream" inside **\<seriesInfo>** |  3.16.0 to 3.29.0 |
| v3-3.0.0.rnc | 2020-09-02 | - Add "indent" to **\<t>**<br> - Add **\<blockquote>** to **\<aside>**<br> - Add ```adaptive``` for "indent" in **\<ol>**<br> - Add default of ```3``` for "indent" in **\<ul>**<br> - Add default of ```3``` for "indent" in **\<dl>**<br> - Add **\<aside>** inside **\<artwork>** inside **\<dd>**<br> - Add **\<sub>** and **\<sup>** inside **\<sub>** and **\<sup>** | 3.0.0 to 3.15.3 |
| v3-2.47.0.rnc | 2020-07-17 | **Only formatting changes** |  2.47.0 |
| v3-2.46.0.rnc | 2020-06-23 | - Allow multiple email addresses in **\<address>** | 2.46.0 |
| v3-2.40.0.rnc | 2020-02-18 | - Add **\<br>** back again<br> - Fix attribute grouping in **\<ul>** |  2.40.0 to 2.45.3 |
| v3-2.37.0.rnc | 2019-12-10 | - Add **\<contact>** | 2.37.0 to 2.39.0 |
| v3-2.36.0.rnc | 2019-12-02 | - Add **\<table>** inside **\<li>** and **\<dd>** | 2.36.0 |
| v3-2.35.0.rnc | 2019-11-12 | - Add text formatting to **\<xref>** | 2.35.0 |
| v3-2.34.0.rnc | 2019-10-23 | - Add **\<toc>**<br>  - Add "brackets" to **\<eref>**<br> - Fix **\<postal>** to remove order | 2.34.0 |
| v3-2.29.0.rnc | 2019-09-17 | - Add **\<artset>** to **\<td>** and **\<th>** | 2.29.0 |
| v3-2.24.0.rnc | 2019-08-10 | - Remove ```contributor``` as a "role"<br> - Fix empty **\<date>** | 2.24.0 to 2.28.0|
| v3-2.23.0.rnc | 2019-06-27 | - Require at least one **\<artwork>** inside **\<artset>** | 2.23.0 2.23.1 |
| v3-2.22.3.rnc | 2019-04-08 | - Add "indent" to **\<ol>** and **\<ul>** | 2.22.3 |
| v3-2.21.0.rnc | 2019-03-04 | - Add "showOnFrontPage" to **\<organization>** | 2.21.0 to 2.22.2 |
| v3-2.19.0.rnc | 2019-02-14 | - Add **\<artset>** | 2.19.0 to 2.20.0 |
| v3-2.18.0.rnc | 2019-02-06 | - Add "target" to **\<referencegroup>** | 2.18.0 |
| v3-2.15.0.rnc | 2018-11-30 | - Add "anchor" to **\<author>**<br> - Add ```contributor``` to "role"<br> - Change **\<postal>** order<br> - Add **\<u>**<br> - Add "quote-title" to **\<reference>**| 2.15.0 to 2.17.2 |
| v3-2.14.0.rnc | 2018-11-23 | - Add **\<iref>** to **\<table>**<br> - Add **\<stream>** | 2.14.0 2.14.1 |
| v3-2.13.0.rnc | 2018-11-17 | - Fix **\<postal>** order<br> - Add **\<extaddr>**<br> - Add **\<pobox>**<br> - Add **\<cityarea>**<br> - Add **\<sortingcode>**<br> - Add multiple elements to **\<name>**<br> - Change default for "newline" in **\<dl>**<br> - Remove **\<iref>** from **\<table>** (also see 2.14.0)<br> - Remove "derivedAnchor" from **\<refeerencegroup>** | 2.13.0 |
| v3-2.12.3.rnc | 2018-10-30 | - Add **\<pobox>**| 2.12.3 |
| v3-2.12.2.rnc | 2018-10-30 | - Reorder **\<postal>**<br> - Add **\<ext>** **\<cityarea>** **\<sortingcode>** and add to **\<postal>** | 2.12.2 |
| v3-2.12.1.rnc | 2018-10-29 | - Remove "iref" from **\<table>** | 2.12.1 |
| v3-2.12.0.rnc | 2018-10-28 | - Change inclusion of SVG grammar to use file in each release<br> - Change all "pn" from text to "xsd:ID"<br> - Remove "derivedAnchor" and "derivedCounter"<br> - Remove **\<blockquote>** from **\<li>**<br> - Change where **\<postalLine>** is allowed in **\<postal>**| 2.12.0 | 
| v3-2.11.1.rnc | 2018-10-11 | - Add "align" to **\<table>** | 2.11.1 |
| v3-2.11.0.rnc | 2018-10-07 | - Remove **\<br>**<br> - Replace "hanging" with "newline" in **\<dl>**<br> - Add "indent" to **\<dl>**| 2.11.0|
| v3-2.10.3.rnc | 2018-09-22 | - Add "markers" to **\<sourcecode>** | 2.10.3|
| v3-2.10.0.rnc | 2018-07-12 | - Allow **\<author>** inside **\<section>**<br> - Add "bare" to **\<ul>**<br> - Change "displayFormat" to "sectionFormat"<br> - Remove "derivedContent"<br> - Change table span defaults to "1"<br> - Allow multiple nesting of **\<reference>** | 2.10.0 to 2.10.2|
| v3-2.9.0.rnc | 2018-02-09 | - Change "category" to a fixed list<br> - Add support for section references in **\<xref>**<br> - Remove default for "stream"| 2.9.0 to 2.9.9|
| v3-2.7.0.rnc | 2017-07-01 | - Initial version of RFC 7991 grammar | 2.7.0 to 2.8.5|

For more information on [xml2rfc](https://github.com/ietf-tools/xml2rfc) changes, see the [CHANGELOG](https://github.com/ietf-tools/xml2rfc/blob/main/CHANGELOG.md)

## Legacy files
The files found in the `legacy` folder are for those working with very old I-Ds or RFCs and should not be used for any new I-Ds.
* **rfc7991.rnc** is the RelaxNG Compact Schema for the first release of v3 of RFCXML as documented in [RFC7991](https://www.rfc-editor.org/rfc/rfc7991.html). Use rfc7991bis.rnc instead.
* **rfc7749.rnc** is the RelaxNG Compact Schema for v2 of RFCXML as documented in [RFC7749](https://www.rfc-editor.org/rfc/rfc7749.html). When originally published, this file was called v2.rnc.
* **rfc2629.dtd** is the DTD for v1 of RFCXML as documented in [RFC2629](https://www.rfc-editor.org/rfc/rfc2629.html).
* **rfc2629-other.ent** is a small set of character entities. This file is no longer needed as the special processing of non-ASCII character has been superseded by direct support for non-ASCII characters in RFCXML.
* **rfc2629-xhtml.ent** is a larger set of character entities. This file is no longer needed as the special processing of non-ASCII character has been superseded by direct support for non-ASCII characters in RFCXML.