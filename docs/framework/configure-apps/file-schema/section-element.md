---
title: <section> element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 88f74c02ef627e9136e4437ffa150c36445266a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153728"
---
# <a name="section-element"></a>\<Abschnitt>-Element

Enthält eine Konfigurationsabschnittsdeklaration.

[**\<Konfiguration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Abschnitt>**

[**\<Konfiguration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGruppe>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Abschnitt>**

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
| **Name**  | Gibt den Namen des Konfigurationsabschnitts an. |
| **Typ**  | Gibt den Namen der Konfigurationsabschnittshandlerklasse an, die den Abschnitt aus der Konfigurationsdatei liest. Der Typwert hat die Syntax "fully-qualified-section-handler-class-name, simple-assembly-name". Der einfache Assemblyname ist der Root-Dateiname ohne die *Dateierweiterung .dll.* |

## <a name="optional-attributes"></a>Optionale Attribute

Die folgenden Attribute gelten nur für ASP.NET Anwendungen. Das Konfigurationssystem ignoriert diese Attribute für andere Anwendungstypen.

|                     | Beschreibung |
| ------------------- | ----------- |
| **Allowdefinition** | Gibt an, in welcher Konfigurationsdatei der Abschnitt verwendet werden kann. Verwenden Sie einen der folgenden Werte:<br><br>**Überall**<br>Ermöglicht die Verwendung des Abschnitts in jeder Konfigurationsdatei. Dies ist die Standardoption.<br>**MachineOnly**<br>Lässt die Verwendung des Abschnitts nur in der Maschinenkonfigurationsdatei (*Machine.config*) zu.<br>**MachineToApplication**<br>Ermöglicht die Verwendung des Abschnitts in der Maschinenkonfigurationsdatei oder in der Anwendungskonfigurationsdatei. |
| **allowLocation**   | Bestimmt, ob der Abschnitt ** \<** innerhalb der Position>Elements verwendet werden kann. Verwenden Sie einen der folgenden Werte:<br><br>**true**<br>Ermöglicht die Verwendung des ** \<** Abschnitts innerhalb der Position>Elements. Dies ist die Standardoption.<br>**false**<br>Lässt nicht zu, dass der ** \<** Abschnitt innerhalb der Position>Elements verwendet wird. |

## <a name="parent-elements"></a>Übergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [** \<configSections>** Element](configsections-element-for-configuration.md) | Enthält Konfigurationsabschnittund- und Namespacedeklarationen. |
| [** \<sectionGruppe>** Element](sectiongroup-element-for-configsections.md) | Definiert einen Namespace für Konfigurationsabschnitte. |

> [!NOTE]
> Ein ** \<Abschnitt>-Element** ist ein untergeordnetes Element von ** \<configSections>** oder ** \<sectionGroup>** aber nicht beides.

## <a name="child-elements"></a>Untergeordnete Elemente

Keine

## <a name="remarks"></a>Bemerkungen

Durch das Deklarieren eines Konfigurationsabschnitts wird im Wesentlichen ein neues Element für die Konfigurationsdatei definiert. Das neue Element enthält Einstellungen, die ein Konfigurationsabschnittshandler <xref:System.Configuration.IConfigurationSectionHandler> (d. h. eine Klasse, die die Schnittstelle implementiert) liest. Die Attribute und untergeordneten Elemente eines Abschnitts, den Sie definieren, hängen vom Abschnittshandler ab, den Sie zum Lesen Ihrer Einstellungen verwenden.

Wenn Sie einen Konfigurationsabschnittshandler in der *Datei Machine.config* deklarieren, können Sie den Konfigurationsabschnitt in jeder Anwendungskonfigurationsdatei auf diesem Computer verwenden, es sei denn, das **allowDefinition-Attribut** gibt etwas anderes an.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie einen Konfigurationsabschnitt definieren und Einstellungen für diesen Abschnitt definieren:

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

Dieses Element kann in der Anwendungskonfigurationsdatei, der Computerkonfigurationsdatei (*Machine.config*) und *web.config-Dateien* verwendet werden, die sich nicht auf Anwendungsverzeichnisebene befinden.

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdateischema für .NET Framework](index.md)
