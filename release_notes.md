### Release Notes 1.5.26 Hotfix
-   allows dataset registration on errored task

### Release Notes 1.5.25 Hotfix
-   ks2task import conflict fix

### Release Notes 1.5.24 Hotfix
-   Ks2 task does not depend on ephys pulses

### Release Notes 1.5.23
- Ephys mtscomp
    - ks2 task registers first probe even if one failing
    - mtscomp task register .ch and .meta even if .cbin doesn't exist
    - move ibllib tests to tests_ibllib
    - brainbox atlas plot functions

### Release Notes 1.5.22
-   Ephys extraction:
    -   synchronisation between probes computed in the ephysPulses job
    -   spike sorting resync done directly after KS2 output
    -   unit-based metrics have their own task

### Release Notes 1.5.21: hotfix
-   create local server tasks only on raw_session.flag

### Release Notes 1.5.20
-   ephys alignment QC
-   hotfix: ibl errors inherit Exception, not BaseException
-   hotfix: partial qc task extractor keeps FPGA stim times

### Release Notes 1.5.19
-   create tasks looks for create_me.flags

### Release Notes 1.5.18
-   add Karolina's optogenetics tasks for extractions

### Release Notes 1.5.17
-   histology probe QC pipeline and final locations dataset export

### Release Notes 1.5.16  Hotfix
-   numpy needs upgrading >= 1.18

### Release Notes 1.5.15  Hotfix
-   session creation skips alyx procedure for unknown task protocol (custom projects)

### Release Notes 1.5.14
-   task extraction:
    -   Habituation QC
    -   ephys extraction StimOffTimes fix

### Release Notes 1.5.13
-   ibllib.atlas
    -   allen csv Atlas part of package is not installed in dev mode
    -   improved slicing performance
-   ephys extraction: mtscomp registers ch file on run and re-runs bis

### Release Notes 1.5.12  Hotfix
-   mtscomp registers ch file on run and re-runs

### Release Notes 1.5.11  Hotfix
-   ffmpeg nostdin option as jobs were stopped in background on a server

### Release Notes 1.5.10
-   QC base class
-   Support for task QC on FPGA data
-   TaskQC run during task extraction

### Release Notes 1.5.9
-   local server: catches error when subject is not registered in Alyx
-   ibllib.atlas.AllenAtlas
    -   re-ordered the volumes in c-order contiguous ml-ap-dv efficient coronal shapes
    -   top/bottom surface extraction

### Release Notes 1.5.8 Hotfix
-   Ephys extraction SyncSpikeSorting: specify different dir for ks2 ouput and raw ephys data

### Release Notes 1.5.7 Hotfix
-   Ephys extraction ks2: mkdir for scratch more robust

### Release Notes 1.5.6
Ephys extraction bugfixes:
-   RawEphysQC: No object "ephysTimeRmsAP" found 
-   EphysMtsComp,RawEphysQC, EphysPulses : ValueError: mmap length is greater than file size
-   Ks2: ks2 job cleans-up temp dir

### Release Notes 1.5.5
-   ONE offline mode and cache dataset table to speed up reloading of large datasets (Olivier)
-   ALF io naming conventions on loading objects (Miles)
-   KS2 Matlab ephys pipeline tasks (Olivier)
-   Support for running QC on biased and training sessions (Nico)
-   metrics_df and passed_df properties in BpodQC obj for qcplots (Nico)
-   Added missing unittest to stim_move_before_goCue metric (Nico)

### Release Notes 1.5.4 - 29/07/2020 hotfix
-   ibllib.pipes.training_preprocessing.TrainingAudio

### Release Notes 1.5.3 - 28/07/2020
-   ibllib.pipes.training_preprocessing.TrainingAudio: returns files for registration and proper status. (Olivier)
-   ibllib.atlas: compute nearest region from probe trajectory (Mayo)
    
### Release Notes 1.5.2 - 23/07/2020
-   Local server jobs:
    -   fix wheel moves size mismatch extractor error
    -   only look for raw_session.flag for ephys extraction to avoid race conditions

### Release Notes 1.5.1 - 25/05/2020
-  Ephys extraction:
    -   spike amplitudes in Volts
    -   added waveforms samples dataset to use Phy from Flatiron datasets
-  ONE performance:
    -   Metaclass implementation of UniqueSingletons for AlyxClient
    -   Multi-threaded downloads
    -   Added JSON fields methods to AlyxClient
-   QCs: Bpod and ONE QC features, basic plotting, examples

### Release Notes 1.4.14 - 2020-03-09
-   Added permutation test, comparing a metric on two sets of datasets, by shuffling labels and seeing how plausible the observed actual difference is
Sped up calculation of firing_rate
-   ephys extraction: updated extracted metrics, including a new contamination estimate and drift metrics.
-   ibllib.io.spikeglx

### Release Notes 1.4.13 - 2020-03-07
-   Hotfix: rig transfer - create probes. One variable used before assignation. 

### Release Notes 1.4.12 - 2020-03-06
-   ONE.load overwrites local file if filesizes different or hash mismatch
-   ephys extraction:
    -   registration sets the session.procedure field to acute recording
    -   bugfix synchronization on re-extraction: always recompute spike.times from spike.samples
    -   ephys registration sets the session.procedure field to acute recording
-   training extraction:
    -   added biasedVisOffChoiceWorld as training extractor
-   wheel data
    -   dropping support for wheel velocity, not extracted anymore

### Release Notes 1.4.11 - 2020-02-14
-   bugfix: Include sessions data files for ephys mock
-   bugfix: Single probe 3B gets synchronized

### Release Notes 1.4.10 - 2020-02-10
-   bugfix: Include sessions data files in pip package 

### Release Notes 1.4.9 - 2020-02-09
-   Big brainbox merge and release
-   bugfix: clusters.metrics spiking rates accurate 
-   probability left for ephys choice world contain generative probabilities, not outcomes

### Release Notes 1.4.8 - 2020-01-27
-   ONE Light Windows fixes
-   Installation documentation separates conda and virtualenv options
-   Conda yaml environement file for ibllib

### Release Notes 1.4.7 
-   ONE Light for behaviour paper data release   
-   ONE() standard syntax matching the one light examples

### Release Notes 1.4.6 
-   Alyx registration: add md5, version and filesize to the pipeline registration
-   Data Patcher: allows to register data from anywhere through FTP/SSH/GLobus
-   ONE Light for behaviour paper data release 

### Release Notes 1.4.5 Hotfix
-   Ephys extraction: left probability bug when sequence was 0 - fixed

### Release Notes 1.4.4
-   Ephys extraction:
    -   left probability extracted properly
    -   add robustness to audio fronts extraction in FPGA
-   Passive stimulus: raw data registered in pipeline
-   Training extraction: microphone extraction for habituation sessions
-   ALF: specific to_dataframe method for Bunch
    
### Release Notes 1.4.3 Hotfix
-   Ephys extraction: handle fringe case where recording is interrupted in the middle
-   Wheel extraction: if rotary encoder version is outdated and stores data in the wrong unit, auto-detect and output in seconds even for new versions

### Release Notes 1.4.2
-  FPGA/bpod events synchronization performed even when their counts do not match
-  Updated requirement versions for mtscomp and phylib

### Release Notes 1.4.1
-   wheel extraction outputs a timestamps attribute, not times
-   make the wheel extraction more robust

### Release Notes 1.4.0
-   Ephys extraction:
    -   un-synchronized spike sortings not uploaded on flat-iron
    -   reaction times extracted
    -   valve-open times bugfix
-   Wheel extraction:
    -   training wheel position and timing are now correct
    -   ephys & training: units: radians mathematical convention
-   ONE:
    -   Alyx client handles pagination seamlessly

### Release Notes 1.3.10 Hotfix
-   cross-platform get of session folder for rig computer copy to server

### Release Notes 1.3.9
-   spikeglx.verify_hash() method to check file integrity after transfers/manipulations
-   create wirings settings files on ephys computer transfer to server

### Release Notes 1.3.8
-   Ephys Extraction:
    -   duplicate probe.trajectories bugfix
    -   extraction works with unoperational fram2ttl at beginning of ephys session
    -   clusters.metrics.csv has consistent size with npy cluster objects
    -   ephys transfer: create ephys extraction flags after the transfer is complete

### Release Notes 1.3.7 hotfixes- 21-NOV-2019
-   Rename spike.times on failed sync to reflect the clock as per ALF convention
-   sync 3A fails if first cam event whithin 200ms of start
-   compress ephys goes through a tempfile to not interfere with transfers/globbing

### Release Notes 1.3.6 - 20-NOV-2019
-   Ephys Extraction (phylib)
    -   convert ks2 amplitudes to volts for spikes.amps, clusters.amps. templates.waveforms, clusters.waveforms to get uV
    -   generates Cluster UUIDs file
    -   individual spike depths computed from PC features  
-   Ephys Synchronization
    -   use frame2TTL split for 3A by default, if not found look for right_camera
    -   output individual probe sync in ALF timestamps format

### Release Notes 1.3.5 - 18-NOV-2019
-   registration ignores ks2alf probes subfolders
-   fix typo in raw qc dataset types

### Release Notes 1.3.4 - 18-NOV-2019
-   Alyx registration adds the relative path to session root as dataset.subcollection
-   Ephys extraction:
    -   split probe folders output alf/probe00 and alf/probe01 instead of merge
    -   outputs templates.waveforms and clusters.waveforms in sparse arrays
    -   outputs probes.description and probes.trajectory
    -   renamed the raw ephys QC output
    -   outputs clusters.metrics
-   Bugfixes:
    -   3B raw ephys QC output ap.file not found on nidq object
    -   3A sync probe threshold set to 2.1 samples

### Release Notes 1.3.1 - 12-NOV-2019
-   transfer scripts from ephys/video/rig computers to local servers
-   bugfix spigeglx.glob_ephys_files when metadata file without ap.bin file

### Release Notes 1.3.0 - 11-NOV-2019
-   Transfer rig data takes into account session type (ephys/training) to create flags
-   Ephys video compression in pipeline
-   Ephys audio compression in pipeline

### Release Notes 1.2.9
-   Ephys extraction: provide full 3B default wirings if files do not exist.

### Release Notes 1.2.8
-   Ephys extraction: merge sync ephys in the pipeline overwrites ks2_alf directory if it already exists

### Release Notes 1.2.7
-   Added `biasedScanningChoiceWorld` task to biased extractor for Zador lab

### Release Notes 1.2.6
#### feature/ephys_compression
- `spikeglx.Reader` supports mtscomp ephys binaries
- server pipeline for compression of ephys files
#### feature/peths
- `brainbox.singlecell.peths` with tests
- `brainbox.processing.bincount2D` supports aggregation on fixed scale
- simple examples script and notebook

### Release Notes 1.2.5
- examples/brainbox/plot_peths.py: by Matt. W.
- examples/brainbox/rasters by Michaël S.
- Allen Atlas framework and probe registration base functions
- server pipeline for audio extraction of training sessions
