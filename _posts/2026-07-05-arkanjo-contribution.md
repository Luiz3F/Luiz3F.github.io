---
title: Contributing to the ArKanjo tool
date: 2026-07-05 20:10:00 +/- 0300
categories: [Open Source Software Development, MAC0470]
tags: [linux, kernel, kernel-linux]
---

## What is ArKanjo?

ArKanjo is an open-source CLI tool designed to detect code duplications. To use it, it first has a preprocessing step, and it is in there we contributed.

## Our contribution

I once again joined Tiago Dourado for this contribution, and this time our task was changing the configuration file for the preprocess cache metadata from a .txt file to a .json file. Luckily, there were only two fields (the file path and timing informations), so the actual changes were quite simple: we created a `PreprocessRunParams` struct with the desired values for the json and substituted the instances in the code where the data was treated as plaintext with `PreprocessRunParams` usages together with [this json library](https://github.com/nlohmann/json#creating-json-objects-from-json-literals). As an example: 
```c
-  config_content.push_back(path_message);
-  config_content.push_back(time_message);
+  json data = PreprocessRunParams{path, time_str};
```
As you can see, instead of creating messages to be pushed into a string, we just create a json object that can be easily be saved to a file and, now that the file is a json, it can also be easily parsed with a `json::parse` command. Although these changes may seem a bit unnecessary given that there are just two values in the json, it makes the code simpler and futures changes much easier to implement. After we sent the patch, the maintainers suggested some minor tweaks, and then the second patch with those tweaks implemented was accepted (the commit can be seen [here](https://github.com/arkanjo-tool/arkanjo/commit/97c10b4ef66114e0997f229621799d8457824bb9)).
