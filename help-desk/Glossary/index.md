
## Glossary

Jump to:
[A](#a) · [B](#b) · [C](#c) · [D](#d) · [E](#e) · [F](#f) · [G](#g) · [H](#h) · [I](#i) · [J](#j) · [K](#k) · [L](#l) · [M](#m) · [N](#n) · [O](#o) · [P](#p) · [Q](#q) · [R](#r) · [S](#s) · [T](#t) · [U](#u) · [V](#v) · [W](#w) · [X](#x) · [Y](#y) · [Z](#z)

---

### A

**Array** - A collection (or list) or multiple items. For example, OME-Zarr files store image data as multi-dimensional arrays (meaning lists of lists of numbers).

[Back to top](#glossary)

### B

**BIDS** - Brain Imaging Data Structure (BIDS) is a community-developed standard for organizing and describing neuroscientific data. The [BIDS specification supports OME-Zarr](https://bids-specification.readthedocs.io/en/stable/common-principles.html#imaging-files) as a storage format for large imaging data.

[Back to top](#glossary)

### C

**Chunk** - A chunk in OME-Zarr is an independent section of pixel data that has been separated so that it can be accessed separately from other pixel data.

**Codecs** - Codecs are the algorithms that compress and decompress chunks. They shrink the data to save space and speed up loading, and then restore it when you read it. Different codecs offer different trade-offs between size, speed, and image quality, but NGFF lets you choose the one that works best for your data.

[Back to top](#glossary)

### D

[Back to top](#glossary)

### E

[Back to top](#glossary)

### F

[Back to top](#glossary)

### G

[Back to top](#glossary)

### H

**HCS** - Dedicated layout of OME-Zarr files representing the used wells and plates for High Content Screening (HCS). The layout allows a user to efficiently address and analyze specific data from specific wells.

**HDF5** - Hierarchical Data Format version 5 (HDF5). It is a data model, file format, and library for organizing, storing, and managing large and complex data.

[Back to top](#glossary)

### I

[Back to top](#glossary)

### J

**JSON file** - A simple standardized human-readable data format for sharing data using nested key-value pairs.

[Back to top](#glossary)

### K

[Back to top](#glossary)

### L

[Back to top](#glossary)

### M

**Multiscale** - Multiscale means storing the same image at multiple resolutions (full size, half size, quarter size, etc.). This makes it easy for tools to zoom and navigate very large images quickly—just like how map apps load lower-resolution versions first, then sharpen the view as you zoom in.

[Back to top](#glossary)

### N

**NGFF** - Next Generation File Format (NGFF) is a community for solving problems related to producing open-source software for microscopy data.

[Back to top](#glossary)

### O

**OME** - Open Microscopy Environment is a consortium of universities, research labs, industry and developers producing open-source software and format standards for microscopy data.

**OMERO** - OMERO is a data management platform for storing, organizing, and sharing microscopy images. To learn more about OMERO, visit the [OMERO guides](https://omero-guides.readthedocs.io/en/latest) webpage.

**OME-NGFF** - OME-NGFF refers to the resulting efforts of the OME & NGFF communities.

**OME-Zarr** - An OME-Zarr is a standardized file format for microscopy images. More details on the [main page](#main-page).

[Back to top](#glossary)

### P

**Processing Unit** - A Processing Unit is an independent section of data that a process (like image analysis) can be run on separately. For OME-Zarr images, a processing unit could be a sub-set of the image, the entire image, or multiple images.

[Back to top](#glossary)

### Q

[Back to top](#glossary)

### R

**RFC** - Request For Comments (RFC) is a process for proposing a change to the standardized specification for OME-Zarr files.

[Back to top](#glossary)

### S

**Shard/ing** - Like [Chunks](#c), sharding is a way of breaking up pixel data for more efficient access. Shards are groups of chunks in a single object with headers describing the chunks inside.

[Back to top](#glossary)

### T

**Transformation** - Transformations describe how to place one array in the same coordinate space as another—for example, how a label mask lines up with its image, or how a lower-resolution level relates to the full-resolution one. They provide the mathematical rules (like shifts, scaling, or rotations) that let software correctly align and overlay different pieces of data.

[Back to top](#glossary)

### U

[Back to top](#glossary)

### V

[Back to top](#glossary)

### W

**Workflow** - A structured sequence of tasks designed to achieve a specific goal. In the case of OME-Zarr, a workflow is some sequence of tasks usually used for performing some type of analysis on the image data.

[Back to top](#glossary)

### X

[Back to top](#glossary)

### Y

[Back to top](#glossary)

### Z

**Zarr** -- A file format, see the [main page](#main-page) for more information about what a Zarr is and the benefits of using Zarr.

**Zarr Group** - A Zarr group is like a folder inside a dataset. It can hold arrays, metadata, or other groups, helping organize complex data into a clear hierarchy. Think of it as a way to keep all related images and information neatly together.

[Back to top](#glossary)

If you think any term is missing or needs to be updated, please open a PR to the [ngff-website repository](https://github.com/ome/ngff).
