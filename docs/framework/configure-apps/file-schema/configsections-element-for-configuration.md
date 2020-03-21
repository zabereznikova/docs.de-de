---
title: <configSections>-Element für <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 55116f1fe6fdffffea8f26d8a4de783c7305ada3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155348"
---
# <a name="configsections-element-for-configuration"></a>\<configSections>-Element für \<die Konfiguration>

Enthält Konfigurationsabschnittund- und Namespacedeklarationen.

Konfiguration &nbsp; &nbsp;>[** \<**](configuration-element.md) **configSections \<>**

## <a name="attributes"></a>Attributes

Keine

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<Konfiguration>**](configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<Abschnitt>**](section-element.md) | Enthält eine Konfigurationsabschnittsdeklaration. |
| [**\<sectionGruppe>**](sectiongroup-element-for-configsections.md) | Definiert einen Namespace für Konfigurationsabschnitte. |
| [**\<entfernen sie>**](remove-element-for-configsections.md) | Entfernt einen vordefinierten Abschnitt oder eine Vorschnittgruppe. |
| [**\<klare>**](clear-element-for-configsections.md) | Löscht alle zuvor definierten Abschnitte und Abschnittsgruppen. |

## <a name="remarks"></a>Bemerkungen

Wenn sich dieses Element in einer Konfigurationsdatei befindet, ** \<** muss es das erste untergeordnete Element der Konfiguration>-Elements sein.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie einen Konfigurationsabschnitt definieren und Einstellungen für diesen Abschnitt definieren:

```xml
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

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungskonfigurationsdatei, der Computerkonfigurationsdatei (*Machine.config*) und *web.config-Dateien* verwendet werden, die sich nicht auf Anwendungsverzeichnisebene befinden.

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdateischema für .NET Framework](index.md)
