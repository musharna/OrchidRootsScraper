# OrchidRootsScraper

A Selenium and BeautifulSoup scraper for [orchidroots.com](https://www.orchidroots.com/), together
with the R analysis built on its output.

Written for a bioinformatics course project on hybridization in the orchid genus *Cattleya*. The
write-up, figures and derived data live in
[`musharna/cattleya-hybridization-signal`](https://github.com/musharna/cattleya-hybridization-signal),
where both files here are also vendored.

| File                   | What it is                                                                                              |
| ---------------------- | ------------------------------------------------------------------------------------------------------- |
| `scraper_v1.0.py`      | Walks the *Cattleya* hybrid index letter by letter, then the species index, and writes two CSVs          |
| `OrchidRootsPlots.Rmd` | Trend plots, species-level tree construction, and the phylogenetic signal tests (K, lambda, Moran's I, Cmean) |

The `.Rmd` here reads from `data/` since it sits at the repository root. The vendored copy in the
analysis repository reads from `../data/` instead, which is the only difference between them.

## Running the scraper

Fill in the `CONFIG` block at the top with an orchidroots account and a `chromedriver` path matching
your Chrome. The committed values are placeholders rather than credentials.

Requires `selenium`, `beautifulsoup4`, `pandas` and `requests`.

## Before you run it

As written, the script also downloads every species and grex photograph, through
`download_images_species` and `download_images_grexs`. Those are third-party copyrighted images, so
comment out both calls in `main()` unless you specifically need them.

The waits in `CONFIG` double as rate limiting and should not be lowered. A full run takes hours by
design.

orchidroots republishes the RHS International Orchid Register. Scraping it for research is one
thing and redistributing a substantial part of it is another, so the scraped CSVs are deliberately
not published in either repository.

## License

MIT, see [`LICENSE`](LICENSE).
