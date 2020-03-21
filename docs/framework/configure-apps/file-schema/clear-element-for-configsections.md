---
title: <clear>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155426"
---
# <a name="clear-element-for-configsections"></a>\<clear>-Element für \<configSections>

Löscht alle zuvor definierten Abschnitte und Abschnittsgruppen.

&nbsp; &nbsp; &nbsp; &nbsp; [** \<Konfiguration>**](configuration-element.md) &nbsp; &nbsp; [** \<configSections**](configsections-element-for-configuration.md) **>\<klare>**

## <a name="syntax"></a>Syntax

```xml
<clear/>
```

## <a name="attribute"></a>attribute

|           | Beschreibung |
| --------- | ----------- |
| **Name**  | Erforderliches Attribut.<br><br>Gibt den Namen des zu entfernenden Abschnitts oder der Zu entfernenden Abschnittsgruppe an. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [** \<configSections>** Element](configsections-element-for-configuration.md) | Enthält Konfigurationsabschnittund- und Namespacedeklarationen. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keine

## <a name="remarks"></a>Bemerkungen

Das ** \<clear>-Element** entfernt alle Abschnitte und Abschnittsgruppen aus der Anwendung, die zuvor in der aktuellen Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationsdateihierarchie definiert wurden.

## <a name="example"></a>Beispiel

In diesem Beispiel werden eine Maschinenkonfigurationsdatei und eine Anwendungskonfigurationsdatei definiert und gezeigt, wie das ** \<>-Element** in einer Anwendungskonfigurationsdatei zum Löschen von Abschnitten verwendet wird, die zuvor in der Maschinenkonfigurationsdatei definiert wurden.

Der folgende Computerkonfigurationsdateicode deklariert zwei Abschnitte, ** \<sampleSection>** und ** \<anotherSampleSection>**, die vor der Anwendungskonfigurationsdatei gelesen werden:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

Der folgende Anwendungskonfigurationsdateicode löscht alle zuvor deklarierten Abschnitte. Die Anwendung kann keine Einstellungen in einem der Abschnitte verwenden oder abrufen, die in der Computerkonfigurationsdatei deklariert wurden. Es können jedoch Einstellungen von ** \<einem anderenAbschnitt**>verwendet werden, da es nach dem ** \<klaren>-Element** kommt.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungskonfigurationsdatei, der Computerkonfigurationsdatei (*Machine.config*) und *web.config-Dateien* verwendet werden, die sich nicht auf Anwendungsverzeichnisebene befinden.

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdateischema für .NET Framework](index.md)
