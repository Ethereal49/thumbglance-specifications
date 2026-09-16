---
license: cc0-1.0
language:
- en
pretty_name: YouTube Image Specifications
configs:
- config_name: thumbnails
  data_files:
  - split: train
    path: youtube-thumbnail-size.csv
- config_name: banners
  data_files:
  - split: train
    path: youtube-banner-size.csv
---

# YouTube Image Specifications

A dated reference dataset of YouTube thumbnail, channel banner, and profile-picture specifications, maintained by Ethereal49.

The tables accompany the image tools and size guides at [ThumbGlance](https://thumbglance.com).

## Files

- `youtube-thumbnail-size.csv`: 7 records covering video thumbnails, Shorts thumbnails, podcast playlist thumbnails, channel banners, and profile pictures.
- `youtube-banner-size.csv`: 4 records distinguishing the minimum upload canvas, recommended canvas, and desktop/mobile layout contexts.
- `README.md`: provenance, verification method, limitations, and citation guidance.
- `LICENSE`: CC0 1.0 Universal legal text.

## Sources and verification

Checked on **2026-09-16**. Each record includes its official source URL and check date. Specifications were compared with the English YouTube Help pages linked in each row:

- [Add video thumbnails on YouTube](https://support.google.com/youtube/answer/72431?hl=en), including the desktop and Android variants.
- [Manage your channel branding](https://support.google.com/youtube/answer/10456525?hl=en).

The source CSV files were retrieved from [the thumbnail table](https://thumbglance.com/youtube-thumbnail-size.csv) and [the banner table](https://thumbglance.com/youtube-banner-size.csv). The thumbnail CSV is unchanged. In the banner CSV, calculated model dimensions and simulated cropping descriptions were replaced with explicit statements that the corresponding device-specific values are not stated by YouTube. All other source values and row labels were retained. The original labels containing "simulation" identify layout contexts only; this edition supplies no simulated measurements.

Values marked "not stated" are not specified in the cited guidance. No device display measurements or estimated dimensions are included. Official reference dimensions at the minimum upload canvas do not establish device-specific safe areas at other canvas sizes. Rows were checked by reading the cited documentation, not by measuring device screenshots or testing upload limits.

CSV files use UTF-8 with a byte-order mark and a header row. Values are descriptive strings, preserving units, device distinctions, and qualifications. The two tables have different schemas and are exposed as separate dataset configurations.

## Scope and limitations

This is a dated snapshot, not an official YouTube publication. Requirements can change; consult the linked official guidance before relying on a value. Blank or undocumented requirements must not be inferred from another device or upload type.

## Citation

Ethereal49. *YouTube Image Specifications*. Checked 2026-09-16. https://github.com/Ethereal49/thumbglance-specifications. Cite a specific commit URL when a fixed snapshot is needed.

## License

This dataset is dedicated to the public domain under **CC0 1.0 Universal** (`cc0-1.0`); see [LICENSE](LICENSE). The dedication applies to this dataset and does not change the terms of the linked source websites or imply endorsement by YouTube.
