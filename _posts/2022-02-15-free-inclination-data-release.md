---
layout: distill
title: Free inclinations for main-belt TNOs
date: 2022-02-17
description: download the original data from our recent ApJS paper
datatable: true

authors:
    - name: Yukun Huang
      affiliations:
        name: PHAS, UBC
    - name: Brett Gladman
      url: "https://www.astro.ubc.ca/people/gladman/"
      affiliations:
        name: PHAS, UBC
    - name: Kat Volk
      url: "https://katvolk.com/wp/"
      affiliations:
        name: LPL, UA

toc:
    - name: Free Inclination Table
    - name: Table Descriptions
    - name: Pre-computed Forcing Poles and How to use it


---

**Note.** Please read our [paper]() before using the <a href="{{ site.baseurl }}/download/ifree/ifree_release.csv" target="_blank" rel="noopener noreferrer">table</a> and the <a href="{{ site.baseurl }}/download/ifree/ifree.tar.gz" target="_blank" rel="noopener noreferrer">script</a>.

## Free Inclination Table


The following interactive data table includes barycentric orbital elements and free inclinations for main-belt TNOs (39.4 < a < 47.7 au). You can search for any TNO by their name (e.g. Arrokoth), number (2014 MU69), or provisional designation (486958). You can also sort the table by clicking on the column title.

Check out [Table Descriptions](#table-desciptions) for detailed descriptions of each column.

Click **<a href="{{ site.baseurl }}/download/ifree/ifree_release.csv" target="_blank" rel="noopener noreferrer">here</a>** to download the table in `.csv` format.

<br />

<script>
$("body").css("display", "none");
$("body").hide();
</script>
<!-- <span id="loader" class="loader">
<span id="loader-inner" class="loader-inner">
</span></span> -->
<div id="table-box" class="table-box l-page">

{% include_relative ifree_table.html %}

</div>


<script>
$(document).ready(function () {
        $('#ifree-table').DataTable( {
        deferRender:    true,
        scrollX: true,
        paging: true,
        searching: true,
        scrollCollapse: true,
        scroller:       true,
        pageLength: 10,
        columns: [
        { title: "Full Name", data: "Name", "width": "120px"  },
        { title: "a (au)", data: "a", "width": "60px" },
        { title: "e", data: "e", "width": "50px"},
        { title: "Inclination (deg)", data: "inc", "width": "60px"  },
        { title: "Omega (deg)", data: "Omega", "width": "80px" },
        { title: "omega (deg)", data: "omega", "width": "80px" },
        { title: "M (deg)", data: "M", "width": "80px" },
        { title: "Distance (au)", data: "dist", "width": "80px" },
        { title: "H (mag)", data: "H", "width": "30px" },
        { title: "RESO", data: "RESO", "width": "30px" },
        { title: "Free Inclination (deg)", data: "Ifree", "width": "80px" },
        { title: "Free Inclination Range (deg)", data: "IfreeRange", "width": "80px" },
        { title: "Forced q (deg)", data: "qForced", "width": "60px" },
        { title: "Forced p (deg)", data: "pForced", "width": "60px" },
        { title: "OSSOS++", data: "OSSOS", "width": "80px" },
        { title: "DES", data: "DES", "width": "80px" },
        { title: "ID", data: "ID", "width": "60px" },],
        initComplete: function () {
            // $("#loader").hide(400);
            $("body").fadeIn(1000);
            }
    });});
</script>

## <a name="table-desciptions"></a>Table Descriptions

| Column names          | Units | Desciptions                                                                                                                                                                          |
| --------------------- | ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Full Name             |       | Full name of the TNO; designation in bracket                                                                                                                                         |
| a                     | au    | Semimajor axis of nominal orbit                                                                                                                                                      |
| e                     |       | Eccentricity                                                                                                                                                                         |
| Inclination           | deg   | Ecliptic inclination                                                                                                                                                                 |
| Omega                 | deg   | Longitude of ascending node                                                                                                                                                          |
| omega                 | deg   | Argument of perihelion                                                                                                                                                               |
| M                     | deg   | Mean anomaly                                                                                                                                                                         |
| Distance              | au    | Barycentric distance                                                                                                                                                                 |
| H                     | mag   | Absolute magnitude <d-footnote>retrived from JPL SBDB; these values are just approximated magnitudes and are not linked to a specific filter</d-footnote>                            |
| RESO                  |       | Dynamics flag <d-footnote>-1 = scattering; 0 = non-resonant-classical; >0 = the exactly resonant ratio, e.g. `74` stands fro the 7/4 mean-motion resonance with Neptune</d-footnote> |
| Free Inlination       | deg   | Free inlination from double averaging                                                                                                                                                |
| Free Inlination Range | deg   | Free inlination range over 10 Myr integration time                                                                                                                                   |
| Forced q              | deg   | q component of the forcing pole <d-footnote>$q_\text{forced} = I_\text{forced} \cos{(\Omega_\text{forced})}$</d-footnote>                                                            |
| Forced p              | deg   | p component of the forcing pole <d-footnote>$p_\text{forced} = I_\text{forced} \sin{(\Omega_\text{forced})}$</d-footnote>                                                            |
| OSSOS                 |       | OSSOS++ internal designation                                                                                                                                                         |
| DES                   |       | DES internal designation                                                                                                                                                             |
| ID                    |       | JPL Small-Body database identifier <d-footnote>For a numbered TNO, ID gives its designated number; For an unnumbered TNO, ID gives its compact provisional designation</d-footnote>  |


**Note.** The six orbital elements (a, e, Inclination, Omega, omega, M) and the distance are barycentric and in the IAU76/J2000 ecliptic reference frame, referring to epoch JD 2459400.5 (July 5 2021 UT). Both free inclination and free inclination range are independent of the choice of reference frame. The absolute magnitude H, ID and Full Name are directly retrieved from [JPL Small-Body Database](https://ssd.jpl.nasa.gov/tools/sbdb_query.html) on Oct. 5th, 2021; these values could change as the MPC receives additional observations. This table is also downloadable **<a href="{{ site.baseurl }}/download/ifree/ifree_release.csv" target="_blank" rel="noopener noreferrer">here</a>**.

***

## Pre-computed Forcing Poles and How to use it

To help the reader quickly estimate the corrent free inclinations for future TNOs, we provide a downloadable data file, in which the forcing pole compentes q and p are precomputed in a (a, e, I, 	ω) 4-dimensional grid. We also provide a Python scirpt to read the file and the find the closet data point for any give orbit, which the reader can then use to estimate the free inclination that would be given by the double average method.

Click **<a href="{{ site.baseurl }}/download/ifree/ifree.tar.gz" target="_blank" rel="noopener noreferrer">here</a>** to download both the data file and the Python script.

| Axis Names  | Ranges           | Grid sizes | Dimensions |
| ---------- | --------------- | --------- | --------- |
| a          | (39.4, 47.7) au | 0.1 au    | 84        |
| e          | (0, 0.25)       | 0.01      | 26        |
| I          | (0, 40) deg     | 2 deg     | 21        |
| ω          | (0, 90) deg     | 10 deg    | 10        |
| Total size |                 |           | 458,640   |

**Note.** This simplified method can only be trusted if the TNO:
1. is a non-resonant and non-scattering object within the given orbital ranges,
2. stays away from secular resonances (in other words, the forcing pole is relatively small),
3. has a current inclination computed at the current epoch.

We have tested the file and confirmed that for TNOs that meet these three requirements, this script yields free inclination to a precision of ~0.1° compared to that computed by double average.