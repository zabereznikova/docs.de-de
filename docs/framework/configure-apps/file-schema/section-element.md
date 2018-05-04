---
title: '&lt;Abschnitt&gt; Element'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 17b44ca93efc26f4732f5fe2926f894257d8f984
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="section-element"></a>\<Abschnitt >-Element

Enthält eine Deklaration der Konfiguration im Abschnitt.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<ConfigSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Abschnitt >**

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<ConfigSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[**\<SectionGroup >**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Abschnitt >**

## <a name="syntax"></a>Syntax

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a>Erforderliche Attribute

|           | Beschreibung |
| --------- | ----------- |
| **name**  | Gibt den Namen des Konfigurationsabschnitts. |
| **Typ**  | Gibt den Namen der Konfiguration im Abschnitt Handler-Klasse, die im Abschnitt aus der Konfigurationsdatei liest. Der Typwert wurde die Syntax "Fully-qualified-section-handler-class-name, einfache Assemblyname". Der einfachen Assemblynamen ist der Stamm-Dateiname ohne die *DLL* Dateierweiterung. |

## <a name="optional-attributes"></a>Optionale Attribute

Die folgenden Attribute gelten nur für ASP.NET-Anwendungen. Das Konfigurationssystem ignoriert diese Attribute für andere Anwendungstypen.

|                     | Beschreibung |
| ------------------- | ----------- |
| **allowDefinition** | Gibt die Konfigurationsdatei an, die in Abschnitt verwendet werden kann. Verwenden Sie einen der folgenden Werte:<br><br>**Überall**<br>Können den Abschnitt in einer beliebigen Konfigurationsdatei verwendet werden. Dies ist die Standardeinstellung.<br>**MachineOnly**<br>Der Abschnitt kann nur in der Computerkonfigurationsdatei verwendet werden (*"Machine.config"*).<br>**MachineToApplication**<br>Können den Abschnitt in der Konfigurationsdatei des Computers oder der Anwendungskonfigurationsdatei verwendet werden. |
| **allowLocation**   | Bestimmt, ob in der Abschnitt verwendet werden kann die  **\<Speicherort >** Element. Verwenden Sie einen der folgenden Werte:<br><br>**true**<br>Im Abschnitt zu verwendenden ermöglicht die  **\<Speicherort >** Element. Dies ist die Standardeinstellung.<br>**false**<br>Im Abschnitt zu verwendenden lässt nicht zu den  **\<Speicherort >** Element. |

## <a name="parent-elements"></a>Übergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<ConfigSections >** Element](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Enthält die Konfiguration im Abschnitt und Namespacedeklarationen. |
| [**\<SectionGroup >** Element](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | Definiert einen Namespace für Konfigurationsabschnitte. |

> [!NOTE]
> Ein  **\<Abschnitt >** Element ist ein untergeordnetes Element des entweder  **\<ConfigSections >** oder  **\<SectionGroup >** jedoch nicht beide.

## <a name="child-elements"></a>Untergeordnete Elemente

Keiner

## <a name="remarks"></a>Hinweise

Deklarieren einen Konfigurationsabschnitt im Wesentlichen wird ein neues Element für die Konfigurationsdatei definiert. Das neue Element enthält Einstellungen, die eine Konfiguration Handler im Abschnitt (d. h. eine Klasse, implementiert die <xref:System.Configuration.IConfigurationSectionHandler> Schnittstelle) liest. Die Attribute und untergeordnete Elemente von einem Abschnitt auf den von den Ihnen definierten richten sich nach den Abschnittshandler, den Sie verwenden, um Ihre Einstellungen zu lesen.

Deklarieren einen Konfigurationsabschnittshandler in der *"Machine.config"* Datei können Sie den Konfigurationsabschnitt in jeder Konfigurationsdatei der Anwendung auf diesem Computer zu verwenden, es sei denn, die **AllowDefinition**Attribut gibt andernfalls an.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht einen Konfigurationsabschnitt zu definieren, und definieren Sie Einstellungen für diesen Abschnitt:

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" 
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungskonfigurationsdatei Computerkonfigurationsdatei verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

[Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
