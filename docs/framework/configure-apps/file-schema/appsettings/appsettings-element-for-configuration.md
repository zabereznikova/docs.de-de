---
title: '&lt;"appSettings"&gt; -Element für &lt;Konfiguration&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
ms.openlocfilehash: d17400536b911ce0be4d2bf105b0b4d99d0916df
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742964"
---
# <a name="appsettings-element-for-configuration"></a>\<"appSettings" >-Element für \<Configuration >

Enthält Einstellungen, die benutzerdefinierte Anwendung. Dies ist eine vordefinierte Konfigurationsabschnitt, der von .NET Framework bereitgestellt werden.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;**\<"appSettings" >**

## <a name="syntax"></a>Syntax

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>Attribut

|           | Beschreibung |
| --------- | ----------- |
| **datei**  | Optionales Attribut.<br><br>Gibt einen relativen Pfad zu einer externen Datei mit benutzerdefinierten Anwendung-Konfigurationseinstellungen an. Die angegebene Datei enthält die gleiche Art von Einstellungen, die im angegebenen der  **\<hinzufügen >**,  **\<entfernen >**, und  **\<deaktivieren >** Elemente und verwendet den gleichen Schlüssel-Wert-Paar als diese Elemente zu formatieren.<br><br>Der angegebene Pfad ist relativ zu der Hauptkonfigurationsdatei. Für eine Windows Forms-Anwendung, die dies ist die binäre Ordner (z. B. */Bin/Debug*), nicht den Speicherort der Konfigurationsdatei der Anwendung. Für Web Forms-Anwendungen ist der Pfad relativ zum Stammverzeichnis Anwendung, in denen die *"Web.config"* Datei befindet.<br><br>Beachten Sie, dass die Laufzeit das Attribut ignoriert, wenn die angegebene Datei nicht gefunden werden kann. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<Konfiguration >** Element](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | Fügt eine benutzerdefinierte Anwendung-Einstellung. |
| [**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | Löscht alle zuvor definierten Anwendungseigenschaften. |
| [**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | Entfernt eine zuvor definierte anwendungseinstellung an. |

## <a name="remarks"></a>Hinweise

Die  **\<"appSettings" >** Element speichert benutzerdefinierte Anwendungskonfigurationsinformationen wie Datenbankverbindungszeichenfolgen, Dateipfade, XML-Webdienst-URLs oder anderen benutzerdefinierten Konfigurationsinformationen für eine die Anwendung. Im angegebenen Schlüssel/Wert-Paare der  **\<"appSettings" >** Element erfolgt in Code mit der <xref:System.Configuration.ConfigurationSettings> Klasse.

Können Sie die **Datei** Attribut in der  **\<"appSettings" >** Element von der *"Web.config"* und Anwendungskonfigurationsdateien. Dieses Attribut gibt an, eine Konfigurationsdatei, die zusätzliche Einstellungen oder die festgelegten Einstellungen überschreibt die  **\<"appSettings" >** Element. Die **Datei** Attribut in Source Control Team Entwicklungsszenarien z. B. wenn ein Benutzer in einer Anwendungskonfigurationsdatei angegebenen projekteinstellungen außer Kraft setzen möchte genutzt werden.

Konfigurationsdateien gemäß der **Datei** Attribut benötigen einen Stammknoten des  **\<"appSettings" >** statt  **\<Configuration >**.

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

Dieses Element kann in der Anwendungskonfigurationsdatei Computerkonfigurationsdatei verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

[Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
