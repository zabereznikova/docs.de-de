---
title: <clear>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: bcc0e23f0c47ad3a98430e36da31d39612caa3c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252760"
---
# <a name="clear-element-for-namedcaches"></a>\<clear>-Element für \<namedCaches>
Löscht alle `namedCache` Einträge in der-Auflistung `namedCaches` für einen Speicher Cache.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>type  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 `None`  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 `None`  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Enthält eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das- `clear` Element löscht alle `namedCache` Einträge in der benannten Cache Auflistung für einen Speicher Cache. Sie können das- `clear` Element verwenden, bevor Sie das- `add` Element verwenden, um einen neuen benannten Cache Eintrag hinzuzufügen, um sicherzustellen, dass keine anderen benannten Caches in der Auflistung vorhanden sind.  
  
## <a name="see-also"></a>Weitere Informationen

- [\<namedCaches>-Element (Cache Einstellungen)](namedcaches-element-cache-settings.md)
