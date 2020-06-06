---
title: Benutzerdefiniertes Element für NameValueSectionHandler und diktarysectionhandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: e5c5c6cf5744aa385e6f6700cad623751a4d7427
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215472"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>Benutzerdefiniertes Element für NameValueSectionHandler und diktarysectionhandler

Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, die die <xref:System.Configuration.NameValueSectionHandler> -Klasse und die- <xref:System.Configuration.DictionarySectionHandler> Klasse verwenden.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;**\<sectionName>**

## <a name="attributes"></a>Attribute

Keine

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

|     | BESCHREIBUNG |
| --- | ----------- |
| [**\<add>**](add-element-for-custom-2.md)für <xref:System.Configuration.NameValueSectionHandler> und<xref:System.Configuration.DictionarySectionHandler>  | Fügt benutzerdefinierte Anwendungseinstellungen hinzu. |
| [**\<remove>**](remove-element-for-custom-2.md)für <xref:System.Configuration.NameValueSectionHandler> und<xref:System.Configuration.DictionarySectionHandler> | Entfernt eine zuvor definierte Einstellung. |
| [**\<clear>**](clear-element-for-custom-2.md)für <xref:System.Configuration.NameValueSectionHandler> und<xref:System.Configuration.DictionarySectionHandler> | Löscht alle zuvor definierten Einstellungen in einem Abschnitt. |

## <a name="remarks"></a>Bemerkungen

Das- **\<sectionName>** Element ist ein benutzerdefiniertes Element, das durch ein- **\<section>** Tag im-Element definiert wird **\<configSections>**

In der folgenden Tabelle wird der Objekttyp angezeigt, der von der ConfigurationSettings. GetConfig-Methode für jeden Konfigurations Abschnitts Handler zurückgegeben wird:

| Konfigurations Abschnitts Handler                        | Rückgabetyp                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie Abschnitte deklarieren, die die <xref:System.Configuration.DictionarySectionHandler> Klassen und verwenden <xref:System.Configuration.NameValueSectionHandler> .

Das erste benutzerdefinierte Element ist **\<dictionarySample>** , das die von der- <xref:System.Configuration.DictionarySectionHandler> Klasse in der Assembly gelesenen Einstellungen enthält `System.dll` . Das zweite benutzerdefinierte Element ist **\<mySection>** , das die von der- <xref:System.Configuration.NameValueSectionHandler> Klasse in der Assembly gelesenen Einstellungen enthält `System.dll` .

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

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
