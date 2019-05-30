---
title: Benutzerdefiniertes Element für NameValueSectionHandler und DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 8636050b2618d1b2c2da0c08c756b0ed221c7f6f
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300757"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>Benutzerdefiniertes Element für NameValueSectionHandler und DictionarySectionHandler

Definiert die Einstellungen für die benutzerdefinierten Konfigurationsabschnitte, mit denen die <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> Klassen.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)\
&nbsp;&nbsp; **\<sectionName>**

## <a name="attributes"></a>Attribute

Keiner

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

|     | Beschreibung |
| --- | ----------- |
| [ **\<Hinzufügen >** ](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) für <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler>  | Fügt benutzerdefinierte Anwendungseinstellungen hinzu. |
| [ **\<Entfernen Sie >** ](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) für <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> | Entfernt eine zuvor definierte Einstellung. |
| [ **\<Deaktivieren Sie >** ](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) für <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> | Löscht alle zuvor definierte Einstellungen in einem Abschnitt. |

## <a name="remarks"></a>Hinweise

Die  **\<SectionName >** Element ist ein benutzerdefiniertes Element, das definiert, indem eine  **\<Abschnitt >** -Tag in die  **\<ConfigSections >** Element.

Die folgende Tabelle zeigt, dass der Typ des Objekts die ConfigurationSettings.GetConfig-Methode für jede Konfigurationsabschnittshandler zurückgibt:

| Konfigurationsabschnittshandler                        | Rückgabetyp                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie die Abschnitte zu deklarieren, mit denen die <xref:System.Configuration.DictionarySectionHandler> und <xref:System.Configuration.NameValueSectionHandler> Klassen.

Das erste benutzerdefinierte Element ist  **\<DictionarySample >** , das Lesen von Einstellungen enthält die <xref:System.Configuration.DictionarySectionHandler> -Klasse in der `System.dll` Assembly. Das zweite benutzerdefinierte Element ist  **\<MySection >** , das Lesen von Einstellungen enthält die <xref:System.Configuration.NameValueSectionHandler> -Klasse in der `System.dll` Assembly.

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

Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden ( *"Machine.config"* ), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
