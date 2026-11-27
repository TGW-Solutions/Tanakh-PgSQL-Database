# Tanakh SQL Database (Pardes)

Repository dedicated to distributing the **Tanakh** database in **SQL** format, used by the **Pardes** project.

---

## 📥 Download

The complete `.sql` file is available for download in the **[Releases](https://github.com/TGW-Solutions/Pardes-Tanakh/releases)** section of this repository.

1. Go to the **Releases** tab on GitHub.
2. Select the latest release.
3. Download the `.sql` file attached under **Assets**.

---

## 📚 Data Sources & Credits

The texts, metadata, lexicon, and morphological analyses included in this database originate from the following open-source projects:

- **[Sefaria Export](https://github.com/Sefaria/Sefaria-Export)**  
  Structured Jewish texts and metadata exported from Sefaria's database • **[CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)** (current Sefaria version).

- **[Miqra al pi ha-Mesorah (מקרא על פי המסורה)](https://he.wikisource.org/wiki/%D7%9E%D7%A7%D7%A8%D7%90_%D7%A2%D7%9C_%D7%A4%D7%99_%D7%94%D7%9E%D7%A1%D7%95%D7%A8%D7%94)**  
  Masoretic Hebrew Bible edition (MAM) on Hebrew Wikisource.

- **[Open Scriptures Hebrew Lexicon](https://github.com/openscriptures/HebrewLexicon)**  
  Parsed Brown-Driver-Briggs (BDB) lexicon and Strong's concordance data.  
  *These files are released under the [Creative Commons Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/) license. The actual text of Brown, Driver, Briggs and Strong’s Hebrew dictionary remain in the public domain. For attribution purposes, credit the Open Scriptures Hebrew Bible Project.*

- **[Open Scriptures MorphHB](https://github.com/openscriptures/morphhb)**  
  Morphological analysis and parsing of the Hebrew Bible (OSHB).  
  *Lemma and morphology data are licensed under a [Creative Commons Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/) license. For attribution purposes, credit the Open Scriptures Hebrew Bible Project. The text of the WLC remains in the [Public Domain](http://creativecommons.org/publicdomain/mark/1.0/). See the [LICENSE](https://github.com/openscriptures/morphhb/blob/master/LICENSE.md) file for more information.*

---

## 📄 License & Attribution

This SQL database is a **derivative work** created by the **Pardes** project. The Hebrew text (MAM via Sefaria Export) and translations were restructured into relational database tables, tokenized word-by-word, enriched with gematria calculations, combined with Open Scriptures lexical and morphological data, and adapted/translated with AI assistance.

- **Derivative Dataset License:** In accordance with the ShareAlike requirement of Sefaria Export's license, this combined SQL dataset is distributed under **[Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)](https://creativecommons.org/licenses/by-sa/3.0/)**.
- **Source Attributions:** Please preserve all original source credits listed above (**Sefaria Export** under **CC BY-SA 3.0**, **Miqra al pi ha-Mesorah**, and the **Open Scriptures Hebrew Bible Project** under **CC BY 4.0**, with BDB/Strong's and the WLC remaining in the **Public Domain**).
