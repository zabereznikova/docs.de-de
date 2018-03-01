---
title: '&lt;Konfiguration&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 3874a613879d099ede4968b5bce349aefa015a38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="configuration-element"></a>\<Konfiguration >-Element

Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.

**\<configuration>**

## <a name="syntax"></a>Syntax

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a>Attribute

Keiner

## <a name="parent-element"></a>Übergeordnetes Element

Keiner

## <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<AssemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.|
| [**\<Start >** -Einstellungsschema](~/docs/framework/configure-apps/file-schema/startup/index.md) | Alle Elemente in der Start-Einstellungsschema. |
| [**\<Common Language Runtime >** -Einstellungsschema](~/docs/framework/configure-apps/file-schema/runtime/index.md) | Alle Elemente in der Common Language Runtime-Einstellungsschema. |
| [**\<System.Runtime.Remoting >** -Einstellungsschema](http://msdn.microsoft.com/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) | Alle Elemente im Schema für Remoteeinstellungen. |
| [**\<system.Net >** -Einstellungsschema](~/docs/framework/configure-apps/file-schema/network/index.md) | Alle Elemente in der Netzwerk-Einstellungsschema. |
| [**\<CryptographySettings >** -Einstellungsschema](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | Alle Elemente im Schema für Kryptografieeinstellungen. |
| [**\<Konfiguration >** Schema für Konfigurationsabschnitte](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | Alle Elemente in der Konfiguration im Abschnitt-Einstellungsschema. |
| [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | Alle Elemente in der Ablaufverfolgung und Debug-Einstellungsschema. |
| [ASP.NET Configuration-Einstellungsschema](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx) | Alle Elemente in dem ASP.NET-Konfiguration-Schema, das Elemente für die Konfiguration von ASP.NET Web Sites und Anwendungen enthält. Verwendet *"Web.config"* Dateien. |
| [**\<WebServices >** -Einstellungsschema](http://msdn.microsoft.com/f84d6d55-1add-4eb7-ae46-33df5833ea2e) | Alle Elemente in der Web-Services-Einstellungsschema. |
| [Web Settings Schema (Schema für Webeinstellungen)](~/docs/framework/configure-apps/file-schema/web/index.md) | Alle Elemente im Webeinstellungsschema, das Elemente für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS enthält. Verwendet *aspnet.config* Dateien. |

## <a name="remarks"></a>Hinweise

Jede Konfigurationsdatei muss genau einen enthalten  **\<Configuration >** Element.

## <a name="see-also"></a>Siehe auch

[Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
