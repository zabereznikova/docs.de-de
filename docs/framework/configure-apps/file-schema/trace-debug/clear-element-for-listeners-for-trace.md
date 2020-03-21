---
title: <clear>Element <listeners> für für<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153541"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<klares> \<Element für \<Hörer> für Trace->
Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<Spur>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Hörer>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<klare>**

## <a name="syntax"></a>Syntax  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`trace`|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
|`listeners`|Enthält Listener, die Nachrichten sammeln, speichern und weiterleiten. Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel weiter.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das `<clear>` Element entfernt alle `Listeners` Listener aus der Auflistung für die Ablaufverfolgung. Sie können `<clear>` das Element `<add>` verwenden, bevor Sie das Element verwenden, um sicher zu sein, dass sich keine anderen aktiven Listener in der Auflistung befinden.  
  
 Sie können `Listeners` die Auflistung programmgesteuert <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> löschen, <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> indem`System.Diagnostics.Trace.Listeners.Clear()`Sie die Methode für die Eigenschaft ( ) aufrufen.  
  
 Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
> [!NOTE]
> Das `<clear>` Element entfernt <xref:System.Diagnostics.DefaultTraceListener> die `Listeners` aus der Auflistung, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>wodurch <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>das <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> Verhalten der , <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, und Methoden geändert wird. Das `Assert` Aufrufen `Fail` einer oder Methode führt normalerweise zur Anzeige eines Meldungsfelds. Das Meldungsfeld wird jedoch <xref:System.Diagnostics.DefaultTraceListener> nicht angezeigt, `Listeners` wenn sich der nicht in der Auflistung befindet.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, `<clear>` wie sie `<add>` das Element verwenden, bevor Sie das Element verwenden, um den Listener `console` zur `Listeners` Auflistung für die Ablaufverfolgung hinzuzufügen.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [Ablaufverfolgungs- und Debugeinstellungsschema](index.md)
- [\<entfernen sie>](remove-element-for-listeners-for-trace.md)
- [Ablaufverfolgungslistener](../../../debug-trace-profile/trace-listeners.md)
