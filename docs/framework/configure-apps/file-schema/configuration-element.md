---
title: <configuration>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 9a7b25c74763c020c0e19c3f6099db9001acf773
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675048"
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

Keine

## <a name="parent-element"></a>Übergeordnetes Element

Keine

## <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.|
| [**\<Startup >** Schema für Laufzeiteinstellungen](~/docs/framework/configure-apps/file-schema/startup/index.md) | Alle Elemente in das Schema für starteinstellungen. |
| [**\<Common Language Runtime >** Schema für Laufzeiteinstellungen](~/docs/framework/configure-apps/file-schema/runtime/index.md) | Alle Elemente in das Schema für Laufzeiteinstellungen. |
| [**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) | Alle Elemente im Schema für Remoteeinstellungen. |
| [**\<system.Net >** Schema für Laufzeiteinstellungen](~/docs/framework/configure-apps/file-schema/network/index.md) | Alle Elemente in der netzwerkeinstellungsschema. |
| [**\<cryptographySettings>** Settings Schema](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | Alle Elemente im Schema für Kryptografieeinstellungen. |
| [**\<Konfiguration >** Schema für Konfigurationsabschnitte](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | Alle Elemente in den Einstellungen des Konfigurationsschemas-Abschnitt. |
| [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | Alle Elemente im Einstellungsschema für Ablaufverfolgung und Debuggen. |
| [Einstellungen für die ASP.NET-Konfigurationsschema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) | Alle Elemente in die ASP.NET-Konfigurationsschema, die Elemente für die Konfiguration von ASP.NET-Websites und-Anwendungen enthält. Verwendet *"Web.config"* Dateien. |
| [**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) | Alle Elemente in das Einstellungsschema für Webdienste. |
| [Web Settings Schema (Schema für Webeinstellungen)](~/docs/framework/configure-apps/file-schema/web/index.md) | Alle Elemente im Webeinstellungsschema, das Elemente für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS enthält. Verwendet *aspnet.config* Dateien. |

## <a name="remarks"></a>Hinweise

Jede der Konfigurationsdateien muss genau einen enthalten  **\<Configuration >** Element.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
