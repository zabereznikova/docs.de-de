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
ms.openlocfilehash: 8f79981a55d0bc9b1cd522e45f5606fda102c72c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544688"
---
# <a name="configuration-element"></a>\<configuration>-Element

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

|     | BESCHREIBUNG |
| --- | ----------- |
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.|
| [**\<startup>** Einstellungs Schema](./startup/index.md) | Alle Elemente im Start Einstellungs Schema. |
| [**\<runtime>** Einstellungs Schema](./runtime/index.md) | Alle Elemente im Lauf Zeit Einstellungs Schema. |
| [**\<system.runtime.remoting>** Einstellungs Schema](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) | Alle Elemente im Remoting-Einstellungs Schema. |
| [**\<system.Net>** Einstellungs Schema](./network/index.md) | Alle Elemente im Netzwerk Einstellungs Schema. |
| [**\<cryptographySettings>** Einstellungs Schema](./cryptography/index.md) | Alle Elemente im kryptografieeinstellungs-Schema. |
| [**\<configuration>** Abschnitts Schema](configuration-sections-schema.md) | Alle Elemente im Konfigurations Abschnitts Einstellungs Schema. |
| [Schema der Ablauf Verfolgung und Debugeinstellungen](./trace-debug/index.md) | Alle Elemente im Ablauf Verfolgungs-und debugeinstellungs Schema. |
| [Schema der ASP.NET-Konfigurationseinstellungen](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) | Alle Elemente im ASP.NET-Konfigurations Schema, die Elemente zum Konfigurieren von ASP.NET-Websites und-Anwendungen enthalten. Wird in *Web.config* Dateien verwendet. |
| [**\<webServices>** Einstellungs Schema](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) | Alle Elemente im Webdienst-Einstellungs Schema. |
| [Webeinstellungs Schema](./web/index.md) | Alle Elemente im Webeinstellungsschema, das Elemente für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS enthält. Wird in *aspnet.config* Dateien verwendet. |

## <a name="remarks"></a>Hinweise

Jede Konfigurationsdatei muss genau ein **\<configuration>** Element enthalten.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
