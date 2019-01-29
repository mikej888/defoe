# Get context of specific words and group by year

* Get context (title, publisher, place, page, enclosing text) of each of a set of words and return, grouped by year. Words in the documents are converted to lower-case and non 'a-z' characters (e.g. commas, hyphens etc.) removed before matches are done.
* Query module: `defoe.alto.queries.find_words_context_group_by_year`
* Configuration file:
  - One or more words to search for, one per line.
  - Examples:
    - `queries/diseases.txt`
    - `queries/hearts.txt`
* Result format:

```
<YEAR>
- {page: <PAGE_NUMBER>,
   place: <PLACE>,
   publisher: <PUBLISHER>,
   text: <TEXT_WITHIN_WHICH_WORD_OCCURRED>,
   title: <TITLE>,
   word: <WORD>}
- ...
<YEAR>
...
```

## Sample results

Query over British Library Books `1510_1699/000001143_0_1-20pgs__560409_dat.zip` and `1510_1699/000000874_0_1-22pgs__570785_dat.zip` with `queries/hearts.txt`:

```
1676:
- {page: 000009,
   place: 'London]',
   publisher: null,
   text: '...',
   title: 'A Warning...',
   word: heart}
- ...
```