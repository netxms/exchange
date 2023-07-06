# ToolBox
## Purpose of this configuration
"Tool box" with various useful NXSL functions that can be used in other scripts.

## Content
toolbox.xml - contains ToolBox script that will be imported to the script library.

## Version
NetXMS version it was tested on: 4.4.0

## Usage
Functions form toolbox can be used by importing them to your script using `import ToolBox;` statement at the beginning of your script or 
by directly calling then using `ToolBox::functionName(parameters);` form.

### Examples

```
// Get table form agent ant print it using println()
ToolBox::printAgentTable($node, "FileSystem.Volumes");

// Get SNMP metric as a string. Function will return obtained value or null if failed to create transport
value = ToolBox::readSNMPMetric($node, ".1.3.6.1.2.1.2.2.1.1.1");
println(value);

// Print meta information about object like class name, class hierarchy, methods and attributes
ToolBox::info($node);

// Print all possible NXSL meta information (all classes, their methods and atgtributes, and functions)
ToolBox::NXSLInfo();

// Get all node objects under given container (includoing sub-containers) as array
allNodes = ToolBox::getAllNodes(FindObject("Infrastructure Services"));
println(allNodes);

// Check if given node is a Windows node (node should have platform name set correctly)
isWindows = ToolBox::isWindows($node);
println(isWindows);

// Check if given node is a Linux node (node should have platform name set correctly)
isLinux = ToolBox::isLinux($node);
println(isLinux);
```

## Change Log

06.Jul.2023 Initial release
