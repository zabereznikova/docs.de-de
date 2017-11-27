---
title: '&lt;Deaktivieren Sie&gt; NameValueSectionHandler und DictionarySectionHandler-Element'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e91c3d9693cf656a8c56c82d1997f74c2b3d64c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Deaktivieren Sie >-Element für NameValueSectionHandler und DictionarySectionHandler

Löscht alle zuvor definierte Einstellungen in einem Abschnitt.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<SectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Deaktivieren Sie >**

## <a name="syntax"></a>Syntax

```xml
<clear />
```

## <a name="attributes"></a>Attribute

Keine

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ------------|
| [**\<SectionName >** Element](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | Definiert die Einstellungen für benutzerdefinierte Konfigurationsabschnitte, mit denen die <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> Klassen. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keine

## <a name="remarks"></a>Hinweise

Sie können die  **\<deaktivieren >** Element So entfernen Sie alle Einstellungen von Ihrer Anwendung, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.

## <a name="example"></a>Beispiel

In diesem Beispiel definiert eine Computerkonfigurationsdatei und einer Anwendungskonfigurationsdatei und zeigt, wie die  **\<deaktivieren >** Element in einer Anwendungskonfigurationsdatei gelöscht zuvor definierten Abschnitte der die Computerkonfigurationsdatei.

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

Der folgende Code für eine Anwendungskonfigurationsdatei entfernt alle Einstellungen von  **\<MySection >**. Die Anwendung kann nicht abgerufen werden, die Einstellungen, die im deklariert wurden die in der  **\<MySection >** Abschnitt der Konfigurationsdatei des Computers.

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungskonfigurationsdatei Computerkonfigurationsdatei verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

[Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
