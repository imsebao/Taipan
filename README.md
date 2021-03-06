# Taipan - Web Application Security Scanner
 
 <p align="center">
    <a href="https://github.com/taipan-scanner/Taipan/releases/latest"><img alt="Release" src="https://img.shields.io/github/release/taipan-scanner/Taipan.svg?style=flat-square"></a>
    <a href="https://ci.appveyor.com/project/enkomio/taipan"><img alt="Release" src="https://ci.appveyor.com/api/projects/status/j0t1m1wm46yrgvdr.svg?style=flat-square"></a>
  </p>

_Taipan_ is a an automated web application scanner which allows to identify web vulnerabilities in an automatic fashion. This project is the core engine of a broader project which include other components, like a web dashboard where you can manage your scan or download a PDF report and a scanner agent to run on specific host. Below are some screenshots of the _Taipan_ dashboard:

<table>
 <tr>
  <td><img src="https://github.com/enkomio/Taipan/blob/master/Misc/Admin-info.png" width="200"></td>
  <td><img src="https://github.com/enkomio/Taipan/blob/master/Misc/Dashboard.png" width="200"></td>
  <td><img src="https://github.com/enkomio/Taipan/blob/master/Misc/Scan-details.png" width="200"></td>
 </tr>
 <tr>
  <td><img src="https://github.com/enkomio/Taipan/blob/master/Misc/Scan-summary.png" width="200"></td>
  <td><img src="https://github.com/enkomio/Taipan/blob/master/Misc/Scan-wizard.png" width="200"></td>
  <td><img src="https://github.com/enkomio/Taipan/blob/master/Misc/Settings.png" width="200"></td>
 </tr>
</table>

If you are interested in trying the full product, you can contact me at: aparata[AT]gmail.com

## Release Download
 - [Source code][1]
 - [Download binary][2]
 
## Download Build Release
If you want to try the dev version of Taipan without to wait for an official release, you can download the build version. This version is built every time that a commit is done and the build process is not broken. 

You can download it from the [Artifacts Directory](https://ci.appveyor.com/project/enkomio/taipan/build/artifacts).

## Using Taipan
_Taipan_ can run on both Windows (natively) and Linux (with mono). To run it in Linux you have to install **mono in version >= 4.8.0**. You can track the implementation of the new features in the related <a href="https://github.com/taipan-scanner/Taipan/projects/1">Kanban board</a>.

### Scan Profile
_Taipan_ allow to scan the given web site by specify different kind of profiles. Each profile enable or disable a specific scan feature, to show all the available profile just run _Taipan_ with the `--show-profiles_` option.

### Scan/Stop/Pause a scan
During a scan you can interact with it by set the scan in Pause or Stop it if necessary. In order to do so you have to press:

- P: pause the scan
- S: stop the scan
- R: resume a paused scan

The state change is not immediate and you have to wait until all threads have reached the desider state.

### Launch a scan
To launch a new scan you have to provide the _url_ and the _profile_ which must be used. It is not necessary to specify the full profile name, a prefix is enough. 

    Taipan.exe -p Full -u http://127.0.0.1/

Below an example of execution:

<a href="https://asciinema.org/a/166362" target="_blank"><img src="https://asciinema.org/a/166362.png" /></a>

## Taipan Components
_Taipan_ is composed of four main components: 
- Web Application fingerprinter: it inspects the given application in order to identify if it is a COTS application. If so, it extracts the identified version.
- Hidden Resource Discovery: this component scans the application in order to identify resources that are not directly navigable or that shouldn't be accessed, like secret pages or test pages.
- Crawler: This component navigates the web site in order to provide to the other components a list of pages to analyze. It allows to mutate the request in order to find not so common pathes.
- Vulnerability Scanner: this component probes the web application and tries to identify possible vulnerabilities. It is composed of various AddOn in order to easily expand its Knowledge Base.

## License

.NET Core (including the coreclr repo) is licensed under the [MIT license](LICENSE.TXT).

License: GNU General Public License, version 2 or later; see LICENSE included in this archive for details.

  [1]: https://github.com/enkomio/Taipan/tree/master/Src
  [2]: https://github.com/enkomio/Taipan/releases/latest
