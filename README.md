# book-template

`book-template` allows you to take a collection of [Markdown](https://en.wikipedia.org/wiki/Markdown) files and turn them into a single file. Currently, the supported output file formats are [EPUB](https://en.wikipedia.org/wiki/EPUB) and [PDF](https://en.wikipedia.org/wiki/PDF).

## Instructions

### Organizing your content

#### Text

Place your input Markdown files into the `src` directory. To keep your chapters in order, add the chapter number (with leading zeroes if necessary) at the start of the filename.

#### Cover

Replace the included cover image (`cover.jpg`) with your own cover image.

#### Metadata

Replace the included metadata (inside `metadata.yaml`) with your own metadata.

### Building locally

**Dependencies**

- [GNU Make](https://www.gnu.org/software/make/)
- [Pandoc](https://pandoc.org/)

To generate your outputs locally, you can use the targets included in `Makefile`. Generated files will appear in the `build` directory.

| Target                 | Description                                                                                 |
| ---------------------- | ------------------------------------------------------------------------------------------- |
| `all`                  | Generates all formats                                                                       |
| `clean`                | Deletes the `build` directory                                                               |
| `epub`                 | Generates an EPUB                                                                           |
| `install-dependencies` | Installs the `pandoc` and `texlive` packages (this is used in the GitHub Actions workflows) |
| `pdf`                  | Generates a PDF                                                                             |

### Building with GitHub Actions

This repository includes several GitHub Actions workflows that will generate outputs based on the content checked into the `src` directory. These workflows must all be manually triggered, which can be done via the GitHub website. From your repository, go to the `Actions` tab and find the workflow you wish to run on the left. From there, click `Run workflow`. After the run has finished, an artifact containing your final output will be available for download.

**Available workflows:**

- Generate all formats
- Generate EPUB
- Generate PDF

---

Sample cover photo (`cover.jpg`) courtesy of [Antonio Zarza](https://unsplash.com/@antoniozarza?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/photos/layered-mountain-ranges-under-a-cloudy-sky-FkKkWob-fkw?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)
