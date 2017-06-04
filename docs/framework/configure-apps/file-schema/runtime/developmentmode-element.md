---
title: "&lt;developmentMode&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<developmentMode>-Element"
  - "Containertags, <developmentMode>-Element"
  - "developmentMode-Element"
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# &lt;developmentMode&gt;-Element
Gibt an, ob die Runtime in Verzeichnissen, die durch die DEVPATH\-Umgebungsvariable angegeben werden, nach Assemblys sucht.  
  
## Syntax  
  
```  
<developmentMode developerInstallation="true | false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|**developerInstallation**|Gibt an, ob die Runtime in Verzeichnissen, die durch die DEVPATH\-Umgebungsvariable angegeben werden, nach Assemblys sucht.|  
  
## developerInstallation\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|**true**|Die Runtime sucht in Verzeichnissen, die durch die DEVPATH\-Umgebungsvariable angegeben werden, nach Assemblys.|  
|**false**|Die Runtime sucht nicht in Verzeichnissen, die durch die DEVPATH\-Umgebungsvariable angegeben werden, nach Assemblys.  Dies ist die Standardeinstellung.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Verwenden Sie diese Einstellung nur zur Entwicklungszeit.  Die Runtime überprüft nicht die Versionen von Assemblys mit starken Namen in DEVPATH.  Sie verwendet einfach die erste Assembly, die sie findet.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie festlegen, dass die Runtime in Verzeichnissen, die durch die DEVPATH\-Umgebungsvariable angegeben werden, nach Assemblys sucht.  
  
```  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Gewusst wie: Suchen von Assemblys mit DEVPATH](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)