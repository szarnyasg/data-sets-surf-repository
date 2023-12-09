# LDBC benchmark data sets

The LDBC benchmark data sets are stored under [SURF's CWI repositories](https://repository.surfsara.nl/community/cwi).

:bulb: The LDBC SNB Business Intelligence (BI) workload's data sets are stored in Cloudflare R2. See the links to the [BI data sets](https://github.com/ldbc/ldbc_snb_bi/blob/main/snb-bi-pre-generated-data-sets.md).

:bulb: The LDBC SNB Interactive v2 workload's data sets are stored in Cloudflare R2. See the links to the [Interactive v2 data sets and update streams](https://github.com/ldbc/ldbc_snb_interactive_impls/blob/main/snb-interactive-pre-generated-data-sets.md).

## Usage

The data sets are [stored on tape](https://servicedesk.surfsara.nl/wiki/display/WIKI/Data+Archive#DataArchive-What?-Thetapeback-endandtheDataMigrationFacility(DMF)), therefore, you may have to stage them before they can be downloaded.
To do so, visit the repository of the data set and click "Request" for offline files. Staging a 20 GB file takes approx. 3-5 minutes, while staging a 200 GB one takes approx. 10-15 minutes.

To decompress, use curl and [zstd](https://github.com/facebook/zstd).

```bash
curl --silent --fail set_url_here | tar -xv --use-compress-program=unzstd
```

We provide the [`download-data-set.sh`](https://github.com/ldbc/data-sets-surf-repository/blob/main/download-data-set.sh) script, which attempts to download the data set and stages it to disk if necessary. Replace the `data_set_url` with one of the URLs linked below in this README (right click and select Copy Link Address).

```bash
./download-data-set.sh data_set_url
```

Example:

```bash
./download-data-set.sh https://repository.surfsara.nl/datasets/cwi/snb/files/social_network-csv_basic-longdateformatter/social_network-csv_basic-longdateformatter-sf0.1.tar.zst
```

## Data sets

* [Graphalytics](graphalytics.md)
* [SNB Interactive v1 (Datagen v0.3.5)](snb-interactive-v1-datagen-v035.md)
* [SNB Interactive v1 (Datagen v1.0.0)](snb-interactive-v1-datagen-v100.md)
* [SNB Business Intelligence](snb-business-intelligence.md)
* [LSQB](lsqb.md)
* [SIGMOD 2014 Programming Contest](sigmod-2014-programming-contest.md)
