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
ms.openlocfilehash: 295cb8ee77c3042dc5742fb23cf4bbcd085b4d36
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659214"
---
# <a name="section-element"></a>\<Abschnitt >-Element

Enthält die Deklaration einer Konfigurations-Abschnitt.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Abschnitt >**

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

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
| **Typ**  | Gibt den Namen der Konfiguration im Abschnitt Handler-Klasse, die im Abschnitt aus der Konfigurationsdatei liest. Der Typwert muss es sich um die Syntax "Fully-qualified-section-handler-class-name, Simple-Assembly-Name". Der einfachen Assemblynamen ist der Stamm-Dateiname ohne die *DLL* Dateierweiterung. |

## <a name="optional-attributes"></a>Optionale Attribute

Die folgenden Attribute gelten nur für ASP.NET-Anwendungen zur Verfügung. Das Konfigurationssystem ignoriert diese Attribute für andere Anwendungstypen.

|                     | Beschreibung |
| ------------------- | ----------- |
| **allowDefinition** | Gibt die Konfigurationsdatei an, die in Abschnitt verwendet werden kann. Verwenden Sie einen der folgenden Werte:<br><br>**Überall**<br>Können den Abschnitt in den Konfigurationsdateien verwendet werden. Dies ist die Standardeinstellung.<br>**MachineOnly**<br>Der Abschnitt kann nur in der Computerkonfigurationsdatei verwendet werden (*"Machine.config"*).<br>**MachineToApplication**<br>Können den Abschnitt in der Konfigurationsdatei des Computers oder der Konfigurationsdatei der Anwendung verwendet werden. |
| **allowLocation**   | Bestimmt, ob im Abschnitt kann, in verwendet werden der  **\<Speicherort >** Element. Verwenden Sie einen der folgenden Werte:<br><br>**true**<br>Der Abschnitt kann verwendet werden die  **\<Speicherort >** Element. Dies ist die Standardeinstellung.<br>**false**<br>Im Abschnitt zu verwendenden lässt nicht zu den  **\<Speicherort >** Element. |

## <a name="parent-elements"></a>Übergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<configSections>** Element](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Enthält die Konfiguration im Abschnitt und Namespacedeklarationen. |
| [**\<sectionGroup>** Element](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | Definiert einen Namespace für Konfigurationsabschnitte. |

> [!NOTE]
> Ein  **\<Abschnitt >** Element ist ein untergeordnetes Element des entweder  **\<ConfigSections >** oder  **\<SectionGroup >** aber nicht beide.

## <a name="child-elements"></a>Untergeordnete Elemente

Keine

## <a name="remarks"></a>Hinweise

Deklarieren im Wesentlichen einen Konfigurationsabschnitt definiert ein neues Element für die Konfigurationsdatei an. Das neue Element enthält Einstellungen, die eine Konfiguration Handler im Abschnitt (d. h. eine Klasse, implementiert die <xref:System.Configuration.IConfigurationSectionHandler> Schnittstelle) liest. Die Attribute und untergeordneten Elemente eines Abschnitts, die Sie definieren, hängt von der Abschnittshandler, die, den Sie verwenden, um Ihre Einstellungen zu lesen.

Deklarieren einen Konfigurationsabschnittshandler in der *"Machine.config"* Datei können Sie Abschnitt "Konfiguration" in den Konfigurationsdateien der Anwendung auf diesem Computer verwenden, es sei denn, die **AllowDefinition**Attribut angibt.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie definieren einen Konfigurationsabschnitt aus, und definieren Sie Einstellungen für diesen Abschnitt:

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

Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
