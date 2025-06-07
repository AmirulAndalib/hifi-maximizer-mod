## Change logs

# v2.5.13
* Nullifying the volume listener for no compressing audio (maybe a peak limiter) on Motorola devices
* Changed an error message for no Magisk mirrors

# v2.5.12
* Tuned for POCO F3 and other "kona" board devices by adjusteding their core control parameters
* Improved and fixed GPU boosting for recent Qcomm and Mtk SoC's
* Fixed the audio policy configuration template for Tensor devices

# v2.5.11
* Tuned for POCO F6 (optimized for the ISIS kernel)
* Tuned for POCO F6 (optimized for the stock kernel, but not for the ISIS kernel)
* Tuned for POCO F3 (Android 15)
* Fixed for InfiR kernel about VM tunables

# v2.5.10
* Adapted to run with my new module "Audio Samplerate Changer"

# v2.5.9
* Optimized I/O scheduler tunables for POCO F6
* Added a support for Tensor G4 (zumapro)
* Tuned I/O scheduler tunables especially for "resampling-for-cheapies"
* Fixed an always 192 kHz USB  audio output mode for Pixel 8 and 9 series
* Changed the USB offload driver configuration of Tensor devices to be automatic max. detection
* Changed a mirroring warning for incompatible Magisk v28.0; Please use [Compatible magisk-mirroring](https://github.com/Magisk-Modules-Alt-Repo/compatible-magisk-mirroring) and Magisk v28.0 together
* Added better re-sampling parameters for very high performance devices

# v2.5.8
* Added disabling Dolby control support for USB DAC's on HyperOS not to reboot
* Excluded "MotorolaSettingsProvider" on Motorala devices only for avoiding their bootloop
* Changed the USB period_us from 2250 usec to 2000 usec to optimize for 48 kHz Opus tracks (recent majority)
* Adjusted jitter optimizations and others for YTM's format change from AAC (141; 44.1 kHz & 256 kbps cbr stereo) to Opus (774; 48 kHz & 256 kbps vbr stereo)
* Added new props "audio.safemedia.force=false" and "audio.safemedia.csd.force=false"
* Fixed above disabling Dolby control support (manufacturer mismatch)

# v2.5.7
* Changed head ahead buffer sizes from 16960 kB to 17000 kB to reduce I/O jitter
* Adjusted NrRequests of I/O scheduling
* Changed dirty_ratio and dirty_background_ration to be 100 to reduce jitter
* Adjusted re-sampling parameters for old devices
* Changed adjustSoC_mq for A14 and later clover not to round I/O parameters
* Adjusted cfq I/O parameters for SDM69x devices
* Changed the way how to get the actual audio policy file path in the service phase because some ROM's fail to execute "dumpsys" in the phase

# v2.5.6
* Added "compatible Magisk-mirroring" message for incompatible Magisk variants

# v2.5.5
* Tuned the USB period size for SDM845 devices (2500 usec to 2250 usec)
* Tuned the USB period size for other devices (to 2250 usec)
* Fixed logically wrong selinux prop settings (no meaning for magisk's magic mount mechanism)
* Added checking incompatible Magisk variants

# v2.5.4
* Tuned the USB period size for Tensor devices (2625 usec to 2250 usec)
* Fixed for Pixel 8's

# v2.5.3
* Changed the re-sampling parameters for Galaxy S4 to the general purpose ones (optimized for 3.5mm jack; not USB DAC's)
* Reduced I/O scheduling jitter on Tensor and SDM660 devices
* Reduced CFQ I/O scheduling jitter on Qcomm devices

# v2.5.2
* Tuned tunables of I/O scheduler
* Added warning messages for unneeded magisk modules

# v2.5.1
* Stopped Tensor device's AOC daemon for reducing significant jitter
* Optimized "extras/jitter-reducer.sh" for reducing I/O scheduling jitter on Tensor devices

# v2.5.0
* Optimized for Tensor devices by tuning GPU & I/O scheduling and replacing their stock audio policy configuration
* Hid preinstalled "Digital Wellbeing" feature for reducing significant jitter (please uninstall this manually if remaining as a usual app)

# v2.4.2
* Optimized "extras/jitter-reducer.sh" for reducing I/O scheduling jitter
* "extras/jitter-reducer.sh" now confirms and sets the cpu scaling max freq to its available max (sometimes the scaling max freq has been lowered before by a controller on some devices)

# v2.4.1
* Added support for ColorOS (experimental)

# v2.4.0
* Fixed some SELinux related bugs for Magisk v26.0's new magic mount feature
* Diabled pre-installed Moto Dolby features for reducing large jitter caused by them

# v2.3.2
* Added support for Tensor devices to bypass their spatial audio feature for reducing jitter distortion

# v2.3.1
* Added support for MTK A12 vendor primary audio HAL for reducing USB audio jitter
* Fixed a bug of DRC removing on phh GSI's (umounted in the boot process of phh GSI's)

# v2.3.0
* Nullified volume listener libraries in "soundfx" folders for disabling slight compression (maybe a peak limiter only on Qcomm devices).
Tuned for "mq-deadline", "kyber" and "none" I/O scheduler (latest kernel common schedulers?)
* Added support to the Nyx kernel 4.19
* Restructured source codes to be sharable with the jitter-reducer.sh in USB_SampleRate_Changer, audio-misc-settings and drc-remover

# v2.2.1
* Adjusted a USB transfer period of the USB HAL driver for reducing jitter

# v2.2.0
* Tuned kernel tunables by assuming an audio scheduling tunable "vendor.audio.adm.buffering.ms" to be "2"
* Adjusted a USB period to reduce jitter

# v2.1.8
* Disabled the Android doze system itself for reducing jitter considerably even though battery optimizations of app's are effective
* Tuned kernel tunables for SDM 8 series, MTK Dimensity's and Galaxy S4 (LineageOS 18.1)

# v2.1.7
* Changed resampling parameters for A12 or later (not having an aliasing processing bug)
* Tuned I/O scheduler tunables

# v2.1.6
* Improved tunable values of the deadline I/O scheduler

# v2.1.5
* Fixed a bug that DRC was not detected when updating from an old module
* Tuned parameters of the I/O scheduler

# v2.1.4
* Resampling quality changes from attenuation 140dB & length 320 to 160dB & 480

# v2.1.2
* Improved AudioFlinger's resampling quality (stopband 140dB, cutoff 91%)

# v2.1.1
* Enhanced the vm jitter reducer to handle "swap_ratio" and "swap_ratio_enable" for Snapdradons
* Optimized tunables of the I/O jitter reducer
* Added LICENSE

# v2.1.0
* The GPU frequency became to be fixed really at the max frequency for Qualcomm Soc and MediaTek SoC
* I/O scheduler tunables were optimized for audio clearness

# v2.0.5
* nr_requests was optimized

# v2.0.4
* Optimized I/O jitter reducer and fixed a bug disabling effects framework under PHH GSI's

# v2.0.2
* I/O tunables improved

# v2.0.1
* Initial public release

# v2.0.0
* Initial public pre-release
* Supported audio policy configuration XML files for "disable a2dp offload", "force-disable a2dp offload", and so on

# v1.4.0
* Moved scattered functions into "functions.sh" together, and treated IO Schedulers more rigorously

# v1.3.0
* Realme support (/proc/sys/vm/direct_swappiness)

# v1.2.0
* Stopped camera servers interfering in jitters on audio outputs, and reformatted source codes

# v1.1.0
* Stopped the EAS+ scheduling feature for MediaTek CPUs

# v1.0.0
* Initial limited release

##
