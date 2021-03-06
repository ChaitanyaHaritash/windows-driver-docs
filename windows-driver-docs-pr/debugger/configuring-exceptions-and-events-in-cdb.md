---
title: Configuring Exceptions and Events in CDB
description: You can configure CDB to react to specified exceptions and events in a specific way. For each exception, you can set the break status and the handling status. 
ms.assetid: EA23057E-3241-43F2-84D3-CA5E56721583
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# Configuring Exceptions and Events in CDB


You can configure CDB to react to specified exceptions and events in a specific way. For each exception, you can set the break status and the handling status. For each event, you can set the break status.

You can configure the break status or handling status by doing one of the following:

-   Use the [**SXE**](sx--sxd--sxe--sxi--sxn--sxr--sx---set-exceptions-.md), **SXD**, **SXN**, or **SXI** command.

-   Use the **-x**, **-xe**, **-xd**, **-xn**, or **-xi** option on the [**CDB command line**](cdb-command-line-options.md).
-   Use the **sxe** or **sxd** keyword in the Tools.ini file.

For a detailed discussion of exceptions and events, see [Controlling Exceptions and Events](controlling-exceptions-and-events.md).

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20[debugger\debugger]:%20Configuring%20Exceptions%20and%20Events%20in%20CDB%20%20RELEASE:%20%285/15/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")




