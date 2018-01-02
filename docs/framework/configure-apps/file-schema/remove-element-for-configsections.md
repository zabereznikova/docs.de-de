---
title: "&lt;Entfernen Sie&gt; -Element für &lt;\"configSections\"&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf2cb49fbeb01ad176a1d24d711cebc97ba14004
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="remove-element-for-configsections"></a>\<Entfernen Sie >-Element für \<ConfigSections >

Entfernt einen vordefinierten Abschnitt oder Abschnittsgruppe.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<ConfigSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Entfernen >**

## <a name="syntax"></a>Syntax

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a>Attribut

|           | Beschreibung |
| --------- | ----------- |
| **name**  | Erforderliches Attribut.<br><br>Gibt den Namen des Abschnitts oder Abschnittsgruppe zu entfernen. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<ConfigSections >** Element](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Enthält die Konfiguration im Abschnitt und Namespacedeklarationen. |

# <a name="child-elements"></a>Untergeordnete Elemente

Keiner

## <a name="remarks"></a>Hinweise

Können Sie die  **\<entfernen >** Element Abschnitte und Abschnittsgruppen aus der Anwendung, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden entfernt.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie die  **\<entfernen >** Element in einer Anwendungskonfigurationsdatei zum Entfernen eines Bereichs, die zuvor in der Computerkonfigurationsdatei definiert.

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

Der folgende Code für eine Anwendungskonfigurationsdatei entfernt die  **\<SampleSection >** Abschnitt. Nach dem entfernen die Anwendung kann nicht die Einstellungen in abrufen  **\<SampleSection >**.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungskonfigurationsdatei Computerkonfigurationsdatei verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

[Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
