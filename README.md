## **Doanh Build Pipeline**

This repository provides an API for building a Unity project from the command line, specifically designed for use in a CI/CD pipeline.

### **Installation**

**Prerequisites:**
This package requires Unity Addressables package. Make sure you have the following package installed in your project:
- `com.unity.addressables` (version 1.19.19 or higher)

To install the package, add the following to your project's **`manifest.json`** file:

```
"com.doanh.buildpipeline": "https://github.com/doanhdinh/DoanhBuildPipeline.git#v1.6.4",

```

### **Usage**

**Create ProjectBuildConfiguration**

The configuration file is used to define the build settings for the project. To create a configuration file, select **`Assets > Create > Build Pipeline > Build Configuration`** from the menu.

In the configuration file, you can define the following settings:

- **Environment**: All Doanh Game projects have three types of environments:
  - Staging: This environment is used by development team.
  - Production: This environment is used for the public release of the game.
  - UAT: This environment is used to test the game in house before releasing.

  Each environment has its own scripting define symbols. You can define the scripting define symbols for each environment in the configuration file. Select the environment from the dropdown list in the configuration file and press the "Apply Scripting Define Symbols" button to apply the scripting define symbols to the project.


With the configuration file set up, you can call **`Doanh.BuildPipeline.DoanhAzureDevops.PerformBuild`** in your CI/CD pipeline to build the project.
