---
title: <clear>-Element für NameValueSectionHandler und diktarysectionhandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
ms.openlocfilehash: f6d860f35d22002030ffa3d09dd0d8a96116bf5e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214744"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<clear>-Element für NameValueSectionHandler und diktarysectionhandler

Löscht alle zuvor definierten Einstellungen in einem Abschnitt.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Syntax

```xml
<clear />
```

## <a name="attributes"></a>Attribute

Keine

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ------------|
| [**\<sectionName>** Gewisses](custom-element-2.md) | Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, die die <xref:System.Configuration.NameValueSectionHandler> -Klasse und die- <xref:System.Configuration.DictionarySectionHandler> Klasse verwenden. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keine

## <a name="remarks"></a>Bemerkungen

Sie können das- **\<clear>** Element verwenden, um alle Einstellungen aus der Anwendung zu entfernen, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdateien definiert wurden.

## <a name="example"></a>Beispiel

In diesem Beispiel werden eine Computer Konfigurationsdatei und eine Anwendungs Konfigurationsdatei definiert. Außerdem wird gezeigt, wie Sie mit dem- **\<clear>** Element in einer Anwendungs Konfigurationsdatei Abschnitte löschen, die zuvor in der Computer Konfigurationsdatei definiert wurden

Der folgende Code der Computer Konfigurationsdatei deklariert den Abschnitt **\<mySection>** :

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

Mit dem folgenden Anwendungs Konfigurationsdatei-Code werden alle Einstellungen aus entfernt **\<mySection>** . Die Anwendung kann keine der im- **\<mySection>** Abschnitt der Computer Konfigurationsdatei deklarierten Einstellungen abrufen.

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
