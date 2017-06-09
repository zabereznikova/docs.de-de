---
title: "&lt;clear&gt;-Element f&#252;r &lt;namedCaches&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<clear>-Element für <namedCaches>"
  - "clear-Element für <namedCaches>"
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;clear&gt;-Element f&#252;r &lt;namedCaches&gt;
Löscht alle `namedCaches`\-Einträge in der `namedCache`\-Auflistung für einen Speichercache.  
  
## Syntax  
  
```  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## Typ  
 `Type`  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 `None`  
  
### Untergeordnete Elemente  
 `None`  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<namedCaches\>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Enthält eine Auflistung der Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache>\-Instanzen.|  
  
## Hinweise  
 Das `clear`\-Element löscht alle `namedCache`\-Einträge in der Auflistung des benannten Caches für einen Speichercache.  Verwenden Sie das `clear`\-Element vor der Verwendung des `add`\-Elements zum Hinzufügen eines neuen benannten Cacheeintrags, um sicherzugehen, dass sich keine weiteren benannten Caches in der Auflistung befinden.  
  
## Siehe auch  
 [\<namedCaches\>\-Element \(Cacheeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)