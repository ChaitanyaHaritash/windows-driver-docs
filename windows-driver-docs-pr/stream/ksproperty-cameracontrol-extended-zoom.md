---
title: KSPROPERTY\_CAMERACONTROL\_EXTENDED\_ZOOM
description: KSPROPERTY\_CAMERACONTROL\_EXTENDED\_ZOOM is used to control digital zoom.
ms.assetid: 93CFCBFC-69B3-4241-913F-94615599BE8E
keywords: ["KSPROPERTY_CAMERACONTROL_EXTENDED_ZOOM Streaming Media Devices"]
topic_type:
- apiref
api_name:
- KSPROPERTY_CAMERACONTROL_EXTENDED_ZOOM
api_location:
- Ksmedia.h
api_type:
- HeaderDef
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# KSPROPERTY\_CAMERACONTROL\_EXTENDED\_ZOOM


**KSPROPERTY\_CAMERACONTROL\_EXTENDED\_ZOOM** is used to control digital zoom. It is defined in the [**KSPROPERTY\_CAMERACONTROL\_EXTENDED\_PROPERT**](https://msdn.microsoft.com/library/windows/hardware/dn917962)Y enumeration and is used to get and set the zoom ratio and get zoom ranges from the driver. In Windows 10, this control is extended to also support smooth zoom.

## <span id="Usage_summary_table"></span><span id="usage_summary_table"></span><span id="USAGE_SUMMARY_TABLE"></span>Usage summary table


<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Scope</th>
<th>Control</th>
<th>Type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Version 1</p></td>
<td><p>Filter</p></td>
<td><p>Synchronous</p></td>
</tr>
</tbody>
</table>

 

The following flags can be placed in the **KSCAMERA\_EXTENDEDPROP\_HEADER.Flags** field to control smooth zoom vs. direct zoom. The default is defined by the driver.

``` syntax
#define KSCAMERA_EXTENDEDPROP_ZOOM_DEFAULT               0x0000000000000000
#define KSCAMERA_EXTENDEDPROP_ZOOM_DIRECT                0x0000000000000001
#define KSCAMERA_EXTENDEDPROP_ZOOM_SMOOTH                0x0000000000000002
```

If the driver supports this control, it must support **KSCAMERA\_EXTENDEDPROP\_ZOOM\_DEFAULT**.

If the driver does not support digital zoom, the driver should not implement this control.

The following table describes the flag capabilities.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Flag</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>KSCAMERA_EXTENDEDPROP_ZOOM_DEFAULT</strong></p></td>
<td><p>This is a mandatory capability. When specified, the driver will decide whether a direct zoom or smooth zoom should be applied and zoom to the target zoom factor specified in VideoProc.Value.ul accordingly. This flag is mutually exclusive with the DIRECT and SMOOTH flags.</p></td>
</tr>
<tr class="even">
<td><p><strong>KSCAMERA_EXTENDEDPROP_ZOOM_DIRECT</strong></p></td>
<td><p>This is a mandatory capability. When specified, the driver will zoom to the target zoom factor specified in VideoProc.Value.ul as quickly as possible. This flag is mutually exclusive with the AUTO and SMOOTH flags.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KSCAMERA_EXTENDEDPROP_ZOOM_SMOOTH</strong></p></td>
<td><p>This capability is optional. When specified, the driver will zoom to the target zoom factor specified in VideoProc.Value.ul gradually in a smooth manner. The number of frames takes to reach the specified zoom factor is up to the driver. This flag is mutually exclusive with the AUTO and DIRECT flags.</p></td>
</tr>
</tbody>
</table>

 

For each **GET** call, the driver must report the current zoom ranges allowed based on current configurations or setup.

The following table contains the descriptions and requirements for the [**KSCAMERA\_EXTENDEDPROP\_HEADER**](https://msdn.microsoft.com/library/windows/hardware/dn925136) structure fields when using the **KSPROPERTY\_CAMERACONTROL\_EXTENDED\_ZOOM** property.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Member</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Version</p></td>
<td><p>This must be 1,</p></td>
</tr>
<tr class="even">
<td><p>PinId</p></td>
<td><p>This must be <strong>KSCAMERA_EXTENDEDPROP_FILTERSCOPE</strong> (0xFFFFFFFF),</p></td>
</tr>
<tr class="odd">
<td><p>Size</p></td>
<td><p>This must be sizeof(<strong>KSCAMERA_EXTENDEDPROP_HEADER</strong>)+sizeof([<strong>KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING</strong>](https://msdn.microsoft.com/library/windows/hardware/dn567566)),</p></td>
</tr>
<tr class="even">
<td><p>Result</p></td>
<td><p>This indicates the error results of the last SET operation. If no SET operation has taken place, this must be 0.</p></td>
</tr>
<tr class="odd">
<td><p>Capability</p></td>
<td><p>Must be a bitwise OR of the supported flags defined above.</p></td>
</tr>
<tr class="even">
<td><p>Flags</p></td>
<td><p>This is a read/write field. This can be any one of the supported flags defined above.</p></td>
</tr>
</tbody>
</table>

 

The table below contains the descriptions and requirements for the **KSCAMERA\_EXTENDEDPROP\_VIDEOPROCSETTING** structure fields for the **KSPROPERTY\_CAMERACONTROL\_EXTENDED\_ZOOM** property.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Member</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mode</p></td>
<td><p>This is unused and must be 0.</p></td>
</tr>
<tr class="even">
<td><p>Min/Max/Step</p></td>
<td><p>The Min/Max/Step contains the minimum/maximum/increment of the zoom ratio supported by the camera driver in Q16 format. The driver must return these values for <strong>GET</strong> operations.</p></td>
</tr>
<tr class="odd">
<td><p>VideoProc</p></td>
<td><p>For <strong>SET</strong> operations, the VideoProc.Value.ul must specify the zoom ratio within the range described by the Min/Max/Step parameter. For <strong>GET</strong> operations, the driver must return the current zoom ratio.</p></td>
</tr>
<tr class="even">
<td><p>Reserved</p></td>
<td><p>This is unused. This must be ignored by the driver.</p></td>
</tr>
</tbody>
</table>

 

Requirements
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Header</p></td>
<td>Ksmedia.h</td>
</tr>
</tbody>
</table>

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bstream\stream%5D:%20KSPROPERTY_CAMERACONTROL_EXTENDED_ZOOM%20%20RELEASE:%20%2811/22/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")




