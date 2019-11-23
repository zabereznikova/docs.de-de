---
title: <clear>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a45572d0dcb2737558e11f5c38ac2ccc338c754a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119082"
---
# <a name="clear-element-for-configsections"></a>\<> Element für \<configabschnitts löschen >

Löscht alle zuvor definierten Abschnitte und Abschnitts Gruppen.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<configSections>** ](configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<löschen >**

## <a name="syntax"></a>Syntax

```xml
<clear/>
```

## <a name="attribute"></a>Attribut

|           | Beschreibung |
| --------- | ----------- |
| **name**  | Erforderliches Attribut.<br><br>Gibt den Namen des Abschnitts oder der Abschnitts Gruppe an, der entfernt werden soll. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [ **\<configSections>** Element](configsections-element-for-configuration.md) | Enthält Konfigurations Abschnitts-und Namespace Deklarationen. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keine

## <a name="remarks"></a>Hinweise

Das **\<Clear >** -Element entfernt alle Abschnitte und Abschnitts Gruppen aus der Anwendung, die zuvor in der aktuellen Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationsdatei Hierarchie definiert wurden.

## <a name="example"></a>Beispiel

In diesem Beispiel werden eine Computer Konfigurationsdatei und eine Anwendungs Konfigurationsdatei definiert. Außerdem wird gezeigt, wie das **\<Clear >** -Element in einer Anwendungs Konfigurationsdatei verwendet wird, um die zuvor in der Computer Konfigurationsdatei definierten Abschnitte zu löschen

Der folgende Computer Konfigurationsdatei-Code deklariert zwei Abschnitte, **\<sampleSection >** und **\<anotherSampleSection->** , die vor der Anwendungs Konfigurationsdatei gelesen werden:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

Der folgende Anwendungs Konfigurationsdatei-Code löscht alle zuvor deklarierten Abschnitte. Die Anwendung kann in keinem der Abschnitte, die in der Computer Konfigurationsdatei deklariert wurden, Einstellungen verwenden oder abrufen. Es können jedoch Einstellungen aus **\<anotherSection->** verwendet werden, da es nach dem **\<Clear >** -Element liegt.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
