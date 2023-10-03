# Position Measurement and References

| **Requested by:** | **AURA** |
|-------------------|----------|
| **Doc. Code**     | #{documentCode}       |
| **Editor:**       | Alberto Izpizua         |
| **Approved by:**  | Julen García         |

## Index

- [Position Measurement and References](#position-measurement-and-references)
  - [Index](#index)
  - [Introduction](#introduction)
  - [Encoder Head data](#encoder-head-data)
  - [Head reference offset calculation](#head-reference-offset-calculation)
  - [Azimuth Cable Wrap](#azimuth-cable-wrap)

## Introduction

This document will show how to manage the references in the encoder (EIB) to set the absolute position for each head and for the telescope.

First a brief introduction to head data is shown, and how the EIB calculates the references to get the absolute position.
Then the calculation of the head references offset is shown. This procedure will make that all heads read the same value as an absolute value.
Lastly, the procedure to convert this value to Telescope absolute value is used.

## Encoder Head data

As shown in the [EIB documentation](https://gitlab.tekniker.es/publico/3151-lsst/documentation/pxicontroller_documentation/-/tree/master/06%20Subsystem%20EIB), the encoder is absolute after performing a reference procedure.

At the referenced document is shown that each encoder head sends its relative position and when performing the reference procedure a reference value is sent. This value is subtracted to the relative position to get the absolute position of the head in the encoder tape. In this sense, each head sends the head relative position and the reference data to convert this position to the absolute position of the head in the tape the head is reading to.  So that, this absolute position is the absolute position of each head and each head has its own absolute position, since they are located in different positions along the tape.

The axis need to have the same position value in all the heads (or at least with a small difference between heads), to solve this issue, there is an offset. This offset must be calculated with a procedure for each axis. **The adjustment procedure must be applied if one head is adjusted in position or one is replaced.**

## Head reference offset calculation

![Alt text](Figures/ReferenceOffsetToolMainWindow.png)


## Azimuth Cable Wrap






