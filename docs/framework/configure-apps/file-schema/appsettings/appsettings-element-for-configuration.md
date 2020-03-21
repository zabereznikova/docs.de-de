---
title: <appSettings>-Element für <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: ea341d562f4b163a3a1771da0f20903b7d64bcdf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155530"
---
# <a name="appsettings-element-for-configuration"></a>\<appSettings>-Element für \<Konfigurations->

Enthält benutzerdefinierte Anwendungseinstellungen. Dies ist ein vordefinierter Konfigurationsabschnitt, der von .NET Framework bereitgestellt wird.

Konfiguration &nbsp; &nbsp;>[** \<**](../configuration-element.md) ** \<appEinstellungen>**

## <a name="syntax"></a>Syntax

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>attribute

|           | Beschreibung |
| --------- | ----------- |
| **Datei**  | Optionales Attribut.<br><br>Gibt einen relativen Pfad zu einer externen Datei an, die benutzerdefinierte Anwendungskonfigurationseinstellungen enthält. Die angegebene Datei enthält die gleiche Art von Einstellungen, die in der ** \<Add->** angegeben sind, ** \<>entfernen **und ** \<>** Elemente löschen und das gleiche Schlüssel-Wert-Paarformat wie diese Elemente verwenden.<br><br>Der angegebene Pfad ist relativ zur Hauptkonfigurationsdatei. Bei einer Windows Forms-Anwendung ist dies der Binärordner (z. B. */bin/debug*), nicht der Speicherort der Anwendungskonfigurationsdatei. Bei Web Forms-Anwendungen ist der Pfad relativ zum Anwendungsstamm, in dem sich die *Datei web.config* befindet.<br><br>Die Laufzeit ignoriert das Attribut, wenn die angegebene Datei nicht gefunden werden kann. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [** \<Konfiguration>** Element](../configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<hinzufügen>**](add-element-for-appsettings.md) | Fügt eine benutzerdefinierte Anwendungseinstellung hinzu. |
| [**\<klare>**](clear-element-for-appsettings.md) | Löscht alle zuvor definierten Anwendungseinstellungen. |
| [**\<entfernen sie>**](remove-element-for-appsettings.md) | Entfernt eine zuvor definierte Anwendungseinstellung. |

## <a name="remarks"></a>Bemerkungen

Das ** \<appSettings>-Element** speichert benutzerdefinierte Anwendungskonfigurationsinformationen, z. B. Datenbankverbindungszeichenfolgen, Dateipfade, XML-Webdienst-URLs oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung. Auf die in der <xref:System.Configuration.ConfigurationSettings> ** \<appSettings>-Elemente** angegebenen Schlüssel-Wert-Paare wird im Code mithilfe der Klasse zugegriffen.

Sie können das **Dateiattribut** im ** \<appSettings>-Element** der *Konfigurationsdateien Web.config* und Application verwenden. Dieses Attribut gibt eine Konfigurationsdatei an, die zusätzliche Einstellungen bereitstellt oder die im ** \<appSettings>-Element** angegebenen Einstellungen überschreibt. Das **Dateiattribut** kann in Entwicklungsszenarien für Quellcodeverwaltungsteams verwendet werden, z. B. wenn ein Benutzer die in einer Anwendungskonfigurationsdatei angegebenen Projekteinstellungen überschreiben möchte.

Konfigurationsdateien, die durch das **Dateiattribut** angegeben werden, müssen über einen Stammknoten von ** \<appSettings>** und nicht über ** \<eine Konfiguration>** verfügen.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine externe Anwendungseinstellungsdatei (*custom.config*), die eine benutzerdefinierte Anwendungseinstellung definiert.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

Das folgende Beispiel zeigt eine Anwendungskonfigurationsdatei, die die Einstellung in der externen Einstellungsdatei verarbeitet und eine eigene Anwendungseinstellung festlegt.

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungskonfigurationsdatei, der Computerkonfigurationsdatei (*Machine.config*) und *web.config-Dateien* verwendet werden, die sich nicht auf Anwendungsverzeichnisebene befinden.

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdateischema für .NET Framework](../index.md)
