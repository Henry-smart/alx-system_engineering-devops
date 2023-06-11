<h1>Postmortem</h1>

 Incident Report or summary, also referred to as a Postmortem outlines the total summary of an incident the occured with a collaborative project deployed by my team of which a security issue was detected. This postmortem follows the guidelines used closely by Microsoft engineers to file reports. The report is made up of five parts, an issue summary, a timeline, root cause analysis, resolution and recovery, and lastly, corrective and preventative measures. Lets review each of these parts in detail.
<ul>
<li><h2>Issue Summary</h2></li>
<p>I was alerted on june 08, 2023 at 14:00hours WAT that the day after I forked Fix_My_Code_Challenge/0x01-challenge/ to fix the code.
After that day(01 june 2023) github constantly alerts me on email as depedance alert every 7 days gap which i percived as a bug. The root cause was the outage(Expiration) of the software version.</p>

<li><h2>Timeline</h2></li>
<p>The issue was detected start from june 02, 2023 at 13:00 AM WAT.
The issue dectected was dependancy alert because the repository I forked was fulled with the outage version of software. This incident is still present because I don't want to fix since it doesn't matter and I there is no need to debug, the software version has already expired and no longer in use.</p>

<li><h2>Root Cause</h2></li>
<p>The main cause of the issues were many but for instance I can mention few of them;

<strong>[Security]</strong>
[CRuby] Vendored libxml2 is updated to address CVE-2022-2309, CVE-2022-40304, and CVE-2022-40303. See GHSA-2qc6-mcvw-92cw for more information. [CRuby] Vendored zlib is updated to address CVE-2022-37434. Nokogiri was not affected by this vulnerability, but this version of zlib was being flagged up by some vulnerability scanners which github file tracking algorithm acknowleged, see #2626 for more information.

<strong>[Dependencies]</strong>
[CRuby] Vendored libxml2 is updated to v2.10.3 from v2.9.14. [CRuby] Vendored libxslt is updated to v1.1.37 from v1.1.35. [CRuby] Vendored zlib is updated from 1.2.12 to 1.2.13. (See LICENSE-DEPENDENCIES.md for details on which packages redistribute this library.)

<strong>[Fixed]</strong>
[CRuby] Nokogiri::XML::Namespace objects, when compacted, update their internal struct's reference to the Ruby object wrapper. Previously, with GC compaction enabled, a segmentation fault was possible after compaction was triggered. [#2658] (Thanks, @​eightbitraptor and @​peterzhu2118!) [CRuby] Document#remove_namespaces! now defers freeing the underlying xmlNs struct until the Document is GCed. Previously, maintaining a reference to a Namespace object that was removed in this way could lead to a segfault. [#2658]</p>

<li><h2>Resolution and Recovery</h2></li>
<p>The resolution and the recovery of this issue was updating the dependance rule to automatically acknowlege the changes made on the original file.</p>

<li><h2>Corrective and preventative measures</h2></li>
<p>After Updating the dependant Rule of this software, it should be able to updated instantly when alerted by the github by making the github alert ON.</p></ul>
