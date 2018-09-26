---
title: '&lt;Konfiguration&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 40c0ab5f18d5aae2c99dd66747d3435f0826af8b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47200320"
---
# <a name="configuration-element"></a>\<Configuration >-Element

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
| [**\<Startup >** Schema für Laufzeiteinstellungen](~/docs/framework/configure-apps/file-schema/startup/index.md) | Alle Elemente in das Schema für starteinstellungen. |
| [**\<Common Language Runtime >** Schema für Laufzeiteinstellungen](~/docs/framework/configure-apps/file-schema/runtime/index.md) | Alle Elemente in das Schema für Laufzeiteinstellungen. |
| [**\<System.Runtime.Remoting >** Schema für Laufzeiteinstellungen](https://msdn.microsoft.com/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) | Alle Elemente im Schema für Remoteeinstellungen. |
| [**\<system.Net >** Schema für Laufzeiteinstellungen](~/docs/framework/configure-apps/file-schema/network/index.md) | Alle Elemente in der netzwerkeinstellungsschema. |
| [**\<CryptographySettings >** Schema für Laufzeiteinstellungen](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | Alle Elemente im Schema für Kryptografieeinstellungen. |
| [**\<Konfiguration >** Schema für Konfigurationsabschnitte](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | Alle Elemente in den Einstellungen des Konfigurationsschemas-Abschnitt. |
| [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | Alle Elemente im Einstellungsschema für Ablaufverfolgung und Debuggen. |
| [Einstellungen für die ASP.NET-Konfigurationsschema](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx) | Alle Elemente in die ASP.NET-Konfigurationsschema, die Elemente für die Konfiguration von ASP.NET-Websites und-Anwendungen enthält. Verwendet *"Web.config"* Dateien. |
| [**\<WebServices >** Schema für Laufzeiteinstellungen](https://msdn.microsoft.com/f84d6d55-1add-4eb7-ae46-33df5833ea2e) | Alle Elemente in das Einstellungsschema für Webdienste. |
| [Web Settings Schema (Schema für Webeinstellungen)](~/docs/framework/configure-apps/file-schema/web/index.md) | Alle Elemente im Webeinstellungsschema, das Elemente für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS enthält. Verwendet *aspnet.config* Dateien. |

## <a name="remarks"></a>Hinweise

Jede der Konfigurationsdateien muss genau einen enthalten  **\<Configuration >** Element.

## <a name="see-also"></a>Siehe auch

[Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
