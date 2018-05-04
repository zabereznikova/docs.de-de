---
title: '&lt;Deaktivieren Sie&gt; -Element für &lt;"configSections"&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 42a44d66a3f70d0572484adf4c8dd946edf2297f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="clear-element-for-configsections"></a>\<Deaktivieren Sie >-Element für \<ConfigSections >

Löscht alle zuvor definierten Abschnitte und Abschnittsgruppen.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<ConfigSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Deaktivieren Sie >**

## <a name="syntax"></a>Syntax

```xml
<clear/>
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

Die  **\<deaktivieren >** Element entfernt alle Abschnitte und Abschnittsgruppen aus der Anwendung, die weiter oben in der aktuellen Konfigurationsdatei oder auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.

## <a name="example"></a>Beispiel

In diesem Beispiel definiert eine Computerkonfigurationsdatei und einer Anwendungskonfigurationsdatei und zeigt, wie die  **\<deaktivieren >** Element in einer Anwendungskonfigurationsdatei gelöscht zuvor definierten Abschnitte der die Computerkonfigurationsdatei.

Der folgende Konfigurationscode Datei Computer deklariert zwei Abschnitte  **\<SampleSection >** und  **\<AnotherSampleSection >**, die vor der Anwendung gelesen werden die Konfigurationsdatei:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

Der folgende Code für eine Anwendungskonfigurationsdatei löscht alle zuvor deklarierten Abschnitte. Die Anwendung kann nicht verwendet oder Abrufen von Einstellungen in den Abschnitten, die in der Computerkonfigurationsdatei deklariert wurden. Es können jedoch Einstellungen von  **\<AnotherSection >** , da es nach geht die  **\<deaktivieren >** Element.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungskonfigurationsdatei Computerkonfigurationsdatei verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

[Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
