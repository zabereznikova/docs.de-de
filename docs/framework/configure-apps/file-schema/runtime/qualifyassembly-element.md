---
title: "&lt;qualifyAssembly&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<qualifyAssembly>-Element"
  - "Containertags, <qualifyAssembly>-Element"
  - "qualifyAssembly-Element"
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# &lt;qualifyAssembly&gt;-Element
Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn ein partieller Name verwendet wird.  
  
## Syntax  
  
```  
  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`partialName`|Erforderliches Attribut.<br /><br /> Gibt den partiellen Namen der Assembly an, wie er im Code erscheint.|  
|`fullName`|Erforderliches Attribut.<br /><br /> Gibt den vollständigen Namen der Assembly an, wie er im Code erscheint.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Durch Aufrufen der <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>\-Methode unter Verwendung von partiellen Assemblynamen sucht die Common Language Runtime nur im Basisverzeichnis der Anwendung nach der Assembly.  Verwenden Sie das **\<qualifyAssembly\>**\-Element in der Anwendungskonfigurationsdatei, um die vollständigen Assemblyinformationen \(Name, Version, öffentliches Schlüsseltoken und Kultur\) bereitzustellen und die Common Language Runtime zu veranlassen, für die Assembly im globalen Assemblycache zu finden.  
  
 Das **fullName**\-Attribut muss folgende vier Felder für die Identität der Assembly enthalten: Name, Version, öffentliches Schlüsseltoken und Kultur.  Das **partialName**\-Attribut muss partiell auf eine Assembly verweisen.  Sie müssen zumindest den Textnamen der Assembly angeben \(in den meisten Fällen\), Sie können jedoch auch die Version, das öffentliche Schlüsseltoken oder die Kultur angeben \(oder eine Kombination aus Elementen, aber nicht alle vier Elemente\).  Der **partialName** muss mit dem Namen übereinstimmen, der in dem Aufruf angegeben wird.  Beispielsweise können Sie nicht `"math"` als **partialName**\-Attribut in der Konfigurationsdatei angeben und `Assembly.Load("math, Version=3.3.3.3")` im Code aufrufen.  
  
## Beispiel  
 Im folgenden Beispiel wird der Aufruf `Assembly.Load("math")` logisch in `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")` umgewandelt.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [NIB: Partial Assembly References](http://msdn.microsoft.com/de-de/ec90f07a-398c-4306-9401-0fc5ff9cb59f)