---
title: Schema für Anwendungseinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 90d471888950347c041b4824b659ce33fda512d7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "81242828"
---
# <a name="application-settings-schema"></a>Schema für Anwendungseinstellungen

Anwendungseinstellungen ermöglichen es einer Windows Forms-oder ASP.NET-Anwendung, anwendungsspezifische und benutzerspezifische Einstellungen zu speichern und abzurufen. In diesem Kontext ist eine *Einstellung* ein beliebiges Informationselement, das spezifisch für die Anwendung oder spezifisch für den aktuellen Benutzer ist – alles von einer Datenbank-Verbindungs Zeichenfolge bis zur bevorzugten Standardfenster Größe des Benutzers.

Standardmäßig verwenden Anwendungseinstellungen in einer Windows Forms Anwendung die- <xref:System.Configuration.LocalFileSettingsProvider> Klasse, die das .NET-Konfigurationssystem zum Speichern von Einstellungen in einer XML-Konfigurationsdatei verwendet. Weitere Informationen zu den von Anwendungseinstellungen verwendeten Dateien finden Sie unter [Architektur der Anwendungseinstellungen](../../winforms/advanced/application-settings-architecture.md).

Anwendungseinstellungen definiert die folgenden Elemente als Teil der Konfigurationsdateien, die Sie verwendet.

| Element                    | Beschreibung                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | Enthält alle **\<setting>** Tags, die für die Anwendung spezifisch sind.                         |
| **\<userSettings>**        | Enthält alle **\<setting>** Tags, die für den aktuellen Benutzer spezifisch sind.                        |
| **\<setting>**             | Definiert eine Einstellung. Untergeordnetes Element von **\<applicationSettings>** oder **\<userSettings>** . |
| **\<value>**               | Definiert den Wert einer Einstellung. Untergeordnetes Element von **\<setting>** .                                   |

## <a name="applicationsettings-element"></a>\<applicationSettings>-Element

Dieses Element enthält alle **\<setting>** Tags, die für eine Instanz der Anwendung auf einem Client Computer spezifisch sind. Es definiert keine Attribute.

## <a name="usersettings-element"></a>\<userSettings>-Element

Dieses Element enthält alle **\<setting>** Tags, die für den Benutzer spezifisch sind, der derzeit die Anwendung verwendet. Es definiert keine Attribute.

## <a name="setting-element"></a>\<setting>-Element

Dieses Element definiert eine Einstellung. Es verfügt über die folgenden Attribute:

| attribute        | BESCHREIBUNG |
| ---------------- | ----------- |
| **name**         | Erforderlich. Die eindeutige ID der Einstellung. Einstellungen, die über Visual Studio erstellt wurden, werden mit dem Namen gespeichert `ProjectName.Properties.Settings` . |
| **SerializeAs** | Erforderlich. Das Format, das zum Serialisieren des Werts in Text verwendet werden soll. Gültige Werte sind:<br><br>- `string`. Der Wert wird als Zeichenfolge mit einem serialisiert <xref:System.ComponentModel.TypeConverter> .<br>- `xml`. Der Wert wird mithilfe der XML-Serialisierung serialisiert.<br>- `binary`. Der Wert wird als Text codierte Binärdatei mit binärer Serialisierung serialisiert.<br />- `custom`. Der Einstellungs Anbieter kennt diese Einstellung und serialisiert und deserialisiert Sie. |

## <a name="value-element"></a>\<value>-Element

Dieses Element enthält den Wert einer Einstellung.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine Anwendungs Einstellungsdatei, die zwei Einstellungen für Anwendungsbereiche und zwei benutzerspezifische Einstellungen definiert:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Anwendungseinstellungen](../../winforms/advanced/application-settings-overview.md)
- [Architektur der Anwendungseinstellungen](../../winforms/advanced/application-settings-architecture.md)
