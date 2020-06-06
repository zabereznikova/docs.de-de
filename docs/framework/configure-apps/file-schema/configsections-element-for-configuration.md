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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155348"
---
# <a name="configsections-element-for-configuration"></a>\<configSections>-Element für \<configuration>

Enthält Konfigurations Abschnitts-und Namespace Deklarationen.

[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**

## <a name="attributes"></a>Attribute

Keine

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

|     | BESCHREIBUNG |
| --- | ----------- |
| [**\<section>**](section-element.md) | Enthält eine Konfigurations Abschnitts Deklaration. |
| [**\<sectionGroup>**](sectiongroup-element-for-configsections.md) | Definiert einen Namespace für Konfigurations Abschnitte. |
| [**\<remove>**](remove-element-for-configsections.md) | Entfernt eine vordefinierte Abschnitts-oder Abschnitts Gruppe. |
| [**\<clear>**](clear-element-for-configsections.md) | Löscht alle zuvor definierten Abschnitte und Abschnitts Gruppen. |

## <a name="remarks"></a>Bemerkungen

Wenn dieses Element in einer Konfigurationsdatei gespeichert ist, muss es das erste untergeordnete Element des- **\<configuration>** Elements sein.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie ein Konfigurations Abschnitt definiert und Einstellungen für diesen Abschnitt definiert werden:

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

Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
