# OrchidRootsScraper

A Selenium + BeautifulSoup scraper for [orchidroots.com](https://www.orchidroots.com/), and the
R analysis built on its output.

Written for a bioinformatics course project on hybridization in the orchid genus *Cattleya*.
The write-up, figures and derived data live in
[`musharna/cattleya-hybridization-signal`](https://github.com/musharna/cattleya-hybridization-signal),
where both files here are also vendored.

| File                    | What it is                                                                                              |
| ----------------------- | ------------------------------------------------------------------------------------------------------- |
| `scraper_v1.0.py`       | Walks the *Cattleya* hybrid index letter by letter, then the species index, and writes two CSVs          |
| `OrchidRootsPlots.Rmd`  | Trend plots, species-level tree construction, and the phylogenetic signal tests (K, λ, Moran's I, Cmean) |

## Running the scraper

Fill in the `CONFIG` block at the top — an orchidroots account, and a `chromedriver` path
matching your Chrome. The committed values are placeholders, not credentials.

Requires `selenium`, `beautifulsoup4`, `pandas`, `requests`.

**Before you run it:**

- The script also downloads every species and grex photograph (`download_images_species`,
  `download_images_grexs`). Those are third-party copyrighted images. Comment out both calls in
  `main()` unless you specifically need them.
- The waits in `CONFIG` double as rate limiting. Do not lower them — a full run takes hours by
  design.
- orchidroots republishes the RHS International Orchid Register. Scraping it for research is one
  thing; redistributing a substantial part of it is another. The scraped CSVs are deliberately
  not published in either repository.

## License

MIT — see [`LICENSE`](LICENSE).
