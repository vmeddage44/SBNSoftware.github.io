---
lang: en
title: List of ICARUS code releases
---



List of ICARUS code releases(#List-of-ICARUS-code-releases)
============================================================================

-   **Table of contents**
-   [List of ICARUS code releases](#List-of-ICARUS-code-releases)
    -   [List of icaruscode releases](#List-of-icaruscode-releases)
    -   [Dependencies](#Dependencies)
        -   [sbndaq\_artdaq\_core quirks](#sbndaq_artdaq_core-quirks)

Here we enumerate the impressive number of code releases by the ICARUS
army.

The army has also filled a [list of
dependencies](#Dependencies), after the list of releases
below.



List of `icaruscode` releases(#List-of-icaruscode-releases)
----------------------------------------------------------------------------

[ **Transient and temporary release manager**: [Tracy
Usher](mailto:usher@slac.stanford.edu)]{style="color: red;"}

These are the `icaruscode` releases tagged until now:

  ------------- ---------------- -----------------------------------------------------------
  Version       Notes            Detailed Notes
  `v08_52_00`   Weekly release   [Release Notes](ReleaseNotes085200.html)
  `v08_43_00`   Weekly release   [Release Notes](ReleaseNotes084300.html)
  `v08_37_00`   Weekly release   [Release Notes](ReleaseNotes083700.html)
  `v08_36_02`   Weekly release   [Release Notes](ReleaseNotes083602.html)
  `v08_36_01`   Weekly release   [Release Notes](ReleaseNotes083601.html)
  `v08_34_00`   Weekly release   [Release Notes](ReleaseNotes083400.html)
  `v08_33_00`   Weekly release   [Release Notes](ReleaseNotes083300.html)
  `v08_32_00`   Weekly release   [Release Notes](ReleaseNotes083200.html)
  `v08_31_01`   Weekly release   [Release Notes](ReleaseNotes083101.html)
  `v08_22_00`   Weekly release   [Release Notes](ReleaseNotes0822_00.html)
  `v08_19_01`   Weekly release   [Release Notes](ReleaseNotes081901.html)
  `v08_14_00`   Weekly release   [Release Notes](ReleaseNotes081400.html)
  `v08_13_02`   Weekly release   [Release Notes](ReleaseNotes081302.html)
  `v08_12_00`   Weekly release   [Release Notes](ReleaseNotes081200.html)
  `v08_11_00`   Weekly release   [Release Notes](ReleaseNotes081100.html)
  `v08_10_01`   Weekly release   [Release Notes](ReleaseNotes081001.html)
  `v08_07_01`   Weekly release   [Release Notes](ReleaseNotes080701.html)
  `v08_03_00`   Weekly release   [Release Notes](ReleaseNotes080300.html)
  `v08_01_00`   Weekly release   [Release Notes](ReleaseNotes080100.html){.wiki-page .new}
  `v07_11_00`   Weekly release   [Release Notes](ReleaseNotes071100.html)
  `v07_08_00`   Weekly release   [Release Notes](ReleaseNotes070800.html)
  ------------- ---------------- -----------------------------------------------------------



Dependencies(#Dependencies)
--------------------------------------------

The ICARUS code repository (`icaruscode`) currently depends on
`icarusutil`, `icarus_data`, `larsoft`, `sbndaq_artdaq_core` and
`cetbuildtools` (for building). In all releases the `icaruscode` release
tag matches the underlying `larsoft` version. Note that in general,
`icarusutil` versions are independent though generally also match. Also,
`icarusutil` is an \"optional\" dependency. So, on [Fermilab
GPVMs](Computing_resources.html#Where-to-work-interactive-nodes-GPVM)
it will be set up but offsite it will not be set up unless it is
available: usually it is not. If you are building your own `icaruscode`
with MRB, you can check out also `icarusutil` (`mrb g icarusutil`) and
when you build the area `icarusutil` will be available to you.

Summary of dependencies; all are mandatory (even when \"not necessary\")
unless otherwise specified:

-   [icaruscode]{style="color: crimson;"} is the main ICARUS simulation
    and reconstruction software repository;
-   [icarus\_signal\_processing]{style="color: crimson;"} includes
    algorithms for readout signal processing;
-   [larsoft]{style="color: crimson;"} includes, well, LArSoft; you
    won\'t go very far without this;
-   [icarus\_data]{style="color: crimson;"} includes data files of
    moderate size (e.g. for signal processing); it is often necessary,
    but not always so;
-   [genie\_xsec]{style="color: crimson;"} to allow our experiment to
    choose which GENIE cross section set to use; necessary when running
    GENIE;
-   [sbndaq\_artdaq\_core]{style="color: crimson;"} (mandatory since
    `icaruscode` [version:v08\_32\_00]{style="font: monospace;"})
    connects to data acquisition (see below);
-   [icarusutil]{style="color: crimson;"} *(optional)* includes scripts
    and facilities for job submission to the grid(s);



### `sbndaq_artdaq_core` quirks(#sbndaq_artdaq_core-quirks)

If you need to check out `sbndaq_artdaq_core` in your working area, the
effective MRB command is:

    mrb gitCheckout -d sbndaq_artdaq_core sbndaq%sbndaq-artdaq-core%sbndaq

which checks out the repository `sbndaq-artdaq-core` from the
[sbndaq](/redmine/projects/sbndaq){.project} Redmine project, using
`sbndaq` as user name as for Fermilab convention, and putting it into
`sbndaq_artdaq_core` directory because if it is true, as it is, that UPS
hates underscores, it is just as true that LArSoft build system
`cet_build_tools` hates hyphens.
