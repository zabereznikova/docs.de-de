---
title: <remove>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 9ceffd3194c7df41f12ac6cd6b589602965b4920
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674310"
---
# <a name="remove-element-for-configsections"></a>\<Entfernen Sie >-Element für \<ConfigSections >

Entfernt einen vordefinierten Abschnitt oder Abschnittsgruppe.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a>Syntax

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a>Attribut

|           | Beschreibung |
| --------- | ----------- |
| **name**  | Erforderliches Attribut.<br><br>Gibt den Namen des Abschnitts oder des zu entfernenden Abschnittsgruppe. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<configSections>** Element](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Enthält die Konfiguration im Abschnitt und Namespacedeklarationen. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keiner

## <a name="remarks"></a>Hinweise

Können Sie die  **\<entfernen >** Elements, Abschnitte und Abschnittsgruppen aus Ihrer Anwendung, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden entfernt.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie mit der  **\<entfernen >** Element in einer Anwendungskonfigurationsdatei auf einen Abschnitt, der zuvor in der Computerkonfigurationsdatei definiert zu entfernen.

Der folgende Konfigurationscode Datei Computer deklariert Abschnitt  **\<SampleSection >**:

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

Der folgende Code für eine Anwendungskonfigurationsdatei entfernt die  **\<SampleSection >** Abschnitt. Nach dem entfernen kann nicht die Anwendung rufen Sie die Einstellungen in  **\<SampleSection >**.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
