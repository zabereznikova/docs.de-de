---
title: "Schema f&#252;r Anwendungseinstellungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Anwendungseinstellungen, Schema [Windows Forms]"
  - "Konfigurationsschema [.NET Framework], Anwendungseinstellungen"
  - "Schema für Anwendungseinstellungen"
  - "Windows Forms, Anwendungseinstellungsschema"
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
caps.latest.revision: 3
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 3
---
# Schema f&#252;r Anwendungseinstellungen
Anwendungseinstellungen ermöglichen es Windows Forms\- oder ASP.NET\-Anwendungen, Einstellungen im Gültigkeitsbereich der Anwendung und im Gültigkeitsbereich des Benutzers zu speichern und abzurufen.  Eine "Einstellung" beschreibt in diesem Kontext beliebige Informationen, die spezifisch für die Anwendung oder spezifisch für den aktuellen Benutzer sind, also alles von einer Zeichenfolge für die Datenbankverbindung bis zu der vom Benutzer bevorzugten Standardfenstergröße.  
  
 Für Anwendungseinstellungen in einer Windows Forms\-Anwendung wird standardmäßig <xref:System.Configuration.LocalFileSettingsProvider> verwendet, der das .NET\-Konfigurationssystem zum Speichern von Einstellungen in einer XML\-Konfigurationsdatei nutzt.  Weitere Informationen zu den von Anwendungseinstellungen verwendeten Dateien finden Sie unter [Architektur der Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-architecture.md).  
  
 Anwendungseinstellungen definieren die folgenden Elemente als Teil der von ihnen verwendeten Konfigurationsdateien.  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`<applicationSettings>`\-Element|Enthält alle anwendungsspezifischen `<setting>`\-Tags.|  
|`<userSettings>`\-Element|Enthält alle für den aktuellen Benutzer spezifischen `<setting>`\-Tags.|  
|`<setting>`\-Element|Definiert eine Einstellung.  Untergeordnetes Element von `<applicationSettings>` oder `<userSettings>`.|  
|`<value>`\-Element|Definiert den Wert einer Einstellung.  Untergeordnetes Element von `<setting>`.|  
  
## \<applicationSettings\>\-Element  
 Dieses Element enthält alle \<Einstellungstags\>, die einer Instanz der Anwendung auf einem Clientcomputer spezifisch sind.  Es definiert keine Attribute.  
  
## \<userSettings\>\-Element  
 Dieses Element enthält alle \<Einstellungstags\>, die für den Benutzer gelten, der derzeit die Anwendung verwendet.  Es definiert keine Attribute.  
  
## \<Einstellung\>\-Element  
 Dieses Element definiert eine Einstellung.  Es verfügt über folgende Attribute.  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`name`|Erforderlich.  Die eindeutige ID der Einstellung.  Durch Visual Studio erstellte Einstellungen werden mit dem Namen `ProjectName``.Properties.Settings` gespeichert.|  
|`serializedAs`|Erforderlich.  Das Format, das zum Serialisieren des Wertes in Text verwendet werden soll.  Gültige Werte sind:<br /><br /> -   `string`.  Der Wert wird unter Verwendung von <xref:System.ComponentModel.TypeConverter> als Zeichenfolge serialisiert.<br />-   `xml`.  Der Wert wird unter Verwendung der XML\-Serialisierung serialisiert.<br />-   `binary`.  Der Wert wird als textcodierter Binärwert unter Verwendung der binären Serialisierung serialisiert.<br />-   `custom`.  Die Person, die die Einstellung bereitgestellt hat, verfügt über eingehende Kenntnisse dieser Einstellung und wird diese serialisieren und deserialisieren.<br />-   Zur Verwendung der binären oder benutzerdefinierten Serialisierung müssen Sie eine eigene Einstellungsklasse definieren und die binäre oder benutzerdefinierte Serialisierung mithilfe von <xref:System.Configuration.SettingsSerializeAsAttribute> angeben.|  
  
## \<Wert\>\-Element  
 Dieses Element enthält den Wert einer Einstellung.  
  
## Beispiel  
 Im folgenden Codebeispiel wird eine Datei mit Anwendungseinstellungen veranschaulicht, durch die zwei Einstellungen im Gültigkeitsbereich der Anwendung und zwei Einstellungen im Gültigkeitsbereich des Benutzers definiert werden.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <configSections>  
        <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >  
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </sectionGroup>  
        <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >  
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
  
## Siehe auch  
 [Übersicht über Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-overview.md)   
 [Architektur der Anwendungseinstellungen](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)