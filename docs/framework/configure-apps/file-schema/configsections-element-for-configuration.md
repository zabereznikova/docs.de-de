---
title: '&lt;ConfigSections&gt; -Element für &lt;Konfiguration&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: guardrex
ms.author: mairaw
ms.openlocfilehash: f46c84a1674a3e9352d0a4ccda23d44e650a70ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629487"
---
# <a name="configsections-element-for-configuration"></a>\<ConfigSections >-Element für \<Configuration >

Enthält die Konfiguration im Abschnitt und Namespacedeklarationen.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;**\<configSections>**

## <a name="attributes"></a>Attribute

Keine

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) | Enthält die Deklaration einer Konfigurations-Abschnitt. |
| [**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | Definiert einen Namespace für Konfigurationsabschnitte. |
| [**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | Entfernt einen vordefinierten Abschnitt oder Abschnittsgruppe. |
| [**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | Löscht alle zuvor definierten Abschnitte und Abschnittsgruppen. |

## <a name="remarks"></a>Hinweise

Wenn dieses Element in einer Konfigurationsdatei ist, muss es sein, dass das erste untergeordnete Element von der  **\<Configuration >** Element.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie definieren einen Konfigurationsabschnitt aus, und definieren Sie Einstellungen für diesen Abschnitt:

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

Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
