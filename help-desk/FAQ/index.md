# FAQs

First, we are sharing some high-value questions, that once lived in the NGFF landing page, to then proceed with a more comprehensive list of FAQs.

## NGFF vs OME-Zarr, what is the difference?

**OME-Zarr** is the file format that the NGFF community has settled on to address issues of scalability and interoperability described below.

**NGFF** is the community-driven process for designing the next generation of bioimaging formats. NGFF brings together the community to define shared specifications, metadata standards, and best practices. OME-Zarr implements those decisions, providing a practical, open, and scalable way to store and share modern microscopy data. As the NGFF specifications evolve, OME-Zarr evolves with them — ensuring the format reflects the needs and experience of the wider community.

## What is an OME-Zarr?

An OME-Zarr is a file format optimized for storing, viewing, & sharing large images.
There are two parts to an OME-Zarr:

- **The "Zarr" part describes how the pixel data for the images are laid out**. [Zarr](https://zarr.dev) is a next-generation data format used for scientific datasets in multiple domains.
- **The "OME" part describes metadata about the pixel data.** OME stands for [Open Microscopy Environment](https://www.openmicroscopy.org/). This includes metadata such as:
  - spatial relationships
  - high content screening data
  - well data
  - [and more](#specifications-main)!

## Why would I use OME-Zarr?

In general, OME-Zarr is growing as a default [FAIR](https://en.wikipedia.org/wiki/FAIR_data) choice for storing and sharing microscopy images.

OME-Zarr files have two major benefits:

- **Standardization:** "OME-Zarr" is a "Zarr" with embedded standardized metadata in the Open Microscopy Environment (OME) format.
  - **_Sharing_**: It eases cross-organization file sharing, aiding organizational collaboration and data sharing. Repositories like the [Image Data Resource](https://idr.openmicroscopy.org/) and [BioImage Archive](https://www.ebi.ac.uk/bioimage-archive/) are currently migrating to having OME-Zarr as a standard format for _all_ their data.
  - **_Interoperability_**: Standardized metadata enables the ability to "mix and match" tools from different organizations, benefiting from the strengths of multiple tools as needed.

- **Parallel access**: Chunking is inherent to "Zarr" files. This means "Zarr" files are stored in independently-accessible blocks.
  - **_Storage_**: Microscopy images can be quite large and can therefore reach Cloud system storage limits for individual files; the chunked nature of a Zarr can alleviate this issue. Some storage systems may also duplicate byte-equivalent files, so a chunked file like Zarr may save storage space.
  - **_Viewing_**: Viewers can target specific chunks to load based upon the current view, reducing lag, & enabling massive images to be viewed within browsers.
  - **_Cost_**: When viewing or reading data, the total cost of accessing a Zarr file on the cloud may be less than a more monolithic file format due to the more efficient data access patterns. Ex. A viewer can just access the chunks of the image it needs to display rather than the entire image.

Of note, both benefits contribute to **_AI-readiness_**: the standardized metadata & access patterns provide a common layer for machine-learning workflows, reducing the friction for developers to build and test models.

The [tools](#resources-tools), [data](#resources-data), and [ecosystem](#resources-ecosystem) may provide a better sense of the range of scientific use cases that may benefit from OME-Zarr. The [publications](#resources-publications) page provides a list of publications that have used OME-Zarr in their work.

## When would I not use OME-Zarr?

While the format matures, it may be frustrating to use OME-Zarr in some cases, for example:

- If you are working with small images, not planning to share them and your current tools already work well, then using OME-Zarr may not be necessary. Planned expansions to the specification (such as single-file Zarrs) will make it more convenient in these scenarios.

- If you need specific conditions for which OME-Zarr support is not mature, you may need to use a different file format.
  - Particularly, if your original file is lossy compressed, you will see a large increase in file size (about an order of magnitude) as the images are decompressed into OME-Zarr, since transferring lossy compressed tiles is not yet supported. This currently impacts most whole slide image (WSI) formats such as SVS, CZI, and NDPI, which are lossy JPEG compressed by default.

## Who is using OME-Zarr?

These are _some_ of the organizations (and their dataset pages) that are using OME-Zarr for their data.

- [Allen Institute](https://bff.allencell.org/datasets)
- biohub
- [Broad Institute](https://broadinstitute.github.io/cellpainting-gallery/overview.html)
- [EMBL - Image Data Resource (IDR)](https://idr.openmicroscopy.org/)
- [Howard Hughes Medical Institute, Janelia (HHMI)](https://openorganelle.janelia.org/)
- [Jackson Laboratory (JAX)](https://images.jax.org/)
- ... [and more](#resources-data)

## How do I use OME-Zarr?

- Already have a Zarr?
  - Check out the [tools section](#resources-tools)!
- Want to create a Zarr?
  - Check out the [tools section](#resources-tools)!
- Want to see or download a Zarr?
  - Check out the [data section](#resources-data)!
- Want to cite OME-Zarr/NGFF in your work?
  - Check out the [publications section](#resources-publications)!

## Other FAQs

## Why OME-Zarr as a format?

OME-Zarr brings many benefits over traditional file formats, such as proprietary ones or OME-TIFF: a few examples are excellent performance, suitability to current research data needs, cloud-friendliness, a dedicated community of developers, and AI-readiness.

## What problems does it solve?**

The two largest problems that led to the initial development of OME-Zarr are data streaming and metadata interoperability. Imaging data has been suffering with increasingly large files, and downloading all of a dataset to view a small part of it was a common issue aggravated by data sizes. Meanwhile, the microscopy community has long had to deal with inconsistent metadata between file formats. OME-Zarr also brings a standardized access protocol to imaging data, and offers a format that is ready to be adopted by repositories and archives.

## 3. What is the future of OME-Tiff?

OME-TIFF is not going anywhere anytime soon - a lot of legacy data exists in that format and there are no deprecation plans. However, community and developer support is increasingly limited, performance can be an issue, and the intrinsic data and metadata structures in those files are fairly limited. Further, Adobe owns the TIFF license.

## Is a converter not enough?

Conversion tools are a first step in a long-term transition to OME-Zarr. Ideally, data producers and vendors would initially enable translation of their file formats to OME-Zarr, then transitioning to providing export and import options, before fully adopting the new format.

**5. What are the benefits for adopting such a format compared to my own?**

A standardized file format provides many advantages compared to a bespoke, "home-grown" one. A wider developer base means increased stability and interoperability, benefitting the final user experience. Community support decreases the burden on any one individual and reduce development costs. Finally, OME-Zarr is uniquely suited for the modern research environment and AI-ready.

**6. What are the downsides of moving to OME-Zarr from my own format?**

As with any initiative involving community consensus, feature adoption and scope definitions can be comparatively slower, and allow for less individual ownership of the format itself. A rich ecosystem of tools and implementations also mean these can be both deep and broad, sometimes increasing the difficulty for finding the "right ones" for a given problem.

**7. Does this format work for non-microscopy data too?**

OME-Zarrs are, by definition, Zarr files with added structures defined by the OME community. These structures have been defined and developed to attend to the needs of the microscopy community, but are by no means limited to those. If you work on other kinds of large multidimensional arrays and you find the OME-Zarr metadata structures useful for your work, great! For example, the [BIDS specification supports OME-Zarr](https://bids-specification.readthedocs.io/en/stable/common-principles.html#imaging-files) as a storage format for imaging data. You might also need different kinds of structures; if you believe these would also be useful for a broader community, engaging with the RFC process is always welcome; otherwise, you might want to consider "pure" Zarr.

**8. Is OME-Zarr a stable format?**

OME-Zarr is (still) an evolving specification. Large breaking changes (i.e. changes in the binary storage format) are not currently planned for the future, but the metadata standards can (and will) evolve in ways that might be backwards-incompatible until an 1.0 release. A conversion path between versions until 1.0 is possible.

**9. What's the difference between OME, OMERO, OME-Zarr, and just Zarr?**

- OME: community developing many open-source microscopy software projects
- OMERO: one of such projects. a data management platform that uses the OME data model to unify data from many file formats
- OME-Zarr: the file format that the community has settled on to address issues of scalability and interoperability
- Zarr: the "base" file format upon which OME-Zarr builds. A general solution for storing large multidimensional arrays with the same advantages of OME-Zarr, but with fewer mechanisms to describe and annotate microscopy data.

**10. Is OME-Zarr AI-ready?**

Yes! The chunked nature of OME-Zarr and its focus on being cloud-native are particularly well-suited for tasks such as ML algorithms where individual inputs are of a small size, but large parallelism is necessary. OME-Zarr allows for excellent performance on both parallel reads and writes, while simplifying data management compared to individually managing thousands of small files.

**11. I want to convert all my data to OME-Zarr right now. Can I safely delete my proprietary files and be sure I am not losing information?**

Not yet. Pixel data is safe, but the metadata completeness is still a current issue. Vendors need to export their metadata fully, and we as a community need to push for this.

**12. Are OME-Zarr files larger than proprietary ones?**

That is often the case. OME-Zarr include multiresolution data (i.e. pyramids), which adds data. This is optional, but performance without pyramids suffer. There is a trade-off between file size and user experience in this case.

**13. Does OME-Zarr support sparse arrays and layers?**

Not yet fully. Some workarounds are possible (1D arrays, mesh formats), but this is an active area of development.