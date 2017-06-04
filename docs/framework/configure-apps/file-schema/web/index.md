---
title: "Webeinstellungsschema | Microsoft Docs"
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
  - "ASP.NET-Konfigurationssystem, Webeinstellungsschema"
  - "Konfigurationsdateien [ASP.NET]"
  - "Konfigurationsschema [.NET Framework], Webeinstellungen"
  - "Webeinstellungsschema"
  - "Webeinstellungen, Schema [ASP.NET]"
  - "Web.config (Konfigurationsdatei) [ASP.NET]"
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Webeinstellungsschema
Webeinstellungen geben ASP.NET\-Einstellungen auf CPU\- und Ausführungsebene für prozessweites Verhalten an, das von der ASP.NET\-Hostebene verwaltet wird.  Diese Einstellungen unterscheiden sich von denen für den Anwendungsdomänentyp, die in der Web.config\-Datei einer ASP.NET\-Anwendung angegeben werden.  
  
 Webeinstellungen sind in Aspnet.config\-Dateien enthalten, die sich in den Installationsordnern von .NET Framework\-Versionen befinden.  Die Aspnet.config\-Datei für [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] befindet sich beispielsweise im folgenden Ordner:  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 Webeinstellungen werden nicht in anderen Konfigurationsdateien wie machine.config, in der Stammdatei Web.config oder in den Web.config\-Dateien auf Anwendungsebene verwendet.  
  
 [\<configuration\>\-Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<system.web\>\-Element \(Webeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [\<applicationPool\>\-Element \(Webeinstellungen\)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<system.web\>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|Enthält Informationen, die von der ASP.NET\-Hostebene verwendet werden.|  
|[\<applicationPool\>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Gibt ASP.NET\-Einstellungen auf CPU\- und Ausführungsebene für prozessweites Verhalten an, das von der ASP.NET\-Hostebene verwaltet wird.|  
  
## Siehe auch  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)