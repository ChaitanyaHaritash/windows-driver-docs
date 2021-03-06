---
title: InputMediaSize element
description: The required InputMediaSize element specifies the size of the media to be scanned for the current job.
ms.assetid: f1fcb152-96c5-469c-8989-a2c4328a5f68
keywords: ["InputMediaSize element Imaging Devices"]
topic_type:
- apiref
api_name:
- wscn InputMediaSize
api_type:
- Schema
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# InputMediaSize element


The required **InputMediaSize** element specifies the size of the media to be scanned for the current job.

Usage
-----

``` syntax
<wscn:InputMediaSize>
  child elements
</wscn:InputMediaSize>
```

Attributes
----------

There are no attributes.

## Child elements


<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th>Element</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[<strong>Height</strong>](height.md)</p></td>
</tr>
<tr class="even">
<td><p>[<strong>Width</strong>](width.md)</p></td>
</tr>
</tbody>
</table>

## Parent elements


<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th>Element</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[<strong>InputSize</strong>](inputsize.md)</p></td>
</tr>
</tbody>
</table>

Remarks
-------

The **InputMediaSize** element contains the width and height of the input media to be scanned, specified in the [**Width**](width.md) and [**Height**](height.md) elements, respectively.

The **Width** element contains the width of the original media in the fast scan direction, and the **Height** element contains the height of the original media in the slow scan direction. Both **Width** and **Height** must be in the range from 1 through 2147483648 and are in units of one-thousandths (1/1000) of an inch.

## <span id="see_also"></span>See also


[**Height**](height.md)

[**InputSize**](inputsize.md)

[**Width**](width.md)

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bimage\image%5D:%20InputMediaSize%20element%20%20RELEASE:%20%2811/8/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





