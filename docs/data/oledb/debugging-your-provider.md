---
title: "Debugging Your Provider"
ms.date: "11/04/2016"
helpviewer_keywords: ["debugging [C++], providers", "OLE DB providers, debugging", "Visual C++ debugger, debugging providers", "Visual C++ debugger"]
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
---
# Debugging Your Provider

There are two ways to debug your provider:

- Because providers are created in process, you can create some consumer code using the OLE DB consumer templates and step into the provider normally.

- You can use the ITEST utility that comes with Visual C++.

## To use the ITEST utility

1. Open the provider project.

1. On the **Projects** menu, click **Settings**.

1. In the **Property Pages** dialog box, click the **Debug** tab.

1. In the **Executable for Debug Session** box, select the ITEST application.

1. Set breakpoints, and then debug as usual.

## See Also

[Working with OLE DB Provider Templates](../../data/oledb/working-with-ole-db-provider-templates.md)