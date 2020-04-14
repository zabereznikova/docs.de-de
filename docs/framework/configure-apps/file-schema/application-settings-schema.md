---
title: Anwendungseinstellungsschema
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 90d471888950347c041b4824b659ce33fda512d7
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242828"
---
# <a name="application-settings-schema"></a>Anwendungseinstellungsschema

Mithilfe von Anwendungseinstellungen können eine Windows Forms- oder ASP.NET-Anwendung anwendungsbezogene und benutzerbezogene Einstellungen speichern und abrufen. In diesem Zusammenhang ist eine *Einstellung* alle Informationen, die spezifisch für die Anwendung oder spezifisch für den aktuellen Benutzer sein können – alles von einer Datenbankverbindungszeichenfolge bis zur bevorzugten Standardfenstergröße des Benutzers.

Standardmäßig verwenden Anwendungseinstellungen in einer Windows <xref:System.Configuration.LocalFileSettingsProvider> Forms-Anwendung die Klasse, die das .NET-Konfigurationssystem verwendet, um Einstellungen in einer XML-Konfigurationsdatei zu speichern. Weitere Informationen zu den Dateien, die von Anwendungseinstellungen verwendet werden, finden Sie unter [Architektur der Anwendungseinstellungen](../../winforms/advanced/application-settings-architecture.md).

Die Anwendungseinstellungen definieren die folgenden Elemente als Teil der konfigurationsdateien, die sie verwendet.

| Element                    | Beschreibung                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | Enthält ** \<** alle Einstellungen>Tags, die für die Anwendung spezifisch sind.                         |
| **\<userEinstellungen>**        | Enthält ** \<** alle Einstellungen>Tags, die für den aktuellen Benutzer spezifisch sind.                        |
| **\<Einstellung>**             | Definiert eine Einstellung. Untergeordnetes Element von ** \<applicationSettings>** oder ** \<userSettings>**. |
| **\<Wert>**               | Definiert den Wert einer Einstellung. Kind ** \< **der Einstellung>.                                   |

## <a name="applicationsettings-element"></a>\<applicationSettings>-Element

Dieses Element ** \<** enthält alle Einstellungen>Tags, die für eine Instanz der Anwendung auf einem Clientcomputer spezifisch sind. Es definiert keine Attribute.

## <a name="usersettings-element"></a>\<userSettings>-Element

Dieses Element ** \<** enthält alle Einstellungen>Tags, die für den Benutzer spezifisch sind, der die Anwendung derzeit verwendet. Es definiert keine Attribute.

## <a name="setting-element"></a>\<Festlegen> Elements

Dieses Element definiert eine Einstellung. Es hat die folgenden Attribute.

| Attribut        | BESCHREIBUNG |
| ---------------- | ----------- |
| **name**         | Erforderlich. Die eindeutige ID der Einstellung. Einstellungen, die über Visual Studio `ProjectName.Properties.Settings`erstellt wurden, werden mit dem Namen gespeichert. |
| **Serializeas** | Erforderlich. Das Format, das zum Serialisieren des Werts in Text verwendet werden soll. Gültige Werte sind:<br><br>- `string`. Der Wert wird als Zeichenfolge <xref:System.ComponentModel.TypeConverter>mit einer serialisiert.<br>- `xml`. Der Wert wird mithilfe der XML-Serialisierung serialisiert.<br>- `binary`. Der Wert wird als textcodierte Binärdatei mithilfe der binären Serialisierung serialisiert.<br />- `custom`. Der Einstellungsanbieter verfügt über inhärente Kenntnisse dieser Einstellung und serialisiert und deserialisiert sie. |

## <a name="value-element"></a>\<Wert>-Element

Dieses Element enthält den Wert einer Einstellung.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine Anwendungseinstellungsdatei, die zwei anwendungsbezogene Und zwei benutzerbezogene Einstellungen definiert:

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

- [Übersicht über Anwendungseinstellungen](../../winforms/advanced/application-settings-overview.md)
- [Architektur der Anwendungseinstellungen](../../winforms/advanced/application-settings-architecture.md)
