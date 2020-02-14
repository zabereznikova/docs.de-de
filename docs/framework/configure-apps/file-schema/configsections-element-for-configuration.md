---
title: <configSections>-Element für <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 5b71eb81769db1188f97b1646a608df172ff56c5
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214824"
---
# <a name="configsections-element-for-configuration"></a>\<configabschnitts > Element für \<Configuration >

Enthält Konfigurations Abschnitts-und Namespace Deklarationen.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; **\<configabschnitts aus >**

## <a name="attributes"></a>Attributes

Keine

## <a name="parent-element"></a>Übergeordnetes Element

|     | BESCHREIBUNG |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

|     | BESCHREIBUNG |
| --- | ----------- |
| [ **\<Abschnitt >** ](section-element.md) | Enthält eine Konfigurations Abschnitts Deklaration. |
| [ **\<sectionGroup >** ](sectiongroup-element-for-configsections.md) | Definiert einen Namespace für Konfigurations Abschnitte. |
| [ **\<remove>** ](remove-element-for-configsections.md) | Entfernt eine vordefinierte Abschnitts-oder Abschnitts Gruppe. |
| [ **\<clear>** ](clear-element-for-configsections.md) | Löscht alle zuvor definierten Abschnitte und Abschnitts Gruppen. |

## <a name="remarks"></a>Bemerkungen

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

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
