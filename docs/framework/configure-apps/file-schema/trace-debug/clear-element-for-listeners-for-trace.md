---
title: <clear> Element für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 049b8e7ed17633c0f34b062915afaf719927dad6
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088915"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<> Element für \<Listener > für \<Ablauf Verfolgung löschen >
Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Ablauf Verfolgungs**](trace-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;[ **&nbsp;&nbsp;\<Listener >\** ](listeners-element-for-trace.md)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Löschen >**

## <a name="syntax"></a>Syntax  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`trace`|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
|`listeners`|Enthält Listener, die Nachrichten erfassen, speichern und weiterleiten. Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.|  
  
## <a name="remarks"></a>Hinweise  
 Das `<clear>`-Element entfernt alle Listener aus der `Listeners` Auflistung für die Ablauf Verfolgung. Sie können das `<clear>`-Element verwenden, bevor Sie das `<add>`-Element verwenden, um sicher zu sein, dass keine anderen aktiven Listener in der Auflistung vorhanden sind.  
  
 Sie können die `Listeners` Auflistung Programm gesteuert löschen, indem Sie die <xref:System.Diagnostics.TraceListenerCollection.Clear%2A>-Methode für die <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType>-Eigenschaft (`System.Diagnostics.Trace.Listeners.Clear()`) aufrufen.  
  
 Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
> [!NOTE]
> Das `<clear>`-Element entfernt die <xref:System.Diagnostics.DefaultTraceListener> aus der `Listeners`-Auflistung und ändert das Verhalten der Methoden <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>und <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>. Wenn Sie eine `Assert` oder `Fail` Methode aufrufen, wird normalerweise eine Meldung angezeigt. Das Meldungs Feld wird jedoch nicht angezeigt, wenn die <xref:System.Diagnostics.DefaultTraceListener> nicht in der `Listeners` Auflistung aufgeführt ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das `<clear>`-Element verwendet wird, bevor das `<add>`-Element verwendet wird, um der `Listeners` Auflistung für die Ablauf Verfolgung den Listener `console` hinzuzufügen.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](index.md)
- [\<remove>](remove-element-for-listeners-for-trace.md)
- [Trace Listeners (Ablaufverfolgungslistener)](../../../debug-trace-profile/trace-listeners.md)
