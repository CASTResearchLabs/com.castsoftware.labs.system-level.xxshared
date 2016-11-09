# _com.castsoftware.labs.system-level.xxshared_ Description

This extension provides sample XX-Shared quality rules:

* Avoid using SQL queries inside an XX-Shared loop
* Check usage of '==' and '!=' on XX-Shared objects
* Avoid UPDATE trigger firing when not necessary in XX-Shared object
* Close the outermost stream ASAP in XX-Shared object
* Avoid method invocation in an XX-Shared loop termination expression
* Avoid instantiations inside XX-Shared loops
* Avoid direct or indirect remote calls inside an XX-Shared loop
* Avoid the use of InstanceOf inside XX-shared loops
* Avoid indirect String concatenation inside XX-shared loops
* Avoid String concatenation in XX-shared loops
* Avoid XX-Shared SQL queries on XXL Tables with implicit conversions in the WHERE clause,
* Avoid XX-Shared SQL queries on XXL tables not using the first column of a composite index in the WHERE clause,
* Avoid XX-Shared SQL queries on XXL Tables using Functions on indexed Columns in the WHERE clause,
* Avoid XX-Shared SQL queries on XXL Tables that no index can support, 
* Avoid XX-Shared SQL queries with a cartesian product on XXL Tables,
* Avoid Cursors inside an XX-Shared loop

# Approach

Turn existing Quality Rules into true System-level Quality Rules

## how?

By integrating in their violation pattern a threshold on their system-level connectedness, as an aggravating factor
threshold is now a quality rule parameter and its default value is 100

## why?

So as to make them:

* more likely to detect real defects \(similarly to XXL SQL rules which use SQL table size to turn potential efficiency issues into near-certain defects\)
* more discriminating to support remediation actions \(by identifying fewer but certainly more beneficial situations\)

## which ones?

Quality Rules which can be aggravated by being massively used within the software
E.g.:

* Quality Rules from the Unexpected Behavior Technical Criterion on the ground that, assuming the original Quality Rule detects a situation where the outcome of the code is unpredictable, the more widely spread the use of the component, the more likely the unexpected behavior will happen
* Quality Rules from the Expensive calls in Loops and SQL Data, Memory, and Network Usage Efficiency Technical Criteria on the ground that the more widely spread the use of the weak component is, the more likely the inefficient behavior will happen

# In what situation should you install this extension?

If you are interested in getting a preview of what XX-shared assisted assessment could be.

# Release notes

## 1.0.0

Initial release delivering 4 sample JEE quality rules

## 1.1.0

Release 1.1.0 of the extension adds 6 new XX-Shared system-level quality rules:

* Avoid method invocation in an XX-Shared loop termination expression,
* Avoid instantiations inside XX-Shared loops,
* Avoid direct or indirect remote calls inside an XX-Shared loop,
* Avoid the use of InstanceOf inside XX-shared loops,
* Avoid indirect String concatenation inside XX-shared loops,
* Avoid String concatenation in XX-shared loops

## 1.2.0

Release 1.2.0 handles connected threshold as quality rule parameter with a default value set to 100 \(note this is lower than the default hard-coded value used in previous releases of the extension: 1000\).

It also demotes original quality rules \(weight and critical contribution option\):

* "Close the outermost stream ASAP" \(metric\_id = 8108\), to an aggregation weight of 5 with the critical contribution flag NOT set from a state with an aggregation weight of 8 with the critical contribution flag set
* "Avoid String concatenation in loops" \(metric\_id = 7200\), to an aggregation weight of 5 with the critical contribution flag NOT set from a state with an aggregation weight of 8 with the critical contribution flag NOT set
* "Avoid method invocation in a loop termination expression" \(metric\_id = 7204\), to an aggregation weight of 5 with the critical contribution flag NOT set from a state with an aggregation weight of 8 with the critical contribution flag NOT set
* "Avoid direct or indirect remote calls inside a loop" \(metric\_id = 7962\), to an aggregation weight of 6 with the critical contribution flag NOT set from a state with an aggregation weight of 9 with the critical contribution flag set
* "Avoid using SQL queries inside a loop" \(metric\_id = 7424\), to an aggregation weight of 5 with the critical contribution flag NOT set from a state with an aggregation weight of 7 with the critical contribution flag set
* "Avoid indirect String concatenation inside loops" \(metric\_id = 7954\), to an aggregation weight of 5 with the critical contribution flag NOT set from a state with an aggregation weight of 7 with the critical contribution flag NOT set
* "Avoid UPDATE trigger firing when not necessary" \(metric\_id = 7490\), to an aggregation weight of 6 with the critical contribution flag NOT set from a state with an aggregation weight of 9 with the critical contribution flag set
* "Check usage of '==' and '!=' on objects" \(metric\_id = 7202\), to an aggregation weight of 5 with the critical contribution flag NOT set from a state with an aggregation weight of 8 with the critical contribution flag set
* "Avoid instantiations inside loops" \(metric\_id = 7210\), to an aggregation weight of 5 with the critical contribution flag NOT set from a state with an aggregation weight of 8 with the critical contribution flag set

## 1.3.0

Release 1.3.0 of the extension adds 7 new XX-Shared system-level quality rules:

* Avoid String concatenation in XX-shared loops \(.NET version while 1.1.0 dealt with the JEE version\)
* Avoid XX-Shared SQL queries on XXL Tables with implicit conversions in the WHERE clause,
* Avoid XX-Shared SQL queries on XXL tables not using the first column of a composite index in the WHERE clause,
* Avoid XX-Shared SQL queries on XXL Tables using Functions on indexed Columns in the WHERE clause,
* Avoid XX-Shared SQL queries on XXL Tables that no index can support, 
* Avoid XX-Shared SQL queries with a cartesian product on XXL Tables,
* Avoid Cursors inside an XX-Shared loop

It also demotes original quality rules \(weight and critical contribution option\):

* "Avoid String concatenation in loops" \(.NET version\) \(metric\_id = 7198\), to an aggregation weight of 5 with the critical contribution flag NOT set from a state with an aggregation weight of 8 with the critical contribution flag NOT set
* "Avoid SQL queries on XXL Tables using Functions on indexed Columns in the WHERE clause" \(metric\_id = 7658\), to an aggregation weight of 6 with the critical contribution flag NOT set and from a state with an aggregation weight of 9 with the critical contribution flag set
* "Avoid SQL queries on XXL Tables with implicit conversions in the WHERE clause" \(metric\_id = 7662\), to an aggregation weight of 6 with the critical contribution flag NOT set from a state with an aggregation weight of 9 with the critical contribution flag set
* "Avoid SQL queries on XXL tables not using the first column of a composite index in the WHERE clause" \(metric\_id = 7642\), to an aggregation weight of 6 with the critical contribution flag NOT set from a state with an aggregation weight of 9 with the critical contribution flag set
* "Avoid Cursors inside a loop" \(metric\_id = 7790\), to an aggregation weight of 5 with the critical contribution flag NOT set from a state with an aggregation weight of 7 with the critical contribution flag set
* "Avoid SQL queries on XXL Tables that no index can support \(AllTechno\)" \(metric\_id = 7656\), to an aggregation weight of 6 with the critical contribution flag NOT set from a state with an aggregation weight of 9 with the critical contribution flag set
* "Never use SQL queries with a cartesian product on XXL Tables" \(metric\_id = 7660\), to an aggregation weight of 6 with the critical contribution flag NOT set from a state with an aggregation weight of 9 with the critical contribution flag set

# _com.castsoftware.labs.system-level.xxshared_ technology support

All technologies configured to be analyzed by AIP are supported.

# Function Point, Quality and Sizing support

This extension is designed to extend Quality Assessments with system-level capabilities via new Quality Rules.

# CAST AIP compatibility

This extension is compatible with:

* 8.1.x out-of-the-box \(AIP release used for the tests\)
* 8.0.x after changing the nuspec file \(there is no reason the extension would not work but it was not tested\)

# Supported DBMS servers

This extension is currently supported on CAST databases installed on CAST Storage Server. All other supported RDBMS are not supported.

# Prerequisites

* An installation of any compatible release of CAST AIP \(see table above\)

# Bug Fix List

N/A

# Download and installation instructions

Please see:  [Extension Link Installation](http://doc.castsoftware.com/display/DOCEXT/Extension+download+and+installation)

The installation steps are the following:

* download the extension through the CAST Extension Downloader using the https://extend.castsoftware.com:443/labs download server
* open Server Manager 8.1+
* select the existing set of databases to update / install a new set of databases
* manage extensions of the existing set of database / follow the installation wizard up to the manage extension pane
* select _com.castsoftware.labs.system-level.xxshared.1.3.0_
* run the update / the installation  
* open CAST Management Studio
* import the Assessment Model from the Dashboard Service processed in steps \#3 to \#6 above; this is a _Mandatory_ step to start computing the new indicator, one MUST import and use the Assessment Model from the Dashboard that was updated with the extension

# Packaging, delivering and analyzing your source code

Packaging, delivering and analyzing your source code is performed the same way as usual.

To get results:

* run a new snapshot

# What results can you expect?

## Objects

N/A

## Links

N/A

## Quality rules

List of new Quality Rules:

* Avoid using SQL queries inside an XX-Shared loop
* Avoid method invocation in an XX-Shared loop termination expression
* Avoid instantiations inside XX-Shared loops
* Avoid direct or indirect remote calls inside an XX-Shared loop
* Avoid the use of InstanceOf inside XX-shared loops
* Avoid indirect String concatenation inside XX-shared loops
* Avoid String concatenation in XX-shared loops
* Avoid Cursors inside an XX-Shared loop
* Avoid UPDATE trigger firing when not necessary in XX-Shared object
* Avoid XX-Shared SQL queries on XXL Tables with implicit conversions in the WHERE clause,
* Avoid XX-Shared SQL queries on XXL tables not using the first column of a composite index in the WHERE clause,
* Avoid XX-Shared SQL queries on XXL Tables using Functions on indexed Columns in the WHERE clause,
* Avoid XX-Shared SQL queries on XXL Tables that no index can support, 
* Avoid XX-Shared SQL queries with a cartesian product on XXL Tables,
* Close the outermost stream ASAP in XX-Shared object
* Check usage of '==' and '!=' on XX-Shared objects

## Technical Criteria

New quality rules results contributes to the following Technical Criteria:

* Efficiency - expensive calls in loops
  * Avoid using SQL queries inside an XX-Shared loop
  * Avoid method invocation in an XX-Shared loop termination expression
  * Avoid instantiations inside XX-Shared loops
  * Avoid direct or indirect remote calls inside an XX-Shared loop
  * Avoid the use of InstanceOf inside XX-shared loops
  * Avoid indirect String concatenation inside XX-shared loops
  * Avoid String concatenation in XX-shared loops
  * Avoid Cursors inside an XX-Shared loop
* Efficiency - SQL and data handling performance
  * Avoid UPDATE trigger firing when not necessary in XX-Shared object
  * Avoid XX-Shared SQL queries on XXL Tables with implicit conversions in the WHERE clause,
  * Avoid XX-Shared SQL queries on XXL tables not using the first column of a composite index in the WHERE clause,
  * Avoid XX-Shared SQL queries on XXL Tables using Functions on indexed Columns in the WHERE clause,
  * Avoid XX-Shared SQL queries on XXL Tables that no index can support, 
  * Avoid XX-Shared SQL queries with a cartesian product on XXL Tables,
* Efficiency - Memory, network, and disk space management
  * Close the outermost stream ASAP in XX-Shared object
* Programming practices - unexpected behaviors
  * Check usage of '==' and '!=' on XX-Shared objects

Furthermore, starting with version 1.2.0, the critical contribution flags of original quality rules have been unset and their weight reduced when needed.

Therefore, you can expect grade variations.

## Business Criteria

New quality rules results contributes to the following Technical Criteria:

* Efficiency - expensive calls in loops
* Efficiency - SQL and data handling performance
* Efficiency - Memory, network, and disk space management
* Programming practices - unexpected behaviors

Therefore, you can expect grade variations for their parents business criteria.

# Limitations

## Functional
Not all quality rules which could benefit from the transformation are already transformed. In other words, it's not because the current extension does not deliver an XX-Shared version of some regular quality rule that it means there would be no value in doing so.

## Technical
N/A

# Illustrations

## CED

### Avoid using SQL queries inside an XX-Shared loop vs. Avoid using SQL queries inside a loop - showing XX-shared violations
![CED Quality Model Drill-down](/CED1.png)
while the original quality rule shows the following violations:
![CED Quality Model Drill-down](/CED2.png)
with only the first one with enough connectedness (> 1000) to be a violation of the XX-Shared version of the quality rulewith only the first one with enough connectedness (> 1000) to be a violation of the XX-Shared version of the quality rule

### Check usage of '==' and '!=' on XX-Shared objects vs. Check usage of '==' and '!=' - showing no XX-shared violation
![CED Quality Model Drill-down](/CED3.png)
while the original quality rule shows the following violations:
![CED Quality Model Drill-down](/CED4.png)
with no violation with enough connectedness (> 1000) to be a violation of the XX-Shared version of the quality rule


## AAD

![AAD home page](/AAD1.png)


## AED

![AED Quality Model Drill-down](/AED1.png)

