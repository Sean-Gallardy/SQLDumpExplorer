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

## How To Use

![Current Interface](https://github.com/user-attachments/assets/c5c46d99-4d40-4d49-8b01-8b5f1cec55f9)

1. Choose a SQL Server dump file for sqlservr.exe, this will typically end in .DMP or .MDMP
2. Select a Symbols path. By default this will choose a local temp directory as a downstream cache location and set the public Microsoft Symbols server. If you want to use this on an internet disconnected location or use an existing symbols cache location, clicking on the "Select Symbols Path" button will allow you to select the local folder. This is an advanced option.
3. Select the Modules path. The modules path is for processing dumps on a different computer other than where they were generated. If you're running it locally to the computer where the dump was generated, there is no need to change this value. If you're running this on a different computer, you'll need to have the modules which are in the dump in a local path which is accessible. This means having a copy of the various files, such as sqlservr.exe, sqlmin.dll, sqlos.dll, sqllang.dll, etc., this is an advanced option.
4. This is a quick summary of the reason for the dump with SQL Server information and the thread which caused the dump to be generated.
5. This is the dump contents window which holds the various resources inside the dump. Depending on the memory dump there may different resource available such as Threads, Modules, Process Memory Information, etc.
6. This is the context information window for any resources selected in #5 and will output various pieces of information. For example, for a thread, it'll output the thread stack, OS thread ID (which can be used to correlate with perfmon/logman/etw tracing), etc.
7. This window holds some basic status and debug information and is generally not important unless an error occurs.


# Releases
3/22/2025 - Alpha 1.0
