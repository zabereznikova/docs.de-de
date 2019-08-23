---
title: <clear>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: c06fca8b83638fb47bedb21863cb9b200cd211f3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927731"
---
# <a name="clear-element-for-configsections"></a>\<Löschen Sie > Element \<für configabschnitts >

Löscht alle zuvor definierten Abschnitte und Abschnitts Gruppen.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<configSections>** ](configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<Löschen >**

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

None

## <a name="remarks"></a>Hinweise

Mit dem  **\<Clear >** -Element werden alle Abschnitte und Abschnitts Gruppen aus der Anwendung entfernt, die zuvor in der aktuellen Konfigurationsdatei oder auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.

## <a name="example"></a>Beispiel

In diesem Beispiel werden eine Computer Konfigurationsdatei und eine Anwendungs Konfigurationsdatei definiert, und es wird gezeigt, wie das  **\<Clear >** -Element in einer Anwendungs Konfigurationsdatei verwendet wird, um die zuvor in der Computerkonfiguration definierten Abschnitte Datei.

Der folgende Computer Konfigurationsdatei-Code deklariert zwei  **\<Abschnitte: Sample section >** und  **\<anotherSampleSection >** , die vor der Anwendungs Konfigurationsdatei gelesen werden:

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

Der folgende Anwendungs Konfigurationsdatei-Code löscht alle zuvor deklarierten Abschnitte. Die Anwendung kann in keinem der Abschnitte, die in der Computer Konfigurationsdatei deklariert wurden, Einstellungen verwenden oder abrufen. Es können jedoch Einstellungen aus  **\<der anotherSection->** verwendet werden, da es hinter das  **\<Clear >** -Element liegt.

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
