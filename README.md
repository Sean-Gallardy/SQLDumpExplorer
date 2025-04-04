# SQLDumpExplorer
GUI based dump viewer for SQL Server memory dumps.

## Information
This is the new home for the SQL Server Dump Explorer/Analyzer tooling, previously at SQLDumpAnalysis.com. Previously it was a web based service, however given the feedback that a stand-alone application would be nice, I've since transitioned the entire project to be application based, which is currently not open source.

## Reporting Bugs
Please use the Issues to create bugs and ideas for functionality.

## Internet Locations Utilized
If you're running the application with limited or not internet connectivity, please note the following.

### Symbols
Microsoft Symbols server will be used unless the symbols path is changed to a local copy. If the symbols do not exist in the local folder and the Microsoft symbols server is not used, symbols will not properly resolve. This will cause the stacks to be unresolvable and the dump information will be limited or fail to properly be found.
If you're in a strict environment, please add the Microsoft Symbols Server exception into your security software/firewall.
Location: https://msdl.microsoft.com/download/symbols

### KB Information
There is an attempt to scrape KB information to find possible known solutions to dumps. This utilizes the KB information available on Microsoft's website. If there is no internet connectivity, this will fail and be skipped.
If you're in a strict environment, please add the Microsoft KB exception into your security software/firewall.
Location: http://*.microsoft.com

## Telemetry
There is no telemtry in the application, it was designed to run locally and without internet connectivity.

## Known Limitations
- Will not work on Linux or ARM dumps
- Compressed memory dumps will need to be uncompressed first
- Will only work for SQL Server, not Agent or other processes

# Releases
3/22/2025 - Alpha 1.0
