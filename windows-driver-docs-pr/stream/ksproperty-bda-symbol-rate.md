---
title: KSPROPERTY\_BDA\_SYMBOL\_RATE
description: Clients use KSPROPERTY\_BDA\_SYMBOL\_RATE to control the symbol rate of a demodulator node.
ms.assetid: 11e2e020-3037-4a68-a8d6-c68efd86a518
keywords: ["KSPROPERTY_BDA_SYMBOL_RATE Streaming Media Devices"]
topic_type:
- apiref
api_name:
- KSPROPERTY_BDA_SYMBOL_RATE
api_type:
- NA
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# KSPROPERTY\_BDA\_SYMBOL\_RATE


Clients use KSPROPERTY\_BDA\_SYMBOL\_RATE to control the symbol rate of a demodulator node.

## <span id="ddk_ksproperty_bda_symbol_rate_ks"></span><span id="DDK_KSPROPERTY_BDA_SYMBOL_RATE_KS"></span>


### <span id="Usage_Summary_Table"></span><span id="usage_summary_table"></span><span id="USAGE_SUMMARY_TABLE"></span>Usage Summary Table

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th>Get</th>
<th>Set</th>
<th>Target</th>
<th>Property descriptor type</th>
<th>Property value type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Filter</p></td>
<td><p>KSP_NODE</p></td>
<td><p>ULONG</p></td>
</tr>
</tbody>
</table>

 

Remarks
-------

The returned value specifies the symbol rate.

The **NodeId** member of KSP\_NODE specifies the identifier of the demodulator node.

## <span id="see_also"></span>See also


[**KSP\_NODE**](https://msdn.microsoft.com/library/windows/hardware/ff566720)

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bstream\stream%5D:%20KSPROPERTY_BDA_SYMBOL_RATE%20%20RELEASE:%20%2811/22/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





