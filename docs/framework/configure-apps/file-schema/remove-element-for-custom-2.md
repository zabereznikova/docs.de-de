---
title: <remove>-Element für "NameValueSectionHandler" und "diktarysectionhandler"
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6cdd5833e14da1ab5185e56dce1190adfee4a2bf
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089039"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<> Element für NameValueSectionHandler und "diktarysectionhandler" entfernen

Entfernt eine zuvor definierte Einstellung.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp;[ **\<sectionName->** ](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<entfernen >**

## <a name="syntax"></a>Syntax

```xml
<add remove="key" />
```

## <a name="attribute"></a>Attribut

|           | Beschreibung |
| --------- | ----------- |
| **key**   | Erforderliches Attribut.<br><br>Gibt den Namen der zu entfernenden Einstellung an. |

## <a name="parent-element"></a>Übergeordnetes Element

| Element | Beschreibung |
| ------- | ------------|
| [ **\<sectionName >** Gewisses](custom-element-2.md) | Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, in denen die Klassen <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> verwendet werden. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keiner

## <a name="remarks"></a>Hinweise

Sie können das **\<remove >** -Element verwenden, um Einstellungen aus der Anwendung zu entfernen, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie das **\<remove >** -Elements in einer Anwendungs Konfigurationsdatei verwendet wird, um die zuvor in der Computer Konfigurationsdatei definierten Einstellungen zu entfernen.

Der folgende Computer Konfigurationsdatei-Code deklariert den Abschnitt **\<mySection >** und fügt ihm zwei Einstellungen hinzu, `key1` und `key2`:

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

Der folgende Anwendungs Konfigurationsdatei-Code entfernt die `key2` Einstellung aus **\<mySection->** :

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
