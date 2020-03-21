---
title: <remove>Element <listeners> für für<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 657e6db2af9b99b3bbf03afc6aab02c58a830f2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153334"
---
# <a name="remove-element-for-listeners-for-source"></a>\<Entfernen> \<Elements für \<Listener, die für>>
Entfernt einen Listener aus der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<Quellen>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Quelle>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Hörer>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entfernen sie>**

## <a name="syntax"></a>Syntax  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`name`|Erforderliches Attribut.<br /><br /> Der Name des Listeners, `Listeners` der aus der Auflistung entfernt werden soll.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sources`|Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.|  
|`source`|Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.|  
|`listeners`|Gibt Listener an, die Nachrichten sammeln, speichern und weiterleiten.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das `<remove>` Element entfernt einen angegebenen `Listeners` Listener aus der Auflistung für eine Ablaufverfolgungsquelle.  
  
 Sie können ein Element `Listeners` aus der Auflistung für eine <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> Ablaufverfolgungsquelle programmgesteuert entfernen, indem Sie die Methode für die <xref:System.Diagnostics.TraceSource.Listeners%2A> Eigenschaft der <xref:System.Diagnostics.TraceSource> Instanz aufrufen.  
  
 Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, `<remove>` wie Sie `<add>` das Element verwenden, `Listeners` bevor Sie das `TraceSourceApp`Element verwenden, um den Listener `console` zur Auflistung für die Ablaufverfolgungsquelle hinzuzufügen.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [Ablaufverfolgungs- und Debugeinstellungsschema](index.md)
- [\<klare>](clear-element-for-listeners-for-source.md)
- [Ablaufverfolgungslistener](../../../debug-trace-profile/trace-listeners.md)
