---
title: "&lt;Deaktivieren Sie&gt; -Element für &lt;NamedCaches&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0819141b2135a2de99a2801a1888f7b0e1cd19fc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a>&lt;Deaktivieren Sie&gt; -Element für &lt;NamedCaches&gt;
Löscht alle `namedCache` Einträge in der `namedCaches` Auflistung für einen Arbeitsspeichercache.  
  
 \<System.Runtime.Caching >  
\<MemoryCache >  
\<NamedCaches >  
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
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Enthält eine Auflistung von Konfigurationseinstellungen für die benannte <xref:System.Runtime.Caching.MemoryCache> Instanzen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `clear` Element löscht alle `namedCache` Einträge in der Auflistung des benannten Caches für einen Speichercache. Können Sie die `clear` Element vor der Verwendung der `add` Element um einen neuen Eintrag für den benannten Cache hinzufügen, damit stellen Sie sicher, dass es sind keine anderen benannte Caches in der Auflistung.  
  
## <a name="see-also"></a>Siehe auch  
 [\<NamedCaches >-Element (Cacheeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
