---
title: <sectionGroup>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 750708483f9680745eef4531d86fa7ecaa329f51
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301193"
---
# <a name="sectiongroup-element-for-configsections"></a>\<SectionGroup >-Element für \<ConfigSections >

Definiert einen Namespace für Konfigurationsabschnitte.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup>**

## <a name="syntax"></a>Syntax

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a>Attribut

|           | Beschreibung |
| --------- | ----------- |
| **name**  | Erforderliches Attribut.<br><br>Gibt den Namen der Abschnittsgruppe, die Sie definieren. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [ **\<configSections>** Element](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Enthält die Konfiguration im Abschnitt und Namespacedeklarationen. |

## <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [ **\<section>** ](~/docs/framework/configure-apps/file-schema/section-element.md) | Enthält die Deklaration einer Konfigurations-Abschnitt. |

## <a name="remarks"></a>Hinweise

Deklarieren einer Abschnittsgruppe erstellt ein Containertag für Konfigurationsabschnitte und stellt sicher, dass keine Namenskonflikte mit Konfigurationsabschnitte, die von einer anderen Person definiert. Sie können schachteln  **\<SectionGroup >** Elemente in einem anderen.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt das Deklarieren einer Abschnittsgruppe und Abschnitte innerhalb einer Abschnittsgruppe deklarieren:

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

Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden ( *"Machine.config"* ), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
