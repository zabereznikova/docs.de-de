---
title: "&lt;remove&gt;-Element f&#252;r &lt;namedCaches&gt; | Microsoft Docs"
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
  - "<remove>-Element für namedCaches"
  - "remove-Element für namedCaches"
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# &lt;remove&gt;-Element f&#252;r &lt;namedCaches&gt;
Entfernt aus der `namedCaches`\-Auflistung einen benannten Cacheeintrag für einen Speichercache.  
  
## Syntax  
  
```  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## Typ  
 `None`  
  
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
 Das `remove`\-Element entfernt einen `namedCache`\-Eintrag aus der Auflistung der benannten Cacheeinträge für einen Speichercache.  
  
## Siehe auch  
 [\<namedCaches\>\-Element \(Cacheeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)