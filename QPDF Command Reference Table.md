| Action                 | Command                                                     | Explanation                                                                                                                                                |
| :--------------------- | :---------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Merge PDFs** 📂      | `qpdf --empty --pages file1.pdf file2.pdf -- merged.pdf`    | Creates a new, empty PDF and adds all pages from `file1.pdf` and `file2.pdf` in that order. The `--` is essential to separate inputs from the output file. |
| **Extract Pages** ✂️   | `qpdf input.pdf --pages . 1-10 -- extracted.pdf`            | Creates a new PDF containing only pages 1 through 10 from the source file. The `.` is a placeholder for the main input file (`input.pdf`).                 |
| **Split All Pages** 📄 | `qpdf input.pdf --split-pages output-%d.pdf`                | Splits the input PDF into individual files for each page, named sequentially (e.g., `output-1.pdf`, `output-2.pdf`, etc.).                                 |
| **Rotate Pages** 🔄    | `qpdf input.pdf rotated.pdf --rotate=+90:1-5`               | Rotates pages 1-5 by 90 degrees clockwise (`+90`). Use `-90` for counter-clockwise. Omit the page range (`:1-5`) to rotate the entire document.            |
| **Encrypt PDF** 🔒     | `qpdf --encrypt user-pass owner-pass 256 -- in.pdf out.pdf` | Protects a PDF with a user password (for opening) and an owner password (for permissions). `256` sets the encryption key length.                           |
| **Decrypt PDF** 🔓     | `qpdf --decrypt --password=pass in.pdf out.pdf`             | Removes password protection from an encrypted PDF, provided you have the correct password.                                                                 |
qpdf input.pdf --pages . 240-254 -- output.pdf    





