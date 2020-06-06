---
title: <remove>-Element für NameValueSectionHandler und diktarysectionhandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
ms.openlocfilehash: d1e4f3478f6afd6a20c01c6b57a137020ee88f5f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214753"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<remove>-Element für NameValueSectionHandler und diktarysectionhandler

Entfernt eine zuvor definierte Einstellung.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a>Syntax

```xml
<add remove="key" />
```

## <a name="attribute"></a>attribute

|           | BESCHREIBUNG |
| --------- | ----------- |
| **key**   | Erforderliches Attribut.<br><br>Gibt den Namen der zu entfernenden Einstellung an. |

## <a name="parent-element"></a>Übergeordnetes Element

| Element | Beschreibung |
| ------- | ------------|
| [**\<sectionName>** Gewisses](custom-element-2.md) | Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, die die <xref:System.Configuration.NameValueSectionHandler> -Klasse und die- <xref:System.Configuration.DictionarySectionHandler> Klasse verwenden. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keine

## <a name="remarks"></a>Bemerkungen

Sie können das- **\<remove>** Element verwenden, um Einstellungen aus der Anwendung zu entfernen, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdateien definiert wurden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie das- **\<remove>** Element in einer Anwendungs Konfigurationsdatei verwendet wird, um zuvor in der Computer Konfigurationsdatei definierte Einstellungen zu entfernen.

Der folgende Computer Konfigurationsdatei-Code deklariert den-Abschnitt **\<mySection>** und fügt ihm zwei Einstellungen hinzu `key1` `key2` :

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

Mit dem folgenden Anwendungs Konfigurationsdatei-Code wird die `key2` Einstellung aus entfernt **\<mySection>** :

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

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
