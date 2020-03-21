---
title: Benutzerdefiniertes Element für SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 04360a796b18cf1e414f1f84bff247a1e9d8ef9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155153"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Benutzerdefiniertes Element für SingleTagSectionHandler

Definiert Einstellungen in einem benutzerdefinierten Konfigurationsabschnitt, der durch \< <xref:System.Configuration.SingleTagSectionHandler> einen Abschnitt>-Elements definiert wird und die Klasse verwendet.

Konfiguration &nbsp; &nbsp;>[** \<**](configuration-element.md) * \<AbschnittName>*

## <a name="syntax"></a>Syntax

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a>Attributes

Attribute und Attributwerte sind benutzerdefinierte.

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<Konfiguration>**](configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keine

## <a name="remarks"></a>Bemerkungen

Das ** \<sectionName>-Element** ist ein benutzerdefiniertes Element, das [** \<**](section-element.md) [** \<**](configsections-element-for-configuration.md) durch ein>-Tag im configSections->-Element definiert wird. Das Konfigurationssystem <xref:System.Collections.IDictionary> gibt ein <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>Objekt zurück, wenn Sie aufrufen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein benutzerdefiniertes Element namens <xref:System.Configuration.SingleTagSectionHandler> ** \<sampleSection>** deklariert, das Einstellungen enthält, die von der Klasse gelesen werden:

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

Dieses Element kann in der Anwendungskonfigurationsdatei, der Computerkonfigurationsdatei (*Machine.config*) und *web.config-Dateien* verwendet werden, die sich nicht auf Anwendungsverzeichnisebene befinden.

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdateischema für .NET Framework](index.md)
