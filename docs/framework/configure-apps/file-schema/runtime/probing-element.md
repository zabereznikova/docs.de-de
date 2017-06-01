---
title: "&lt;probing&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#probing"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<probing>-Element"
  - "Containertags, <probing>-Element"
  - "probing-Element"
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# &lt;probing&gt;-Element
Gibt Unterverzeichnisse der Anwendungsbasis an, die die Common Language Runtime beim Laden von Assemblys durchsucht.  
  
## Syntax  
  
```  
<probing privatePath="paths"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`privatePath`|Erforderliches Attribut.<br /><br /> Gibt Unterverzeichnisse des Basisverzeichnisses der Anwendung an, die möglicherweise Assemblys enthalten.  Trennen Sie die einzelnen Unterverzeichnisse durch Semikolons voneinander.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie Unterverzeichnisse der Anwendungsbasis angeben, die die Runtime nach Assemblys durchsuchen soll.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Festlegen des Speicherortes einer Assembly](../../../../../docs/framework/configure-apps/specify-assembly-location.md)   
 [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)