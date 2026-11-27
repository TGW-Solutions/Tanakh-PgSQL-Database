# Tanakh SQL Database (Pardes)

Open relational **PostgreSQL** dataset (`tanakh.sql`) of the **Tanakh**, including Masoretic and consonantal Hebrew text, word-by-word tokenization, gematria values, multilingual verse translations, and Hebrew lexical/morphological data, distributed by the **Pardes** project under **CC BY-SA 3.0**.

---

## 📥 Download

The complete `tanakh.sql` file is available in the **[Releases](https://github.com/TGW-Solutions/Pardes-Tanakh/releases)** section of this repository.

1. Go to the **Releases** tab on GitHub.
2. Select the latest release.
3. Download the `tanakh.sql` file attached under **Assets**.

---

## 🛠️ Compatibility & Import

This dump is exported as plain **PostgreSQL SQL** (`CREATE TYPE ... AS ENUM`, `GENERATED ... AS IDENTITY`, standard `CREATE TABLE` / `CREATE VIEW`, `INSERT INTO`, and `pg_catalog.setval`). It contains only the public dataset schema and records—with no application authentication, roles, ownership clauses, or access-control policies—so it can be restored directly into any clean **PostgreSQL 12+** database (tested on PostgreSQL 17).

```bash
psql "<POSTGRES_CONNECTION_STRING>" --single-transaction --variable ON_ERROR_STOP=1 -f tanakh.sql
```

> **Note:** Because this file uses PostgreSQL-specific DDL and sequence syntax, importing into other RDBMS engines (such as MySQL, SQLite, or SQL Server) requires schema conversion.

---

## 🗄️ Dataset Structure

- **1 Custom Enum Type:** `public.vocabulary_item_type`
- **28 Relational Tables:**
  - **Corpora & Text:** `corpora`, `canonical_divisions`, `artifact_types`, `artifacts`, `artifact_section_types`, `artifact_sections`, `verses`, `verse_translations`, `verse_vocabulary`, `vocabulary`
  - **Lexicon & Morphology:** `language_types`, `parts_of_speech`, `parts_of_speech_i18n`, `morph_tags`, `morph_tags_i18n`, `affixes`, `affixes_i18n`, `lemmas`, `lemmas_i18n`, `bdb_senses`, `bdb_senses_i18n`, `inflected_forms`, `inflected_form_affixes`, `vocabulary_lexical_links`, `bible_books`, `bible_books_i18n`, `lexicon_sample_verses`, `inflected_form_sample_verses`
- **5 Views:**
  - `public.v_indexation_of_corpora` — Primary flattened Tanakh index (books, chapters, verses, word positions, Masoretic/consonantal Hebrew words, gematria values, and verse translations).
  - `public.v_vocabulary_lexicon` — Unified Hebrew lexicon lookup (Strong's definitions, BDB summaries, KJV usage, morphology). *Always filter by `WHERE language_id = <id>`.*
  - `public.v_inflected_forms_i18n` — Inflected Hebrew forms with localized morphological descriptions. *Always filter by `WHERE language_id = <id>`.*
  - `public.v_inflected_form_affixes_i18n` — Ordered prefix/suffix breakdowns with localized grammatical meanings. *Always filter by `WHERE language_id = <id>`.*
  - `public.v_refine_vocabulary` — Data-QA view for detecting unexpected Unicode characters in Masoretic words.

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
