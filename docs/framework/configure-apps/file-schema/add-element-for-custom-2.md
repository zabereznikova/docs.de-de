---
title: <add>-Element für "NameValueSectionHandler" und "diktarysectionhandler"
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac07fc9ba6f030209a5e0d0160689fab95bc1b4a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088764"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<> Element für NameValueSectionHandler und "diktarysectionhandler" hinzufügen

Fügt benutzerdefinierte Anwendungseinstellungen hinzu. Jede **\<Add >** -Tags enthält ein Schlüssel-Wert-Paar.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp;[ **\<sectionName->** ](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<hinzufügen >**

## <a name="syntax"></a>Syntax

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a>Attribute

| Attribut | Beschreibung |
| --------- | ----------- |
| **key**   | Erforderliches Attribut.<br><br>Gibt den Namen der Einstellung an. |
| **Wert** | Erforderliches Attribut.<br><br>Gibt den Wert der Einstellung an. |

## <a name="parent-element"></a>Übergeordnetes Element

| Element | Beschreibung |
| ------- | ------------|
| [ **\<sectionName >** Gewisses](custom-element-2.md) | Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, in denen die Klassen <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> verwendet werden. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keiner

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie ein benutzerdefinierter Konfigurations Abschnitt definiert wird und wie das **\<Add >** -Element verwendet wird, um Einstellungen im-Abschnitt zu platzieren:

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
