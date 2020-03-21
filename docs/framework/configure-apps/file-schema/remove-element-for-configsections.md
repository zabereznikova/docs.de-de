---
title: <remove>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154529"
---
# <a name="remove-element-for-configsections"></a>\<Entfernen>-Elements für \<configSections>

Entfernt einen vordefinierten Abschnitt oder eine Vorschnittgruppe.

[**\<Konfiguration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<entfernen sie>**

## <a name="syntax"></a>Syntax

```xml
<remove name="section name or section group name" />
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

Sie können das ** \<>-Element entfernen** verwenden, um Abschnitte und Abschnittsgruppen aus der Anwendung zu entfernen, die auf einer höheren Ebene in der Konfigurationsdateihierarchie definiert wurden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie das ** \<>-Element** in einer Anwendungskonfigurationsdatei verwenden, um einen zuvor in der Maschinenkonfigurationsdatei definierten Abschnitt zu entfernen.

Der folgende Computerkonfigurationsdateicode deklariert den Abschnitt ** \<sampleSection>: **

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

Der folgende Anwendungskonfigurationsdateicode entfernt den ** \<Abschnitt "beispielAbschnitt>.** Nach dem Entfernen kann die Anwendung die Einstellungen in ** \<sampleSection>** nicht abrufen.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungskonfigurationsdatei, der Computerkonfigurationsdatei (*Machine.config*) und *web.config-Dateien* verwendet werden, die sich nicht auf Anwendungsverzeichnisebene befinden.

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdateischema für .NET Framework](index.md)
