---
title: '&lt;Deaktivieren Sie&gt; -Element für &lt;NamedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: d71c5de42104961bc096b786dfe50bb4097bc4fc
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083560"
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a>&lt;Deaktivieren Sie&gt; -Element für &lt;NamedCaches&gt;
Löscht alle `namedCache` Einträge in der `namedCaches` Auflistung für einen Speichercache.  
  
 \<system.runtime.caching>  
\<memoryCache>  
\<namedCaches>  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Typ  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 `None`  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 `None`  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Enthält eine Auflistung von Konfigurationseinstellungen für den benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `clear` Element löscht alle `namedCache` Einträge in der Auflistung benannter Caches für einen Speichercache. Können Sie die `clear` Element vor der Verwendung der `add` Element um einen neuen Eintrag für den benannten Cache hinzufügen, um sicherzugehen, dass sich keine weiteren benannten Caches in der Auflistung.  
  
## <a name="see-also"></a>Siehe auch
- [\<NamedCaches >-Element (Cacheeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
