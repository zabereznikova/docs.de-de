---
title: <clear> Element für NameValueSectionHandler und DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: ad3ac93b2a7f92cd33787620fc0caa2b632aa072
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705362"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Deaktivieren Sie >-Element für NameValueSectionHandler und DictionarySectionHandler

Löscht alle zuvor definierte Einstellungen in einem Abschnitt.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Syntax

```xml
<clear />
```

## <a name="attributes"></a>Attribute

Keiner

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ------------|
| [**\<sectionName>** Element](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | Definiert die Einstellungen für die benutzerdefinierten Konfigurationsabschnitte, mit denen die <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> Klassen. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keiner

## <a name="remarks"></a>Hinweise

Können Sie die  **\<Löschen >** Element So entfernen Sie alle Einstellungen aus Ihrer Anwendung, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.

## <a name="example"></a>Beispiel

In diesem Beispiel definiert eine Computer-Konfigurationsdatei und eine Anwendungskonfigurationsdatei und zeigt, wie die  **\<Löschen >** Element in der Konfigurationsdatei einer Anwendung zum Entfernen von Abschnitten, die zuvor definiert, der die Computerkonfigurationsdatei.

Der folgende Konfigurationscode Datei Computer deklariert Abschnitt  **\<MySection >**:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

Der folgende Code für eine Anwendungskonfigurationsdatei entfernt alle Einstellungen von  **\<MySection >**. Die Anwendung kann nicht abgerufen werden, die Einstellungen, die in deklariert wurden die in der  **\<MySection >** Abschnitt der Konfigurationsdatei des Computers.

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
