---
title: "Optimization for Shared Web Hosting | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "garbage collection, Web hosting"
  - "garbage collection, optimizing"
  - "garbage collection, shared Web hosting"
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Optimization for Shared Web Hosting
Wenn Sie Administrator eines Servers sind, auf dem mehrere kleine Websites gemeinsam gehostet werden, können Sie dei Leistung optimieren und die Sitekapazität erhöhen, indem Sie die folgende `gcTrimCommitOnLowMemory`\-Einstellung zum `runtime`\-Knoten zur Aspnet.config\-Datei im .NET Framework\-Verzeichnis hinzufügen:  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  Diese Einstellung wird nur für Szenarien freigegebenen Webhostings empfohlen.  
  
 Da der Garbage Collector für die spätere Belegungen Speicher beibehält, kann der beanspruchte Speicher größer sein als eigentlich notwendig.  Sie können diesen Speicher reduzieren, um so Zeiten hoher Auslastung des Systemarbeitsspeichers zu berücksichtigen.  Die Reduzierung des belegten Speichers verbessert die Leistung und erweitert die Kapazität für das Hosting weiterer Sites.  
  
 Wenn die `gcTrimCommitOnLowMemory`\-Einstellung aktiviert ist, wertet der Garbage Collector die Systemarbeitsspeicherauslastung aus und geht in einen Einschränkungsmodus über, wenn die Auslastung 90 % erreicht.  Dieser Modus wird so lange beibehalten, bis die Auslastung auf unter 85 % sinkt.  
  
 Falls die Bedingungen dies zulassen, kann der Garbage Collector entscheiden, dass die `gcTrimCommitOnLowMemory`\-Einstellung keine Hilfe für die aktuelle Anwendung ist, und sie ignorieren.  
  
## Beispiel  
 Das folgende XML\-Fragment zeigt, wie die `gcTrimCommitOnLowMemory`\-Einstellung aktiviert wird.  Auslassungspunkte geben andere Einstellungen an, die sich im `runtime`\-Knoten befänden.  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## Siehe auch  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)