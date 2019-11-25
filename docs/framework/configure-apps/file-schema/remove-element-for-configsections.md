---
title: <remove>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efc7208aa51cbf6abdb2fe151d48071c0aa95b5c
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089054"
---
# <a name="remove-element-for-configsections"></a>\<> Element für \<configabschnitts entfernen >

Entfernt eine vordefinierte Abschnitts-oder Abschnitts Gruppe.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp;[ **\<configabschnitts >** ](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<entfernen >**

## <a name="syntax"></a>Syntax

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a>Attribut

|           | Beschreibung |
| --------- | ----------- |
| **name**  | Erforderliches Attribut.<br><br>Gibt den Namen des Abschnitts oder der Abschnitts Gruppe an, der entfernt werden soll. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [ **\<configabschnitts >** Gewisses](configsections-element-for-configuration.md) | Enthält Konfigurations Abschnitts-und Namespace Deklarationen. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keiner

## <a name="remarks"></a>Hinweise

Sie können das **\<remove >** -Element verwenden, um Abschnitts-und Abschnitts Gruppen aus der Anwendung zu entfernen, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie das **\<remove >** -Elements in einer Anwendungs Konfigurationsdatei verwendet wird, um einen Abschnitt zu entfernen, der zuvor in der Computer Konfigurationsdatei definiert wurde.

Der folgende Code der Computer Konfigurationsdatei deklariert den Abschnitt **\<sampleSection->** :

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

Der folgende Anwendungs Konfigurationsdatei-Code entfernt den Abschnitt **\<Sample section >** . Nach dem Entfernen kann die Anwendung die Einstellungen nicht mehr in **\<sampleSection->** abrufen.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
