JPS Workflow Narrative instructions
===================================

| This document provides the JPS user with a workflow-based overview of
  the manuscript production process in the October 2017 release of
  Impact Journals, JPS. The tasks described here are organized in the
  same order as they are encountered in the workflow to the maximum
  extent possible. Please keep in mind that some tasks or task chains
  may run in parallel. Please refer to the workflow diagram for further
  information.

.. important:: This is not a specific guide for each task. Instead, this
  document should give you a general idea of how the tasks are arranged
  and what’s the overall purpose of each task, as well as serve as a
  point of reference for the various naming conventions used throughout
  the system. For specific instructions associated with each task, please refer to
  the linked videos.
.. note:: the password to access all videos is 1100316

.. raw:: html
 <video controls src="_static/JPSintro.mp4"></video>

| Video: `JPS
  Intro <http://oncotarget.screencasthost.com/watch/cbQYosI34l>`__

ASSIGN TO VENDOR
================

| Roles: Production manager
| The Assign to vendor task (system [ID] 117) open automatically when an
  accepted paper is imported from the submission system. During this
  task, the production manager reviews the originally submitted
  manuscript to collect and act upon the following information:
| - Whether the manuscript was assigned to the correct section
| - Whether a fee waiver or any English editing fees may apply
| - What type of license/author agreement document should be sent to the
  authors
| - Whether the manuscript section places any restrictions on which
  vendor it may be assigned to
| The production editor then records the results of their inquiry using
  the designated system functions and assigns the manuscript to the
  composition vendor. Before completing the task, the production editor
  has an option to add special instructions to the composition vendor.
  Three tasks open automatically upon completion of the ASSIGN TO VENDOR
  task: `AWAITING LICENSE TO PUBLISH <#awaiting-license-to-publish>`__,
  `AWAITING PAYMENT <#awaiting-payment>`__, and
  `COMPOSITION <#composition>`__.
| Video: `Assigning the manuscript to a vendor - full
  workflow <http://oncotarget.screencasthost.com/watch/cbQYYhI3Ms>`__

AWAITING LICENSE TO PUBLISH
===========================

| Roles: Record office, Author
| Immediately upon completion of the `ASSIGN TO
  VENDOR <#assign-to-vendor>`__ task, JPS opens a query and notifies the
  authors regarding the required license to publish or author agreement
  document. The system sends scheduled reminders to the authors until
  the complete the query response. Upon completion of the query
  response, the system notifies the Forms Office staff that a document
  was submitted and asks them to review it. The Forms Office staff
  reviews the document and either reinitiates the AWAITING LICENSE TO
  PUBLISH task if the provided document is not suitable, or records the
  status of the form as received and completes the task. Note that this
  task blocks the `EPUB IN OJS <#epub-in-ojs>`__ task: it won’t open
  until this task is complete.

AWAITING PAYMENT
================

| Roles: Payment office, Authors
| Awaiting payment is a multi-step task that runs in parallel with the
  rest of the workflow. This task opens when the `ASSIGN TO
  VENDOR <#assign-to-vendor>`__ task is completed and involves
  generating the initial invoice, adjusting it per authors’
  requirements, recording payments (manually for checks, wire transfers,
  and ACH, automatically for credit cards), and providing receipts and
  paid invoice documents.

COMPOSITION
===========

| COMPOSITION is a group of tasks that are arranged together to achieve
  the goals of creating the page proofs and obtaining feedback on these
  proofs from the manuscript’s authors.
| Video: `JPS - Author proofing
  process <http://oncotarget.screencasthost.com/watch/cbQrrFIZ6F>`__

EXPORT FILES FOR INITIAL PROOF
------------------------------

| Role: System
| This is an automated system task during which JPS gathers the files
  transferred from the submission system, organizes them into an
  archive, and notifies the composition vendor assigned to the article
  in the `ASSIGN TO VENDOR <#assign-to-vendor>`__ task that the page
  proofs need to be prepared. The files will be packaged together in a
  ZIP archive names as follows: OT_[MS#]_orig.zip
| The following files are supplied to the vendor if present in the
  original accepted submission:
| a. Article/Source = OT_[MS#]_[ID]_ms.doc/docx
| b. Figures/Source = OT_[MS#]_[ID]_figure1.ext
| c. Tables/Source = OT_[MS#]_[ID]_table1.ext
| d. Supplemental material/Source = OT_[MS#]_[ID]_supp1.ext
| e. V[ID]eo/Source = OT_[MS#]_[ID] \_v[ID]eo.ext
| f. Dataset/Source= OT_[MS#]_[ID] \_dataset1.ext
| g. Merged PDF = OT_[MS#]_[ID].pdf
| Note: [MS#] is the six-digit manuscript number assigned by the
  submission system. Revision markers (R1, R2) are not included in this
  number. [ID] is a sequential identifier assigned to each file in the
  package, it can be ignored.
| Here are the contents of a typical file package:
| |image0|
| As soon as JPS successfully exports the file package to the FTP
  server, it will notify the composition vendor that the article is
  ready for the page proofs. The Awaiting import – initial proof task
  will open automatically.

AWAITING IMPORT - INITIAL PROOF
-------------------------------

| Role: Vendor
| During this task, JPS waits for the composition vendor to upload
  prepared page proofs to the FTP so that it can pass them on to the
  authors. The vendor prepares the PDF page proofs for the main article
  and any supplementary files that may be present. To ensure the
  successful import of the page proofs, the files must be named as
  follows:
| a. article proof = OT_[MS#]_proof.pdf
| b. first supplementary materials proof (if present) =
  OT_[MS#]_supplementary_proof.pdf
| c. Any additional supplementary materials proofs (if present) =
  OT_[MS#]_supplementary_proof[ID].pdf
| Note: [ID] is a sequential number of the supplementary proof file,
  starting with 2. So, if an article requires three PDF supplementary
  proof files, the ID will be 2 for the second file and 3 for the third
  file.
| All of these PDF files must be zipped together with the archive named
  as follows:
| OT_[MS#]_proof.zip
| Here’s an example of a typical package containing author proofs:
| |image1|
| The vendor then uploads the complete package to the JPS FTP.
| Upload directory: /home/JPS/To_JPS
| For the current FTP credentials, please contact the production
  manager.
| During this task, the vendor has an option to open a query to the
  authors via the Send email interface.
| After the proofs import successfully, the author will be notified and
  the Author proof review task will open.

AUTHOR PROOF REVIEW
-------------------

| Role: Authors
| During the author proof review task, the authors have a chance to
  review the page proofs produced by the composition vendor and provide
  their corrections. After the system imports the page proof package
  uploaded by the vendor, it will open a query to the authors. The
  authors will be asked to review each of the page proof files and
  provide their comments. Alternatively, authors have the option to sign
  off on the proofs without requesting any corrections.

EXPORT FILES FOR REVISED PROOF
------------------------------

| Role: System
| This is, once again, an automated task. After the authors complete the
  proof review task, JPS will check the status of the Awaiting license
  to publish task. If the task is not complete, the system will continue
  checking and reminding the authors about the outstanding
  license/author agreement.
| Important! The workflow will not proceed to the next task until the
  Awaiting license to publish task is completed.
| Once the Awaiting license to publish task is completed (or immediately
  if it was completed at an earlier point), JPS will process and package
  the author proof response and then upload it to the FTP. As soon as
  the upload is finished, JPS will notify the vendor and open the ePub
  in OJS task. At this point, the COMPOSITION process is finished.
| The response files will be in the following directory:
  /home/JPS/From_JPS
| The files will be packaged in a ZIP archive and named as follows:
  OT_[MS#]_proofrev.zip
| Inside the package, there will be a readme file containing the text
  response, as well as any other files the authors chose to include with
  their proof revisions. Here’s a typical proof response package:
| |image2|

EPUB IN OJS
===========

| Role: Vendor
| As a reminder, this task can only open if the Awaiting license to
  publish task is complete. During this task, the vendor will prepare
  the article files for publication in OJS (“on the website”). This
  process requires that the vendor review and implement any changes
  requested by the authors during the Author proof review task. It also
  requires that the vendor prepare the publication-ready PDF, HTML, and
  any supplementary files and upload them to OJS. The vendor will also
  enter the article metadata and provide the HTML code for the front
  matter of the article. Overall, the steps that the vendor must take
  during this task outside of JPS are the standard steps required for
  article publication under the old workflow.
| Once the vendor has published the article in OJS, they also must mark
  this task as complete in JPS. During this process, they will be
  required to enter and verify the PII number assigned to the article by
  OJS, as well as the total page count for the PDF version of the
  article.
| Note: please do not include supplementary file page counts in the
  total!
| During this task, the vendor has an option to open a query to the
  authors via the Send email interface.
| Video: `JPS - Publishing an article in
  OJS <http://oncotarget.screencasthost.com/watch/cbQOYFIuN1>`__

EPUB IN PAPERCHASE
==================

| Role: Production manager
| This task opens immediately after the ePub in OJS task is completed.
  It is assigned to the production manager and requires publishing the
  article to the Advance page and entering the date published into OJS.
  Once this task is complete, the system will notify the authors that
  their article is published online and provide them with the link to
  it. The Post-publication check group of tasks begins immediately after
  this step.
| Video: `JPS - ePub in
  Paperchase <http://oncotarget.screencasthost.com/watch/cbQUbzIxb8>`__

POST-PUBLICAION CHECK
=====================

| The post-publication check is a group of tasks that are arranged
  together to achieve the goal of identifying post-publications
  (commonly referred to as PubMed) corrections to the article,
  communicating them to the vendor, implementing the identified
  corrections and verifying the implementation.
| Video: `JPS - Post-publication check; overview and
  navigation <http://oncotarget.screencasthost.com/watch/cb6eFAIzev>`__

ASSIGN POST-PUBLICATION CHECK TO PE
-----------------------------------

| Role: Production Editor Manager
| During this step, the PE manager assigns the published articles to
  individual production editors who will guide it through the
  post-publication check process.
| Video: `JPS - Assigning the post-publication check
  task <http://oncotarget.screencasthost.com/watch/cb6eqwIziY>`__

POST-PUBLICATION CHECK (ROUND 1)
--------------------------------

| Role: Production Editor
| This task opens when the article is assigned to a production editor.
  During this task, the PE navigates to the article and checks it
  against the predetermined set of standards. The PE then identifies any
  required corrections and relays them to the vendor. Alternatively, the
  PE may mark the article as ready for archiving right away if they do
  not locate any required corrections. Doing so will immediately
  complete the post-publication check process and open the ready for
  archiving task.
| During this step, the PE also has an option to contact the authors by
  opening a query via the Send email function.
| Video: `JPS - Post-publication check - PE
  perspective <http://oncotarget.screencasthost.com/watch/cb6QqGIC3J>`__
| Video: `JPS - Post-publication check: contacting authors and recording
  response <http://oncotarget.screencasthost.com/watch/cb60blI84N>`__

VENDOR REVISIONS REQUIRED
-------------------------

| Role: Vendor
| This task opens if the PE identifies any required corrections during
  the post-publication check task. During this task, the vendor performs
  the requested corrections and notified the PE that they are completed.
| Video: `JPS - Post-publication check - Vendor
  perspective <http://oncotarget.screencasthost.com/watch/cb6QYlICTn>`__

POST-PUBLICATION CHECK (ROUND 2)
--------------------------------

| Role: Production Editor
| After the vendor indicates that they’ve completed the requested
  corrections, it is up to the PE to review the published article again
  and to indicate if further corrections are required. This can be
  accomplished in the same way as the initial post-publication check:
  the PE is presented with two options, one of which returns the article
  to the vendor for further corrections and the other one complete the
  post-publication check process and opens the ready for archiving task.

READY FOR ARCHIVING
===================

| Role: Vendor
| This is the final task in the current implementation of the workflow.
  During this task, JPS notifies the vendor that the article is ready
  for pre-issue archiving. The vendor packages the article files into an
  archive and uploads it to the JPS FTP.
| Upload directory: /home/JPS/To_JPS
| The archive file should be names as follows: OT_[MS#]_VoR.zip
| Note: VoR stands for version of record.
| Once the archive has been important, JPS will notify the Production
  Manager that the article has been archived and is ready to be included
  in the issue.
| Video: `JPS - Archiving the paper for
  issue <http://oncotarget.screencasthost.com/watch/cb6FqOIshQ>`__

.. |image0| image:: media/image1.png
   :width: 2.71641in
   :height: 2.89167in
.. |image1| image:: media/image2.png
   :width: 2.55029in
   :height: 1.55in
.. |image2| image:: media/image3.png
   :width: 4.56667in
   :height: 1.61378in
