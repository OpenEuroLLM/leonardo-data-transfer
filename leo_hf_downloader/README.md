You can use download.py to create a command for using a datamover node to download a huggingface repo using rclone.
It will print a command starting with `ssh ...`` that you can run on a leonardo login node.


Example output for downloading fineweb-2
```bash
# 2025/07/09 15:02:33 NOTICE: Config file "/home/.rclone.conf" not found - using defaults
# 2025/07/09 15:02:39 NOTICE: Time may be set wrong - time from "cdn-lfs-us-1.hf.co" is 306h34m3.435898448s different from this computer
# Transferred:       38.997 GiB / 38.997 GiB, 100%, 1.262 GiB/s, ETA 0s
# Checks:               350 / 350, 100%
# Transferred:           19 / 9241, 0%
# Elapsed time:        39.0s
# Transferring:
#  *         data/arb_Arab/train/000_00001.parquet:  0% /off, 198.771Mi/s, -
#  *         data/arb_Arab/train/000_00004.parquet:  0% /off, 172.021Mi/s, -
#  *         data/arb_Arab/train/001_00000.parquet:  0% /off, 211.299Mi/s, -
#  *         data/arb_Arab/train/001_00001.parquet:  0% /off, 210.342Mi/s, -
#  *         data/arb_Arab/train/001_00002.parquet:  0% /off, 213.998Mi/s, -
#  *         data/arb_Arab/train/001_00003.parquet:  0% /off, 0/s, -
#  *         data/arb_Arab/train/001_00004.parquet: transferring
#  *         data/arb_Arab/train/002_00000.parquet: transferring
```

The progress indicator is a bit screwed because we do not want to send a head request to hf for every file, so it does not know the file sizes and cannot give you an estimate.