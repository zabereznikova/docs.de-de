---
title: <sectionGroup>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 746a997e162b0fd370a249b8d039be623b57d77f
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089007"
---
# <a name="sectiongroup-element-for-configsections"></a>\<sectionGroup-> Element für \<configabschnitts->

Definiert einen Namespace für Konfigurations Abschnitte.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp;[ **\<configabschnitts >** ](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup >**

## <a name="syntax"></a>Syntax

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a>Attribut

|           | Beschreibung |
| --------- | ----------- |
| **name**  | Erforderliches Attribut.<br><br>Gibt den Namen der Abschnitts Gruppe an, die Sie definieren. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [ **\<configabschnitts >** Gewisses](configsections-element-for-configuration.md) | Enthält Konfigurations Abschnitts-und Namespace Deklarationen. |

## <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [ **\<Abschnitt >** ](section-element.md) | Enthält eine Konfigurations Abschnitts Deklaration. |

## <a name="remarks"></a>Hinweise

Beim Deklarieren einer Abschnitts Gruppe wird ein containertag für Konfigurations Abschnitte erstellt, und es wird sichergestellt, dass keine Namenskonflikte mit von einer anderen Person definierten Konfigurations Abschnitten bestehen. Sie können **\<sectionGroup->** Elemente in einander Schachteln.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie eine Abschnitts Gruppe deklarieren und Abschnitte innerhalb einer Abschnitts Gruppe deklarieren:

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
