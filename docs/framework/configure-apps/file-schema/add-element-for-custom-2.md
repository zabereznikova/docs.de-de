---
title: <add>-Element für NameValueSectionHandler und diktarysectionhandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: ec6d5045580e887de5f05a05c8f39fa62c6e3f2e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921333"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Add >-Element für NameValueSectionHandler und "diktarysectionhandler"

Fügt benutzerdefinierte Anwendungseinstellungen hinzu. **Jedes\<Add >** -Tag enthält ein Schlüssel-Wert-Paar.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<sectionName>** ](custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**

## <a name="syntax"></a>Syntax

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a>Attribute

| Attribut | Beschreibung |
| --------- | ----------- |
| **key**   | Erforderliches Attribut.<br><br>Gibt den Namen der Einstellung an. |
| **value** | Erforderliches Attribut.<br><br>Gibt den Wert der Einstellung an. |

## <a name="parent-element"></a>Übergeordnetes Element

| Element | Beschreibung |
| ------- | ------------|
| [sectionName > Element  **\<** ](custom-element-2.md) | Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, die <xref:System.Configuration.NameValueSectionHandler> die <xref:System.Configuration.DictionarySectionHandler> -Klasse und die-Klasse verwenden. |

## <a name="child-elements"></a>Untergeordnete Elemente

None

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie ein benutzerdefinierter Konfigurations Abschnitt definiert wird und wie mit dem  **\<Add >** -Element Einstellungen in den Abschnitt eingefügt werden:

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
