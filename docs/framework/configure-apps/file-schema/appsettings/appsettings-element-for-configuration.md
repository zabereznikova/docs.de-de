---
title: <appSettings>-Element für <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
ms.openlocfilehash: dcdf8d0f11ae65353da08bba1f8d2fe5ab415c6b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289587"
---
# <a name="appsettings-element-for-configuration"></a>\<AppSettings >-Element für \<Configuration >

Enthält benutzerdefinierte anwendungseinstellung an. Dies ist eine vordefinierte Konfigurationsabschnitt von .NET Framework bereitgestellt.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;**\<appSettings>**

## <a name="syntax"></a>Syntax

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>Attribut

|           | Beschreibung |
| --------- | ----------- |
| **datei**  | Optionales Attribut.<br><br>Gibt einen relativen Pfad zu einer externen Datei, die Konfigurationseinstellungen für die benutzerdefinierte Anwendung enthält. Die angegebene Datei enthält die gleiche Art von Einstellungen, die im angegebenen die  **\<hinzufügen >**,  **\<entfernen >**, und  **\<Löschen >** -Elemente an und verwendet die gleichen Schlüssel-Wert-Paar als dieser Elemente zu formatieren.<br><br>Der angegebene Pfad ist relativ zu der Hauptkonfigurationsdatei. Für eine Windows Forms-Anwendung ist dies der Ordner "binary" (z. B. */Bin/Debug*), nicht der Speicherort der Konfigurationsdatei der Anwendung. Für Web Forms-Anwendungen wird der Pfad relativ zum Stammverzeichnis Anwendung, ist, in denen die *"Web.config"* Datei befindet.<br><br>Beachten Sie, dass die Laufzeit das Attribut ignoriert, wenn die angegebene Datei nicht gefunden werden kann. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<Konfiguration >** Element](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | Fügt eine benutzerdefinierte anwendungseinstellung an. |
| [**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | Löscht alle zuvor definierten Anwendungseigenschaften. |
| [**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | Entfernt eine zuvor definierte anwendungseinstellung an. |

## <a name="remarks"></a>Hinweise

Die  **\<AppSettings >** Element speichert Informationen der benutzerdefinierten Anwendung, wie Datenbank-Verbindungszeichenfolgen, Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine die Anwendung. Die Schlüssel-/Wertpaaren, die im angegebenen die  **\<AppSettings >** Element erfolgt in Code mithilfe der <xref:System.Configuration.ConfigurationSettings> Klasse.

Können Sie die **Datei** -Attribut in der  **\<"appSettings" >** Element der *"Web.config"* und Konfigurationsdateien der Anwendung. Dieses Attribut gibt an, eine Konfigurationsdatei, die zusätzliche Einstellungen bereitstellt oder die angegebenen Einstellungen überschreibt die  **\<AppSettings >** Element. Die **Datei** Attribut in Source Control Team Entwicklungsszenarios, z. B. wenn ein Benutzer möchte, überschreiben Sie die projekteinstellungen, die in einer Anwendungskonfigurationsdatei angegeben verwendet werden kann.

Konfigurationsdateien, die gemäß der **Datei** Attribut muss einen Stammknoten aufweisen  **\<AppSettings >** statt  **\<Configuration >**.

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

Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
