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
ms.openlocfilehash: 0e09ec49024b769c516fd97085904781f64b4486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921251"
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

None

## <a name="parent-element"></a>Übergeordnetes Element

None

## <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [ **\<assemblyBinding>** ](assemblybinding-element-for-configuration.md) | Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.|
| [Schema für Start > Einstellungen  **\<** ](./startup/index.md) | Alle Elemente im Start Einstellungs Schema. |
| [Schema für Lauf Zeit > Einstellungen  **\<** ](./runtime/index.md) | Alle Elemente im Lauf Zeit Einstellungs Schema. |
| [Schema für **System. Runtime. Remoting > Einstellungen \<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) | Alle Elemente im Remoting-Einstellungs Schema. |
| [Schema für **System .net-> Einstellungen \<** ](./network/index.md) | Alle Elemente im Netzwerk Einstellungs Schema. |
| [cryptographySettings > Einstellungs Schema  **\<** ](./cryptography/index.md) | Alle Elemente im kryptografieeinstellungs-Schema. |
| [Schema der Konfigurations > Abschnitte  **\<** ](configuration-sections-schema.md) | Alle Elemente im Konfigurations Abschnitts Einstellungs Schema. |
| [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](./trace-debug/index.md) | Alle Elemente im Ablauf Verfolgungs-und debugeinstellungs Schema. |
| [Schema der ASP.NET-Konfigurationseinstellungen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) | Alle Elemente im ASP.NET-Konfigurations Schema, die Elemente zum Konfigurieren von ASP.NET-Websites und-Anwendungen enthalten. Wird in *Web. config* -Dateien verwendet. |
| [Schema für Webservices-> Einstellungen  **\<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) | Alle Elemente im Webdienst-Einstellungs Schema. |
| [Web Settings Schema (Schema für Webeinstellungen)](./web/index.md) | Alle Elemente im Webeinstellungsschema, das Elemente für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS enthält. Wird in *ASPNET. config* -Dateien verwendet. |

## <a name="remarks"></a>Hinweise

Jede Konfigurationsdatei muss genau ein  **\<Konfigurations >** Element enthalten.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
