---
title: Application-Einstellungsschema
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7af6342e9c05fc4e6c1bf4daac59db14ccdf22c7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741736"
---
# <a name="application-settings-schema"></a>Application-Einstellungsschema

Anwendungseinstellungen ermöglichen eine Windows Forms- oder ASP.NET-ANWENDUNGEN Anwendung speichern und Abrufen von anwendungsspezifische und benutzerspezifische Einstellungen. In diesem Kontext eine *Einstellung* ist eine Information, die speziell für die Anwendung oder gelten speziell für den aktuellen Benutzer möglicherweise – alles von einer Datenbank-Verbindungszeichenfolge für den Benutzer bevorzugte Standard-Fenstergröße.

Anwendungseinstellungen in einer Windows Forms-Anwendung verwendet standardmäßig die <xref:System.Configuration.LocalFileSettingsProvider> -Klasse, die das Konfigurationssystem .NET verwendet wird, um die Einstellungen in eine XML-Konfigurationsdatei zu speichern. Weitere Informationen zu den Dateien, die von den Anwendungseinstellungen verwendet, finden Sie unter [Architektur der Anwendungseinstellungen](~/docs/framework/winforms/advanced/application-settings-architecture.md).

Die Anwendungseinstellungen definiert die folgenden Elemente im Rahmen der Konfigurationsdateien verwendet.

| Element                    | Beschreibung                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<ApplicationSettings >** | Enthält alle  **\<Einstellung >** Tags, die für die Anwendung spezifisch sind.                         |
| **\<UserSettings >**        | Enthält alle  **\<Einstellung >** Tags für den aktuellen Benutzer spezifisch.                        |
| **\<Festlegen von >**             | Definiert eine Einstellung. Untergeordnetes Element des  **\<ApplicationSettings >** oder  **\<UserSettings >**. |
| **\<value>**               | Definiert eine Einstellung-Wert. Untergeordnetes Element des  **\<Einstellung >**.                                   |

## <a name="applicationsettings-element"></a>\<ApplicationSettings >-Element

Dieses Element enthält alle  **\<Einstellung >** Tags, die mit einer Instanz von der Anwendung auf einem Clientcomputer spezifisch sind. Es definiert keine Attribute.

## <a name="usersettings-element"></a>\<UserSettings >-Element

Dieses Element enthält alle  **\<Einstellung >** Transpondern, die für den Benutzer spezifisch sind, der die Anwendung derzeit verwendet. Es definiert keine Attribute.

## <a name="setting-element"></a>\<Festlegen von >-Element

Dieses Element definiert eine Einstellung an. Es weist folgende Attribute.

| Attribut        | Beschreibung |
| ---------------- | ----------- |
| **name**         | Erforderlich. Die eindeutige ID der Einstellung. Einstellungen, die in der Visual Studio erstellt werden gespeichert, mit dem Namen `ProjectName.Properties.Settings`. |
| **serializedAs** | Erforderlich. Das Format, das zum Serialisieren des Wertes in Text. Gültige Werte sind:<br><br>- `string`. Der Wert wird als eine Zeichenfolge mit serialisiert eine <xref:System.ComponentModel.TypeConverter>.<br>- `xml`. Der Wert wird mithilfe von XML-Serialisierung serialisiert.<br>- `binary`. Der Wert wird als Text-codierte Binärdaten mit binärer Serialisierung serialisiert.<br />- `custom`. Der Einstellungsanbieter Kenntnisse von dieser Einstellung hat und serialisiert und deserialisiert serialisiert. |

## <a name="value-element"></a>\<Wert >-Element

Dieses Element enthält den Wert einer Einstellung.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine Einstellungen Anwendungsdatei, die zwei anwendungsspezifische Einstellungen und zwei benutzerspezifische Einstellungen definiert:

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

[Übersicht über Anwendungseinstellungen](~/docs/framework/winforms/advanced/application-settings-overview.md)   
[Architektur der Anwendungseinstellungen](~/docs/framework/winforms/advanced/application-settings-architecture.md)
