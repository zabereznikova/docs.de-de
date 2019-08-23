---
title: Benutzerdefiniertes Element für NameValueSectionHandler und diktarysectionhandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 890269857aaa00ce62195ccb2f4cb184b363b61e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921044"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>Benutzerdefiniertes Element für NameValueSectionHandler und diktarysectionhandler

Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, die <xref:System.Configuration.NameValueSectionHandler> die <xref:System.Configuration.DictionarySectionHandler> -Klasse und die-Klasse verwenden.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp; **\<sectionName>**

## <a name="attributes"></a>Attribute

None

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| Hinzufügen von <xref:System.Configuration.NameValueSectionHandler> > für und [ **\<** ](add-element-for-custom-2.md)<xref:System.Configuration.DictionarySectionHandler>  | Fügt benutzerdefinierte Anwendungseinstellungen hinzu. |
| Entfernen Sie <xref:System.Configuration.NameValueSectionHandler> > für und. [ **\<** ](remove-element-for-custom-2.md)<xref:System.Configuration.DictionarySectionHandler> | Entfernt eine zuvor definierte Einstellung. |
| Löschen von <xref:System.Configuration.NameValueSectionHandler> > für und [ **\<** ](clear-element-for-custom-2.md)<xref:System.Configuration.DictionarySectionHandler> | Löscht alle zuvor definierten Einstellungen in einem Abschnitt. |

## <a name="remarks"></a>Hinweise

**Das\<Element sectionName >** ist ein benutzerdefiniertes Element, das durch einen  **\<Abschnitt >** -Tag im  **\<>** -Element von configabschnitts definiert wird.

In der folgenden Tabelle wird der Objekttyp angezeigt, der von der ConfigurationSettings. GetConfig-Methode für jeden Konfigurations Abschnitts Handler zurückgegeben wird:

| Konfigurations Abschnitts Handler                        | Rückgabetyp                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie Abschnitte deklarieren <xref:System.Configuration.DictionarySectionHandler> , <xref:System.Configuration.NameValueSectionHandler> die die Klassen und verwenden.

Das erste benutzerdefinierte Element ist <xref:System.Configuration.DictionarySectionHandler> `System.dll`  **\<eine "ditionarysample >** ", die die von der-Klasse in der Assembly gelesenen Einstellungen enthält. Das zweite benutzerdefinierte Element ist  **\<mySection >** , das die von der <xref:System.Configuration.NameValueSectionHandler> -Klasse in der `System.dll` Assembly gelesenen Einstellungen enthält.

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
