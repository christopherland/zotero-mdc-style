# A Guide to Using MDC Style in Zotero

Version: 1.0

Date: September 18, 2026

This guide explains how to enter source data in Zotero so that citations and bibliographies generated using the MDC CSL style conform as closely as possible to the *MDC Press Style Guide*.

# The "Extra" Field

Most of the supplied Zotero item types supply users with specific, named fields for relevant information, but there is also an **Extra** field. This special field allows users to achieve citations and bibliographic entries that are not possible using Zotero's built-in fields.

## Field vs. Variable Prefixes

Throughout this Guide, a capitalized prefix and colon will routinely specify an input field shown by Zotero. For example:

```text
Date: 1991
```

should be interpreted to mean, "Enter everything after the colon into Zotero's **Date** field."

Zotero's **Extra** field is an important exception to this, because the field allows users to explicitly define what is being entered. This is done by typing an appropriate prefix followed by a colon.

For instance, you can force Zotero to include two titles for a book, if a titled book appears in a titled multi-volume series. Simply enter the following in the **Extra** field:

```text
container-title: Old Testament Theology
```

Similarly, this mechanism can override Zotero's normal handling of a built-in field. For example, Zotero can be forced to ignore the usual **Date** field by supplying a fixed string in the **Extra** field:

```text
issued: "1991–1995"
```

Throughout this Guide, lowercase prefixes are used for variables that must be supplied in the **Extra** field, including the prefix and colon themselves. Uppercase prefixes are used to introduce values that can be entered directly into a Zotero field named by the prefix.

So,

```text
Date: 1991
```

means, "Enter `1991` in Zotero's **Date** field."

Whereas,

```text
issued: "1991–1995"
```

means, "Enter `issued: "1991–1995"` in Zotero's **Extra** field, including the prefix, the colon, and the quotation marks.

## Annotations

The annotated bibliography style (MDC-annotated.csl) will concatenate "note" variables as a single block paragraph (i.e. it treats notes as annotations).

If no variable prefix is supplied in the **Extra** field, Zotero defaults to its "note" variable. This allows you to include annotations without supplying a prefix:

```text
Extra: This is an annotation that might appear in an annotated bibliography.
```

If multiple variables are needed in the Extra field, each variable should begin a new line. To avoid errors, it is best to begin an annotation with an explicit prefix. For example, in the **Extra** field you might enter:

```text
container-title: Old Testament Theology
note: This is an annotation that might appear in an annotated bibliography following one volume
of a multi-volume work entitled <i>Old Testament Theology</i>.
```

# General Data Entry Requirements

## Contributor Names

### Personal Names

Enter personal names using Zotero's standard two-field format. Do not include academic degrees, honorifics, or titles.

```text
First Name: Stanley E.
Last Name: Porter
```

INCORRECT:

```text
Name: Stanley E. Porter, PhD
First Name: Dr. Stanley E.
```

### Ancient Names, Organizations, and Institutions

For simple names, such as ancient names, organizations, institutions, churches, publishers, denominations, committees, and agencies, click the toggle button (immediately after the name field) to switch to **single-field mode**.

Enter the full name exactly as it should appear:

```text
Epictetus
American Psychiatric Association
The Missions Society
Canadian Baptist Archives
```

### Name Suffixes

Enter suffixes in the **first name** field following a comma. Zotero will split the field's content at the comma and treat what follows as a suffix:

```text
First Name: Dale C., Jr.
Last Name: Allison
```

### Selecting a Contributor Role

The role played by a named contributor is set using a dropdown menu in Zotero. For example, click on "Author" and change it to "Editor". The available roles will change depending on the item type (e.g. "Director" and "Producer" become available for films).

CSL allows a contributor to play multiple roles, but it cannot collapse roles played by the same person. So, if a book is "edited and translated by" a single person, your bibliography must be manually corrected.

### Adding Multiple Names

Include additional contributors by clicking the “+” button next to the initial contributor field. Zotero respects and maintains the exact top-to-bottom order of authors, editors, and other contributors. This order directly dictates how they will appear in your citations and bibliography.

### Name Variations

Zotero will automatically use em-dashes in place of contributor names for subsequent entries in a bibliography, if they are by the same author(s) or editor(s). However, in order for this to work the names must be *exactly* the same. Enter a consistent form of each person's name across all Zotero records. Ideally, use the form most commonly used by the author in scholarly publications.

## Titles

### Quotes in Titles

Zotero will ensure that quotation marks toggle properly between single and double quotes. You need not worry about deciding between single and double quotes in Zotero's title fields.

### Ranges in Titles

For ranges within titles, you must manually supply en-dashes. Zotero cannot fix hyphens in titles when generating citations or bibliographies.

INCORRECT:

```text
Title: The "Exegetical Logic" of Daniel 9.1-27 (with hyphen)
```

Correct:

```text
Title: The "Exegetical Logic" of Daniel 9.1–27 (with en-dash)
Title: The ‘Exegetical Logic’ of Daniel 9.1–27 (with en-dash)
```

### Italics in Titles

Put `<i>` before a word to toggle the use of italics, and `</i>` following the last relevant word. This is useful when foreign words appear in a title, or when a title includes another title.

### Capitalization of Titles

Zotero will automatically produce title case for titles. Because foreign words in titles do not follow English capitalization rules, put `<span class="nocase">` before any foreign title or before any foreign word(s) within a title, then put `</span>` after the relevant word(s).

For example:

```text
Title: luther's doctrine of <span class="nocase"><i>sola fide</i></span>
```

Zotero will output this correctly as "Luther's Doctrine of *sola fide*."

### Short Titles

MDC will look for a short title when one is required, then fall back to a full title if it finds an empty field.

Zotero will *not* automatically fix short titles. To produce MDC style, you must manually remove initial articles (e.g. "A," "The") and then manually shorten whatever remains, producing a brief substantive short title (usually, everything up to the first noun).

```text
Title: Remarks on Nominalization
Short Title: Remarks
```

```text
Title: The Prestige Language of Christianity in the Book of Acts: Historical Sociolinguistic Approaches to Multilingualism
Short Title: Prestige Language
```

### Abbreviated Titles

Several fields allow for abbreviated titles to be used in bibliographic entries.

Such abbreviations must follow standard conventions (e.g. SBL Handbook of Style).

If a bibliography is part of a thesis, dissertation, or published monograph, its abbreviations must appear in a List of Abbreviations.

Abbreviated titles will *not* auto-capitalize, so you must enter abbreviations exactly as they should appear.

For example:

```text
Title: New Testament Studies
Journal Abbr: NTS
```

INCORRECT:

```text
Journal Abbr: nts
```

For certain source types, a short title must be entered using an appropriate prefix in the **Extra** field:

```text
container-title-short: ABD (for a dictionary or encyclopedia)
collection-title-short: JSNTSup (for a monograph series)
```

## Multi-Volume Works

### Individual Volumes

If you only wish to cite a single volume out of multiple volumes, create a Zotero item for the individual volume. Enter the volume number of your source as well as the total number of volumes in the set.

When citing a source entered as a single volume, *do not* include the volume number when citing pages using the Word plug-in (e.g. cite pages using just "23–25" rather than "4:23–24"). Zotero knows to include the volume number and colon before the cited pages.

### Individually Titled Volumes

If an individual volume in a titled series has its own title, the book title should be entered in:

```text
Title: Prolegomena
```

The title of the multi-volume work must be entered in **Extra**, so Zotero knows that you are supplying the title of an overarching multi-volume work:

```text
container-title: Reformed Dogmatics
```

### Entire Sets

If you wish to enter an entire multi-volume set, enter the total number of volumes but *do not* enter any individual volume number.

```text
# of Volumes: 3
Volume: [leave blank]
```

When citing such sources, you must include a volume number and colon when using the Word plug-in (e.g. cite pages using "4:23–24" exactly).

## Publishers

Zotero will not automatically fix publisher names. You must manually correct publisher names so they adhere to MDC style.

Incorrect:

```text
Publisher: Wm. B. Eerdmans Publishing Co.
```

Correct:

```text
Publisher: Eerdmans
```

## Dates

### Format

Zotero recommends ISO date formats (YYYY or YYYY-MM or YYYY-MM-DD).

### Ranges

Zotero cannot process a range entered into any of its date fields. To force a date range, use the **Extra** field. You can separate ISO-formatted start- and end-dates with a slash, or use quotation marks to supply a range exactly as it should appear.

For example:

```text
issued: 1991/1992
issued: "1982–2007"
issued: "June/July 2025"
```

## Pagination

Enter full page numbering so that you have all digits available for other citation styles. Zotero will correctly truncate pagination to produce MDC style.

For example, if you enter:

```text
Pages: 134-176
```

Zotero will output:

```text
134–76
```

NB: This applies only to bibliographies. For footnote citations, pagination must be entered *exactly* according to MDC style (see below).

# Zotero Item Types

Choosing a correct item type in Zotero is vital. Not only does each item type supply different input fields, but the contents of these fields will be organized differently depending on the overarching type.

Some types may not seem intuitive. For example:

```text
Essay in an edited volume → Book Section
Review of a book → Journal Article (if it appears in a periodical)
```

The following sections explain how Zotero's item types (and associated input fields) should be used.

## Book

### Authored Books

Use **Author**.

```text
Author: D. A. Carson
```

### Edited Books

Use **Editor**, not Author.

```text
Editor: Stanley E. Porter
```

### Translated Books

Use **Translator**.

```text
Translator: John Bowden
```

### Subsequent Editions

Numeric editions should be entered as numerals.

```text
2
3
```

will automatically become:

```text
2nd ed.
3rd ed.
```

Non-numeric editions should be entered exactly as desired:

```text
Rev. ed.
Rev. and exp. ed.
2nd and rev. ed.
```

### Reprints

If a value is entered into **Original Date** for an original publication year, Zotero will treat the remaining info as reprint info. (NB: This also works for articles reprinted as **Book Chapters**.)

For example:

```text
Date: 1982
Publisher: Brill
Place: Leiden
Original Date: 1958
```

will automatically become:

```text
1958. Reprint, Leiden: Brill, 1982.
```

### Electronic Editions

Enter an exact description in the **Format** field.

```text
Format: Kindle edition
Format: ePub edition
```

### Translations of Ancient Sources

For modern translations of ancient sources, totally different footnote citations are required. To trigger this, put the following in the **Extra** field of a **Book** item:

```text
version: ancient
```

The **Short Title** should not be the ancient source abbreviation but a typical short title. Use the **License** field for the ancient source abbreviation. For example:

```text
Item Type: Book
Author: Aristotle
Translator: George A. Kennedy
Short Title: On Rhetoric
License: Rhet.
Extra: version: ancient
```

will correctly output as follows, if you supply "3.1.1" as "Pages" using the plug-in:

Aristotle, *Rhet.* 3.1.1 (Kennedy, *On Rhetoric*)

To include a series abbreviation such as LCL, use the **Extra** field as usual for the series abbreviation:

```text
version: ancient
collection-title-short: LCL
```

Zotero knows to insert the series abbreviation rather than a short title:

Homer, *Il.* 24.744–746 (Murray, LCL)

## Journal Articles

### Journal Titles

Enter full journal titles in:

```text
Publication:
```

### Abbreviated Journal Titles

Enter standard abbreviations in:

```text
Journal Abbr.:
```

Example:

```text
Publication: Journal of Biblical Literature
Journal Abbr.: JBL
```

MDC style will use the abbreviation when appropriate.

### Issue Numbers

Issue numbers are not required for volumes with continuous pagination, but MDC allows them and they will be included if they are in your database. You must remove issue numbers from your database if you wish to exclude them from your citations (though this will prevent you from correctly producing any style that requires the issue number).

### "Online-Only" Articles

Enter DOIs and/or URLs in the designated fields, so they are available for styles that require them.

MDC style will not include a DOI or URL for any article that has typeset pagination.

## Book Chapters

### Chapters in Edited Volumes

Use:

```text
Title:
Author:
Book Title:
Editor:
Pages:
```

Do not place editors in the Author field.

### Chapters in Authored Volumes

In rare occasions where an author publishes a chapter in an authored book by some other author (e.g. an introduction), the author of the overall book should be entered in:

```text
Book Author:
```

This allows the author of the containing work to be distinguished from the author of the cited chapter.

## Dictionary and Encyclopedia Entries

Use these types for individual entries. Use the **Book** type if you wish to cite an entire dictionary or encyclopedia.

```text
Author: the author of the individual entry
Title: the title of the individual entry
Encyclopedia/Dictionary Title: the title of the overall reference work
Pages: the pages on which the individual entry appears
```

You can supply an abbreviated title for the overall reference work in the **Extra** field:

```text
container-title-short: ABD
```

If you are citing an unpaginated electronic edition, you can specify an exact description in the **Extra** field:

```text
medium: Kindle edition
medium: ePub edition
```

## Theses

Use Zotero's **Thesis** type for all theses and dissertations. Enter the relevant source type in the **Type** field exactly as it should appear in the bibliography:

For example:

```text
Type: PhD diss.
Type: ThD diss.
Type: MA thesis
```

## Conference Papers

Use this type only for unpublished oral presentations at academic conferences. For published conference proceedings, use whatever Zotero item type matches the source (usually **Book Section**).

Be sure to include values in the following fields:

```text
Author:
Meeting Name:
Place:
Date:
```

## Presentations

Use this type for oral presentations outside of formal society meetings. The **Type** field allows you to offer a useful description of the type of presentation you are citing.

For example:

```text
Type: sermon
Type: lecture
```

## *Book Reviews

There is no Zotero item type for book reviews. Instead, use an appropriate Zotero item type for the venue in which the review appears (e.g. Journal Article).

Exception: If a book review has been assigned its own unique title, you should enter the review as a titled **Journal Article** rather than as a **Book** with a Title and a Reviewed Author.

Put the author and title of *the reviewed book* in:

```text
Title: The title of the reviewed book
Reviewed Author: The name of the author whose work is being reviewed
```

Use the **Author** field for the name of the reviewer:

```text
Author: The name of the reviewer
```

Use the usual **Journal Article** fields to specify where the review appears. Do *not* use them to identify the work that is being reviewed:

```text
Publication: The journal in which the review appears
Date: The date of the review (NB: *not* the date of the reviewed work)
```

## Podcasts

Oddly, to produce MDC style you must enter "podcast" (or "podcast series") in:

```text
File Type:
```

Include the podcaster and producer as:

```text
Podcaster:
Producer:
```

If a titled podcast episode is part of an overarching series, include the title of the episode in:

```text
Title:
```

Include the title of the whole series and the number of the cited episode in:

```text
Series Title:
Episode Number:
```

Conversely, when citing an entire podcast series, leave the above fields blank and supply the podcast series title in:

```text
Title:
```

## Television Shows

Use the **TV Broadcast** type both for traditional networks and for internet streaming services.

Enter a useful description in the **Format** field:

```text
Format: TV series
Format: Netflix show
```

As with podcasts, Zotero will handle individual episodes differently than entire shows. If you cite an individual titled episode, be sure to include the overall series details in:

```text
Title: Episode title goes here
Program Title: Series title goes here
Episode Number: Episode number goes here
```

To include a season number, use the **Extra** field:

```text
volume: 3
```

## Video Recordings

Use this type for videos posted to social media or uploaded online.

Enter the name (or username) responsible for uploading the video in:

```text
Creator:
```

Use the **Series Title** field to name the relevant platform. To allow for fixed capitalization patterns, you must enter the name exactly as it should appear:

```text
Series Title: YouTube
Series Title: Vimeo
Series Title: TikTok
```

## Emails

Oddly, to produce MDC style you must tell Zotero that your source is an email, using the **Extra** field:

```text
genre: email
```

## Letters

You *must* specify a type:

```text
Type: letter
Type: personal letter
```

## Interviews, Films, Web Pages, Blogs

These types are self-explanatory. Just notice that they allow for different type-specific contributor roles.

# Footnote Citations

## Punctuation

MDC style treats most footnote citations as complete sentences, so they must be followed by a period. However, parenthetical citations appear *inside* punctuated sentences, and a period must not precede the closing parenthesis.

To allow for this flexibility, the CSL style does not add a final period to footnote citations. You must manually conclude your footnote citations with periods, if they are complete sentences.

## Pagination

Pagination auto-formatting applies only to bibliographies. When inserting footnote citations using the Word plug-in, you must enter page references exactly as required by MDC style. Zotero cannot fix your pagination digits or change your hyphens to en-dashes.

INCORRECT:

```text
134-176 (too many digits)
134-76 (hyphen rather than en-dash)
```

## Parenthetical Citations

When a citation supports something stated in a footnote, it must appear in parentheses within the footnote. It is best to use your word processor for the parentheses, leaving Zotero to handle only what goes inside them.

## Prefixes and Suffixes

Zotero allows prefixes and suffixes to be supplied when a source is cited. This content is inserted directly before or after the citation itself.

A common use case for a suffix is to note changes made to quoted text, since this must appear before a concluding period or parenthesis. For example, you might enter the following as a suffix:

```text
(italics original)
[emphasis mine] (for a parenthetical citation)
```

## Author Suppression

When a parenthetical citation immediately follows the naming of an author in a footnote, click the **Suppress Author** checkbox to avoid having the author name duplicated in the Zotero citation.

# Quick Checklist

Before citing, verify:

- The correct Zotero item type has been selected.
- Contributors are in the correct order.
- Contributors have been assigned to the correct roles.
- Organizations have been entered using single-field entry.
- Name suffixes follow a comma in First Name.
- A short title has been correctly entered.
- Title abbreviations have been supplied as appropriate.
- Publisher name has been manually corrected.
- Both original and reprint publication dates have been supplied (if relevant).
- Edition statements match the source exactly.
- Kindle books use `Format: Kindle edition`.