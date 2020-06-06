---
title: <clear>-Element für <listeners> für<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153541"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<clear>-Element für \<listeners> für\<trace>
Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Syntax  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`trace`|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
|`listeners`|Enthält Listener, die Nachrichten erfassen, speichern und weiterleiten. Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das- `<clear>` Element entfernt alle Listener aus der-Auflistung für die Ablauf `Listeners` Verfolgung. Sie können das- `<clear>` Element verwenden, bevor Sie das- `<add>` Element verwenden, um sicher zu sein, dass keine anderen aktiven Listener in der Auflistung vorhanden sind.  
  
 Sie können die Auflistung Programm gesteuert löschen, `Listeners` indem Sie die- <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> Methode für die- <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> Eigenschaft ( `System.Diagnostics.Trace.Listeners.Clear()` ) aufrufen.  
  
 Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
> [!NOTE]
> Das- `<clear>` Element entfernt das <xref:System.Diagnostics.DefaultTraceListener> -Element aus der-Auflistung `Listeners` und ändert das Verhalten der <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> Methoden,, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> und <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> . Wenn eine-Methode oder eine-Methode aufgerufen wird, wird `Assert` `Fail` normalerweise ein Meldungs Feld angezeigt. Das Meldungs Feld wird jedoch nicht angezeigt, wenn <xref:System.Diagnostics.DefaultTraceListener> sich nicht in der Auflistung befindet `Listeners` .  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie das-Element verwendet wird, bevor das-Element verwendet wird, um der-Auflistung für die Ablauf `<clear>` `<add>` Verfolgung den Listener hinzuzufügen `console` `Listeners` .  
  
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
- [Schema für Ablaufverfolgungs- und Debugeinstellungen](index.md)
- [\<remove>](remove-element-for-listeners-for-trace.md)
- [Ablaufverfolgungslistener](../../../debug-trace-profile/trace-listeners.md)
