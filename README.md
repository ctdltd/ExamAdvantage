# ExamAdvantage

Free study program for ISC2, ISACA, CompTIA, EC-Council and PECB certifications, by Certification Tool and Die, Ltd. Co. (www.certificationtoolanddie.com). Each course follows its exam outline objective by objective: a study page for every topic with a Deep Dive, a Real-World Example and an Exam Tip, practice questions with an explanation for every answer, progress tracking, review scheduling, read-aloud and a continuing-education report (CPE, CEU, ECE or CPD, depending on the certifying body). ExamAdvantage works alongside Examulator, the practice-exam program: each can open the matching topic or objective in the other.

This repository holds the program downloads. Courses are published separately, in ctdltd/ExamAdvantage-Courses: the app lists them and downloads the ones you want to study. 

You can read more about ExamAdvantage on our website: certificationtoolanddie.com/exam-advantage

## Downloads

Get the files from the [latest release](https://github.com/ctdltd/ExamAdvantage/releases/latest).

| File | For |
|---|---|
| ExamAdvantage2-Program-win_x64-{version}.zip | Windows 10/11 (x64; also runs on Windows on Arm) |
| ExamAdvantage2-Program-osx_arm64-{version}.zip | macOS on Apple Silicon |
| ExamAdvantage2-Program-osx_x64-{version}.zip | macOS on Intel |
| ExamAdvantage2-Program-linux_x64-{version}.zip | Linux (x64) |
| EXAMADVANTAGE-{version}.apk | Android, for side-loading (the same app is on Google Play) |
| SHA256SUMS.txt | Checksums for every file in the release |

The PC programs are self-contained: they need no .NET, Node.js or other runtime installed.

ExamAdvantage-Program-{version}.zip, the browser version that ran on Node.js, is retired: 26312.0216 is its last release. It is available here so older users can update to the newer version to get bug fixes, but we will not be publishing further updates for it. See Moving from the browser version if you are currently on the browser version. If you are a new user, please use one of the ExamAdvantage2 zip files for installation.

## Installing

- Windows: unzip the program zip into a folder of your choice (for example C:\ExamAdvantage) and run ExamAdvantage.Web.exe. If Windows SmartScreen warns about an unrecognized app, choose More info, then Run anyway. If you're concerned about viruses, etc. then by all means please scan the installation files yourself, and do not simply run them because we're saying "trust us". (You are, after all, studying for a Cybersecurity examination! :) )
- macOS: unzip into a folder of your choice. In Terminal, in that folder, run chmod +x ExamAdvantage.Web and xattr -dr com.apple.quarantine . once, then start it with ./ExamAdvantage.Web. If macOS still refuses to run it (for example "killed" on Apple Silicon), run codesign --force --sign - ExamAdvantage.Web in the same folder and try again.
- Linux: unzip into a folder of your choice, run chmod +x ExamAdvantage.Web once, then ./ExamAdvantage.Web.
- Android: install from Google Play, or allow installs from unknown sources and open the APK.

The PC program opens in your web browser at http://localhost:5000. Keep its window (the console) open while you study; closing it stops the program. If another program already uses port 5000, start it with another port, for example ExamAdvantage.Web --urls http://localhost:5050.

Then choose a certifying body's tab and click a course to download it. Downloads are checked against their published SHA-256 before they are installed.

## Where your data is kept

On the PC, courses and your progress (progress.db) are kept in the db folder inside the program folder. On Android they are kept inside the app.

To make a copy of your progress, notes, bookmarks and preferences, use Manage progress at the bottom of the screen and choose Download backup. A backup restores on any device and in any version of ExamAdvantage, including the browser version and Android.

## Updating

- Courses: the course list shows when a newer version of an installed course is published; click it to update. Your progress is kept.
- PC programs: When you run the program, it checks for a new version in the github repo and, if one exists, asks if you want to install the update. The db folder is not in the zip, so your courses and progress stay. Make a backup first if you want to be safe.
- Android: Google Play updates the app; with the APK, install the new APK over the old one.

## Installing a course by hand

Optional, PC only: useful on a machine that can't reach GitHub from inside the program.

Download ExamAdvantage-Course-{course id}-{version}.zip from the course releases (for example ExamAdvantage-Course-ISC2_CISSP_2027-26308.01.zip). Every course published so far stays available; the course list in the program always offers the newest. Check it against that release's SHA256SUMS.txt (see below). With the program closed, copy db/{course id}.db from the zip into the program's db folder (create the folder if it isn't there), then start the program.

## Moving from the browser version

The browser version (`ExamAdvantage-Program-*.zip`, started with launch.bat or launch.sh and run on Node.js) is no longer updated; 26312.0216 is its last release. It keeps working and still downloads course updates, but new program features and fixes come only in ExamAdvantage2. To move:

1. In the browser version, choose Manage progress at the bottom of the screen and Download backup.
2. Install ExamAdvantage2 (above) and download your courses in it.
3. In ExamAdvantage2, choose Manage progress, pick the backup file and restore it.

## Checking a download:

Compare the file's SHA-256 with SHA256SUMS.txt (GitHub also shows each file's SHA-256 on the release page):

- Windows (PowerShell): Get-FileHash .\ExamAdvantage2-Program-win_x64-....zip -Algorithm SHA256
- macOS / Linux: shasum -a 256 ExamAdvantage2-Program-....zip

## Versions

Programs are YYDDD.HHmm: the year and day of the year, then the time of the release (26312.0216 = 8 November 2026, 02:16). Releases up to 26298_01 used YYDDD_VV instead. Courses are YYDDD.VV: the day of the year and a release number (26308.01).

## Support

Reddit message to u/mikedn02908, the r/ctdltd subreddit, or support@certificationtoolanddie.com. For a problem with the program, say which version and which platform you use, and what you did just before it happened.

## Changelog

Newest first. Note: This changelog shows a history for the program front-end only. To see the changelog for the courses, visit the ExamAdvantage-Courses repository.

<!-- changelog -->

### 26312.0216 - 2026-11-08

**Programs:** ExamAdvantage (browser version) · ExamAdvantage2 (Windows, macOS, Linux) · ExamAdvantage (Android APK)

The first program update since 26272_01. Full notes: [ExamAdvantage changelog](https://www.certificationtoolanddie.com/exam-advantage/changelog).

**New**
- **Five certifying bodies:** CompTIA, EC-Council and PECB join ISC2 and ISACA, each with its own tab in the course list. CompTIA CySA+ 2026 is the first new course; 22 more are listed and appear as they are published. ISC2's AI Security Certification (AISC) is listed too.
- **Deep dive subtitles:** every Deep Dive shows its own heading, and it is read aloud with the section.
- **Your language:** menus, buttons, messages and reports in Simplified Chinese, Spanish, Japanese, German, French, Korean and Portuguese (Brazil). Course text can be translated on the device on iPhone and iPad (iOS 26 and later) and on the desktop in Chrome and Edge.
- **More than one edition of a course,** side by side (for example CISSP 2024 and CISSP 2027).
- **Links with Examulator** in both directions: "Practice this objective in Examulator" and "Study this topic".
- **Continuing-education report named per body:** CPE, CEU, ECE or CPD.

**Safer and more reliable**
- Progress is never overwritten by a damaged or older copy; backups and restores are complete and take effect at once; two windows on one course merge their progress.
- Updates come from GitHub first, then Google Drive, and every download is checked against its SHA-256.
- The browser version saves progress to its server again, accepts requests only from this computer, and installs updates in stages with rollback.

**Fixes**
- The app's own fonts load as designed; charts and reading speed work with a comma decimal mark; search finds terms like 802.1X and C++.
- Android: Google ML Kit removed (smaller app; translation on Android is off for now), the launcher icon, backup export and import.

**Upgrade:** Android from the Play Store; desktop: install the new build; browser version: it updates itself. Saved progress, notes, bookmarks and backups carry over.
