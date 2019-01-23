---
title: '&lt;Entfernen Sie&gt; -Element für NameValueSectionHandler und DictionarySectionHandler'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: guardrex
ms.author: mairaw
ms.openlocfilehash: ece76f06f5ecbf47302b62a5e546cc13298106bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535579"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Entfernen Sie >-Element für NameValueSectionHandler und DictionarySectionHandler

Entfernt eine zuvor definierte Einstellung.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a>Syntax

```xml
<add remove="key" />
```

## <a name="attribute"></a>Attribut

|           | Beschreibung |
| --------- | ----------- |
| **key**   | Erforderliches Attribut.<br><br>Gibt den Namen der Einstellung, um Sie zu entfernen. |

## <a name="parent-element"></a>Übergeordnetes Element

| Element | Beschreibung |
| ------- | ------------|
| [**\<sectionName>** Element](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | Definiert die Einstellungen für die benutzerdefinierten Konfigurationsabschnitte, mit denen die <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> Klassen. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keine

## <a name="remarks"></a>Hinweise

Sie können die  **\<entfernen >** Elements, das Einstellungen entfernt, von der Anwendung, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie mit der  **\<entfernen >** Element in einer Anwendungskonfigurationsdatei, entfernen Sie die Einstellungen, die zuvor in der Computerkonfigurationsdatei definiert.

Der folgende Konfigurationscode Datei Computer deklariert Abschnitt  **\<MySection >** und fügt zwei Einstellungen `key1` und `key2`, damit:

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

Der folgende Code für eine Anwendungskonfigurationsdatei entfernt die `key2` aus  **\<MySection >**:

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
