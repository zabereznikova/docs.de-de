---
title: Benutzerdefiniertes Element für SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: a40f35838655f6021af0b2e966335803ec8c16b4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "80635401"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Benutzerdefiniertes Element für SingleTagSectionHandler

Definiert die Einstellungen in einem benutzerdefinierten Konfigurations Abschnitt, der von einem-Element definiert wird, \<section> und verwendet die- <xref:System.Configuration.SingleTagSectionHandler> Klasse.

[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*

## <a name="syntax"></a>Syntax

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a>Attribute

Attribute und Attributwerte sind Benutzer definiert.

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keine

## <a name="remarks"></a>Bemerkungen

Das- **\<sectionName>** Element ist ein benutzerdefiniertes Element, das durch ein- [**\<section>**](section-element.md) Tag im-Element definiert wird [**\<configSections>**](configsections-element-for-configuration.md) Das Konfigurationssystem gibt ein-Objekt zurück, <xref:System.Collections.IDictionary> Wenn aufgerufen wird <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType> .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein benutzerdefiniertes Element namens deklariert **\<sampleSection>** , das von der-Klasse gelesene Einstellungen enthält <xref:System.Configuration.SingleTagSectionHandler> :

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
