---
title: SXM Image Analyzer
summary: A web app to open, filter and export scanning probe microscopy (SPM/STM) images in the Nanonis .sxm format directly in the browser.
date: 2026-10-08
type: docs
math: false
tags:
  - Web app
  - Scanning probe microscopy
  - Image processing
image:
  caption: 'SXM Image Analyzer'
---

## Description

**SXM Image Analyzer** is a [Streamlit](https://streamlit.io/) app for quickly viewing and cleaning up scanning probe microscopy (SPM/STM) images saved in the Nanonis `.sxm` format, with no local installation needed. Upload a `.sxm` file (up to 200 MB) to see the image and its acquisition metadata right away.

Open the app directly via the [site link](https://sxmfkf.streamlit.app/).

## Features

### Original image

- View the raw topography image as recorded.
- Download the unfiltered image (PNG), the scan metadata (TXT) and the STM data grid (NPZ) for further analysis in Python.

### Processing

Use the **Process** tab to enhance the image interactively:

- **FFT filtering** with Gaussian, Blackman–Harris or exponential windows and an adjustable width (σ), to remove high-frequency noise.
- **Unsharp masking** with adjustable radius and amount, to sharpen molecular and atomic features.
- **Image transforms**: contrast inversion and cosine transform.

The processed image, processed raw image and metadata can be downloaded.

### Analysis (coming soon)

Dedicated analysis modes for specific adsorbates are under development: **chitosan**, **RNA**, **proteins**, **chlorophyll** and **glycolipids**.

## Tutorial

A step-by-step notebook showing how to load `.sxm` files and apply these filters in Python is available on [GitHub](https://github.com/tipiorgup/SXM-filters).


## Did you find this page helpful? Consider sharing it 🙌
