---
title: Schema für Anwendungseinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 7a4f60571fb4d30793f64c57317bf0b372ae4812
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701910"
---
# <a name="application-settings-schema"></a>Schema für Anwendungseinstellungen

Anwendungseinstellungen ermöglichen eine Windows Forms- oder ASP.NET-ANWENDUNGEN-Anwendung zum Speichern und Abrufen von anwendungsspezifische und benutzerspezifische Einstellungen. In diesem Kontext ein *Einstellung* ist Information, die speziell auf die Anwendung oder für den aktuellen Benutzer spezifisch sein können – alles aus einer Datenbank-Verbindungszeichenfolge, die dem Benutzer die Standardfenstergröße bevorzugte.

Einstellungen für Anwendungen in einer Windows Forms-Anwendung verwendet standardmäßig die <xref:System.Configuration.LocalFileSettingsProvider> -Klasse, die das Konfigurationssystem .NET verwendet wird, um die Einstellungen in eine XML-Konfigurationsdatei zu speichern. Weitere Informationen zu den Dateien, die von den Einstellungen für Anwendungen verwendet, finden Sie unter [Architektur der Anwendungseinstellungen](~/docs/framework/winforms/advanced/application-settings-architecture.md).

Die Anwendungseinstellungen definiert die folgenden Elemente als Teil der verwendeten Konfigurationsdateien.

| Element                    | Beschreibung                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | Enthält alle  **\<Einstellung >** Tags, die spezifisch für die Anwendung.                         |
| **\<userSettings>**        | Enthält alle  **\<Einstellung >** Tags, die spezifisch für den aktuellen Benutzer.                        |
| **\<setting>**             | Definiert eine Einstellung. Untergeordnetes Element des  **\<"ApplicationSettings" >** oder  **\<UserSettings >**. |
| **\<value>**               | Der Wert einer Einstellung wird definiert. Untergeordnetes Element des  **\<Einstellung >**.                                   |

## <a name="applicationsettings-element"></a>\<"ApplicationSettings" >-Element

Dieses Element enthält alle  **\<Einstellung >** Tags, die für eine Instanz der Anwendung auf einem Clientcomputer spezifisch sind. Es definiert keine Attribute.

## <a name="usersettings-element"></a>\<UserSettings >-Element

Dieses Element enthält alle  **\<Einstellung >** Tags, die für den Benutzer spezifisch sind, die die Anwendung derzeit verwendet. Es definiert keine Attribute.

## <a name="setting-element"></a>\<Festlegen von >-Element

Dieses Element definiert eine Einstellung an. Es hat die folgenden Attribute.

| Attribut        | Beschreibung |
| ---------------- | ----------- |
| **name**         | Erforderlich. Die eindeutige ID der Einstellung. Einstellungen, die mit Visual Studio erstellt wurden, werden mit dem Namen gespeichert `ProjectName.Properties.Settings`. |
| **serializedAs** | Erforderlich. Das Format für den Wert in Text zu serialisieren. Gültige Werte sind:<br><br>- `string`. Der Wert wird als Zeichenfolge serialisiert eine <xref:System.ComponentModel.TypeConverter>.<br>- `xml`. Der Wert wird mit XML-Serialisierung serialisiert.<br>- `binary`. Der Wert wird als Text codiert-binär mit binärer Serialisierung serialisiert.<br />- `custom`. Der Einstellungsanbieter inhärenten Kenntnisse über diese Einstellung hat und serialisiert und deserialisiert es. |

## <a name="value-element"></a>\<Wert >-Element

Dieses Element enthält den Wert einer Einstellung an.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine Datei mit den Anwendungseinstellungen, die zwei Einstellungen mit Anwendungsbereich und zwei benutzerspezifische Einstellungen definiert:

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

## <a name="see-also"></a>Siehe auch

- [Übersicht über Anwendungseinstellungen](~/docs/framework/winforms/advanced/application-settings-overview.md)
- [Architektur der Anwendungseinstellungen](~/docs/framework/winforms/advanced/application-settings-architecture.md)
