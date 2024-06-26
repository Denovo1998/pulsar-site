---
id: functions-deploy-cluster-builtin
title: Use built-in functions
sidebar_label: "Use built-in functions"
---

Similar to built-in connectors, the code of Java functions [packaged as NAR](functions-package-java.md) that are placed in the `functions` directory of the function worker are loaded at startup and can be referenced when creating a function.

For instance if you have a built-in function with name `exclamation` in its `pulsar-io.yaml`, you can create a function instance with:

```bash
bin/pulsar-admin functions create \
  --function-type exclamation \
  --inputs persistent://public/default/input-1 \
  --output persistent://public/default/output-1
```

To get the list of available built-in Functions, use the `available-functions` command:

```bash
bin/pulsar-admin functions available-functions
```

If you add or delete a NAR file in a `functions` folder, reload the available built-in functions before using it.

```bash
bin/pulsar-admin functions reload
```
