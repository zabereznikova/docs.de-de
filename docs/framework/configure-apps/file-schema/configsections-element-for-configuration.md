---
title: <configSections>-Element für <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6024144b6f12df22369366f04c3cbad02c5011d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119020"
---
# <a name="configsections-element-for-configuration"></a>\<configabschnitts > Element für \<Configuration >

Enthält Konfigurations Abschnitts-und Namespace Deklarationen.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; **\<configSections>**

## <a name="attributes"></a>Attribute

Keine

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [ **\<Abschnitt >** ](section-element.md) | Enthält eine Konfigurations Abschnitts Deklaration. |
| [ **\<sectionGroup>** ](sectiongroup-element-for-configsections.md) | Definiert einen Namespace für Konfigurations Abschnitte. |
| [ **\<remove>** ](remove-element-for-configsections.md) | Entfernt eine vordefinierte Abschnitts-oder Abschnitts Gruppe. |
| [ **\<clear>** ](clear-element-for-configsections.md) | Löscht alle zuvor definierten Abschnitte und Abschnitts Gruppen. |

## <a name="remarks"></a>Hinweise

Wenn dieses Element in einer Konfigurationsdatei gespeichert ist, muss es das erste untergeordnete Element des **\<Configuration >** -Elements sein.

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

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
