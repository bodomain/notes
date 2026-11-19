
pdfcraft file.pdf (only file paths, nothing else)	No new instance. The paths are sent over the socket to the running PdfCraft, they open as tabs there, and the new process exits.

pdfcraft (no files)	New instance + window. Hand-off is only attempted when files were named: may_hand_off = !new_window && !files.is_empty() && options.is_empty() ...

pdfcraft --new-window file.pdf	New instance + window, by design.