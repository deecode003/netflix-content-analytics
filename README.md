# Netflix Content Strategy Analysis

Exploratory data analysis of Netflix's global content catalog to uncover trends in content strategy, catalog composition, and geographic/genre gaps — framed around the kinds of questions a content strategy or analytics team would actually ask.

## Business Questions Explored

1. Has Netflix's content mix (Movies vs. TV Shows) shifted over time?
2. Is the content rating distribution skewed toward mature audiences, and is kids/family content underrepresented?
3. Is the catalog concentrated around a small number of directors/actors, or is it a long-tail, diverse catalog?
4. Which countries dominate content production, and where are the geographic gaps?
5. Which genres are over- or under-represented relative to the rest of the catalog?

## Dataset

- **Source:** Netflix titles dataset (8,807 records)
- **Fields:** `show_id`, `type`, `title`, `director`, `cast`, `country`, `date_added`, `release_year`, `rating`, `duration`, `listed_in` (genre), `description`
- **Missing data:** Several columns (`director`, `cast`, `country`, `date_added`, `rating`, `duration`) contained nulls; each was handled with a documented, column-specific strategy rather than a blanket fill (see notebook, Data Cleaning section).

## Key Insights

- **Content mix:** The catalog skews ~70/30 toward Movies (6,131) over TV Shows (2,676).
- **Rating distribution:** TV-MA and TV-14 dominate the catalog, while TV-Y and TV-Y7 (kids' ratings) are the smallest categories — suggesting limited investment in children's content relative to mature content.
- **Catalog concentration:** Despite a few standout names (e.g. the most-credited director appears in only 22 titles), over 96% of directors have two or fewer titles in the catalog — this is a long-tail catalog, not one built around a small set of prolific creators.
- **Geographic concentration:** The US is the single largest content-producing country by a wide margin, pointing to a clear opportunity gap in international content investment.
- **Genre distribution:** International Movies and Dramas are the most common genres, while genres like horror are comparatively underrepresented — a potential content-gap/growth area.

## Tools & Tech Stack

`Python` · `Pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `Jupyter Notebook`

## Repository Structure

```
├── Netflix_Project.ipynb   # Main analysis notebook
├── requirements.txt        # Python dependencies
└── README.md
```

## How to Run

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
pip install -r requirements.txt
jupyter notebook Netflix_Project.ipynb
```

## Planned Enhancements

This project is being actively extended beyond the initial EDA pass:

- [ ] Time-series analysis of `date_added` to measure content acquisition pace over time
- [ ] Split `duration` into movie runtime vs. TV season count for separate analysis
- [ ] SQL-based querying (SQLite) to answer the business questions above using SQL instead of Pandas
- [ ] Statistical testing (chi-square) on rating vs. content-type association
- [ ] Interactive dashboard (Plotly/Tableau) summarizing key findings

## License

This project is licensed under the MIT License.
