---
title: "&lt;configuration&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<configuration>-Element"
  - "configuration-Element"
  - "Containertags, <configuration>-Element"
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;configuration&gt;-Element
Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.  
  
 **\<konfiguration\>**  
  
## Syntax  
  
```  
  
      <configuration>   
   <!-- configuration settings -->   
</configuration>  
```  
  
## Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<assemblyBinding\>\-Element](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)|Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.|  
|[Schema für Starteinstellungen](../../../../docs/framework/configure-apps/file-schema/startup/index.md)|Alle Elemente im Schema für Starteinstellungen.|  
|[Schema für Laufzeiteinstellungen](../../../../docs/framework/configure-apps/file-schema/runtime/index.md)|Alle Elemente im Schema für Laufzeiteinstellungen.|  
|[Schema für Remoteeinstellungen](http://msdn.microsoft.com/de-de/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e)|Alle Elemente im Schema für Remoteeinstellungen.|  
|[Netzwerkeinstellungsschema](../../../../docs/framework/configure-apps/file-schema/network/index.md)|Alle Elemente im Schema für Netzwerkeinstellungen.|  
|[Schema für Kryptografieeinstellungen](../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)|Alle Elemente im Schema für Kryptografieeinstellungen.|  
|[Schema für Konfigurationsabschnitte](../../../../docs/framework/configure-apps/file-schema/configuration-sections-schema.md)|Alle Elemente im Schema für Konfigurationsabschnittseinstellungen.|  
|[Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)|Alle Elemente im Schema für Ablaufverfolgungs\- und Debugeinstellungen.|  
|[ASP.NET\-Einstellungsschema](http://msdn.microsoft.com/de-de/116608f3-c03d-4413-9fc7-978703e18b0f)|Alle Elemente im ASP.NET Konfigurationsschema, das Elemente für die Konfiguration von ASP.NET\-Websites und Anwendungen enthält.  Wird in Web.config\-Dateien verwendet.|  
|[Einstellungsschema für XML\-Webdienste](http://msdn.microsoft.com/de-de/f84d6d55-1add-4eb7-ae46-33df5833ea2e)|Alle Elemente im Einstellungsschema für Webdienste.|  
|[Webeinstellungsschema](../../../../docs/framework/configure-apps/file-schema/web/index.md)|Alle Elemente im Webeinstellungsschema, das Elemente für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS enthält.  Wird in aspnet.config\-Dateien verwendet.|  
  
## Hinweise  
 Jede Konfigurationsdatei muss **\<Konfiguration\>** genau ein Element enthalten.  
  
## Siehe auch  
 [Konfigurationsdateischema](../../../../docs/framework/configure-apps/file-schema/index.md)