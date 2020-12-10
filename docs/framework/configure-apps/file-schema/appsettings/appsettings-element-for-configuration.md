---
title: <appSettings>-Element für <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: 66260d15768781b7fa3d9397b8e8a7d9ad68ab95
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009793"
---
# <a name="appsettings-element-for-configuration"></a>\<appSettings>-Element für \<configuration>

Enthält benutzerdefinierte Anwendungseinstellungen. Dies ist ein vordefinierter Konfigurations Abschnitt, der vom .NET Framework bereitgestellt wird.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<appSettings>**

## <a name="syntax"></a>Syntax

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>attribute

|           | BESCHREIBUNG |
| --------- | ----------- |
| **datei**  | Optionales Attribut.<br><br>Gibt einen relativen Pfad zu einer externen Datei an, die benutzerdefinierte Anwendungs Konfigurationseinstellungen enthält. Die angegebene Datei enthält die gleichen Einstellungen, die in den **\<add>** Elementen, und angegeben sind, **\<remove>** **\<clear>** und verwendet dasselbe Schlüssel-Wert-Paar-Format wie diese Elemente.<br><br>Der angegebene Pfad ist relativ zur Hauptkonfigurationsdatei. Bei einer Windows Forms Anwendung ist dies der binäre Ordner (z. b. */bin/debug*) und nicht der Speicherort der Anwendungs Konfigurationsdatei. Bei Web Forms-Anwendungen ist der Pfad relativ zum Stamm der Anwendung, in dem sich die Datei *web.config* befindet.<br><br>Die Laufzeit ignoriert das-Attribut, wenn die angegebene Datei nicht gefunden werden kann. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<configuration>**-Element](../configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

|     | BESCHREIBUNG |
| --- | ----------- |
| [**\<add>**](add-element-for-appsettings.md) | Fügt eine benutzerdefinierte Anwendungs Einstellung hinzu. |
| [**\<clear>**](clear-element-for-appsettings.md) | Löscht alle zuvor definierten Anwendungseinstellungen. |
| [**\<remove>**](remove-element-for-appsettings.md) | Entfernt eine zuvor definierte Anwendungs Einstellung. |

## <a name="remarks"></a>Hinweise

Das- **\<appSettings>** Element speichert benutzerdefinierte Konfigurationsinformationen für die Anwendung, z. b. Daten bankverbindungs Zeichenfolgen, Dateipfade, XML-Webdienst-URLs oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung. Der Zugriff auf die im-Element angegebenen Schlüssel-Wert-Paare **\<appSettings>** erfolgt im Code mithilfe der- <xref:System.Configuration.ConfigurationSettings> Klasse.

Sie können das **File** -Attribut im **\<appSettings>** -Element der *Web.config* -und Anwendungs Konfigurationsdatei verwenden. Dieses Attribut gibt eine Konfigurationsdatei an, die zusätzliche Einstellungen bereitstellt oder die im-Element angegebenen Einstellungen überschreibt **\<appSettings>** . Das **File** -Attribut kann in Entwicklungsszenarien der Quell Code Verwaltung verwendet werden, z. b. Wenn ein Benutzer die in einer Anwendungs Konfigurationsdatei angegebenen Projekteinstellungen überschreiben möchte.

Die Konfigurationsdateien, die vom **File** -Attribut angegeben werden, müssen einen Stamm Knoten von anstelle von aufweisen **\<appSettings>** **\<configuration>** .

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

Dieses Element kann in der Anwendungs Konfigurationsdatei, der Computer Konfigurationsdatei (*Machine.config*) und *Web.config* Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdatei Schema für die .NET Framework](../index.md)
