---
title: <add> Element für NameValueSectionHandler und DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 3bbe4ad6559e324db5853b95e797f50a7b908dcb
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301431"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Hinzufügen >-Element für NameValueSectionHandler und DictionarySectionHandler

Fügt benutzerdefinierte Anwendungseinstellungen hinzu. Jede  **\<hinzufügen >** -Tag enthält ein Schlüssel/Wert-Paar.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[ **\<sectionName>** ](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**

## <a name="syntax"></a>Syntax

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a>Attribute

| Attribut | Beschreibung |
| --------- | ----------- |
| **key**   | Erforderliches Attribut.<br><br>Gibt den Namen der Einstellung. |
| **value** | Erforderliches Attribut.<br><br>Gibt den Wert der Einstellung. |

## <a name="parent-element"></a>Übergeordnetes Element

| Element | Beschreibung |
| ------- | ------------|
| [ **\<sectionName>** Element](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | Definiert die Einstellungen für die benutzerdefinierten Konfigurationsabschnitte, mit denen die <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> Klassen. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keiner

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie zum Definieren eines benutzerdefinierten Konfigurationsabschnitts und Verwenden der  **\<hinzufügen >** Element, Einstellungen in den Abschnitt zu speichern:

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

Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden ( *"Machine.config"* ), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
