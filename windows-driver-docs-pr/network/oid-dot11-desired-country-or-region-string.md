---
title: OID_DOT11_DESIRED_COUNTRY_OR_REGION_STRING
author: windows-driver-content
description: OID_DOT11_DESIRED_COUNTRY_OR_REGION_STRING
ms.assetid: 5a1e9019-c821-45c9-b8ed-5b78d213f7ee
ms.author: windowsdriverdev
ms.date: 08/08/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
keywords: 
 -OID_DOT11_DESIRED_COUNTRY_OR_REGION_STRING Network Drivers Starting with Windows Vista
---

# OID\_DOT11\_DESIRED\_COUNTRY\_OR\_REGION\_STRING


**Important**  The [Native 802.11 Wireless LAN](https://msdn.microsoft.com/library/windows/hardware/ff560690) interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see [WLAN Universal Windows driver model](https://msdn.microsoft.com/library/windows/hardware/dn897672).

 

When set, the OID\_DOT11\_DESIRED\_COUNTRY\_OR\_REGION\_STRING object identifier (OID) requests that the miniport driver set the value of the Extensible Station (ExtSTA) **msDot11DesiredCountryOrRegionString** management information base (MIB) object to the specified data.

When queried, OID\_DOT11\_DESIRED\_COUNTRY\_OR\_REGION\_STRING requests that the miniport driver return the value of the **msDot11DesiredCountryOrRegionString** MIB object.

The data type for OID\_DOT11\_DESIRED\_COUNTRY\_OR\_REGION\_STRING is the [**DOT11\_COUNTRY\_OR\_REGION\_STRING**](dot11-country-or-region-string.md) structure.

**Note**  Support for OID\_DOT11\_DESIRED\_COUNTRY\_OR\_REGION\_STRING is mandatory if the 802.11 station supports multiple regulatory domains as defined through the IEEE 802.11d-2001 standard. For more information about how the miniport driver specifies its support for regulatory domains, see [OID\_DOT11\_MULTI\_DOMAIN\_CAPABILITY\_IMPLEMENTED](oid-dot11-multi-domain-capability-implemented.md).

 

The **msDot11DesiredCountryOrRegionString** MIB object specifies an IEEE 802.11d country string used by the 802.11 station whenever it does one of the following:

-   Associates with an access point (AP) or peer stationconnection operation. In this situation, the 802.11 station uses the **msDot11DesiredCountryOrRegionString** MIB object to create a BSS network candidate list in order to determine which AP or peer station it can associate with.

    For more information about the association operation, see [Association Operations](https://msdn.microsoft.com/library/windows/hardware/ff543789). For more information about the BSS network candidate list, see [BSS Network Candidate List](https://msdn.microsoft.com/library/windows/hardware/ff543855).

-   Starts a new independent BSS (IBSS) network during a connection operation. In this situation, the 802.11 station sets the IEEE 802.11Country Information Element (IE) to the value of the **msDot11DesiredCountryOrRegionString** MIB object in the 802.11 Beacon and Probe Response frames that the station transmits.

    For more information about the connection operation, see [Connection Operations](https://msdn.microsoft.com/library/windows/hardware/ff545185). For more information about how the 802.11 station starts an IBSS network, see [Connection Operation Guidelines for Independent BSS Networks](https://msdn.microsoft.com/library/windows/hardware/ff545188).

The default for the **msDot11DesiredCountryOrRegionString** MIB object is a [**DOT11\_COUNTRY\_OR\_REGION\_STRING**](dot11-country-or-region-string.md) string of all zeros. The miniport driver must set this MIB object to its default if any of the following occur:

-   The miniport driver's [*MiniportInitializeEx*](https://msdn.microsoft.com/library/windows/hardware/ff559389) function is called.

-   A method request of [OID\_DOT11\_RESET\_REQUEST](oid-dot11-reset-request.md) is made to reset the MAC layer of the 802.11 station and the **bSetDefaultMIB** member of the DOT11\_RESET\_REQUEST structure is **TRUE**.

Requirements
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Version</p></td>
<td><p>Available in Windows Vista and later versions of the Windows operating systems.</p></td>
</tr>
<tr class="even">
<td><p>Header</p></td>
<td>Windot11.h (include Ndis.h)</td>
</tr>
</tbody>
</table>

## See also


[Native 802.11 Wireless LAN OIDs](https://msdn.microsoft.com/library/windows/hardware/ff560691)

 

 




