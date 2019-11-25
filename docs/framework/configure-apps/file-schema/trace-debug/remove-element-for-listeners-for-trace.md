---
title: <remove> Element für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: f06973ec30d5061e4a200d6bf7e68adcf6302018
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088838"
---
# <a name="remove-element-for-listeners-for-trace"></a>\<> Element für \<Listener > für \<Ablauf Verfolgung entfernen >
Entfernt einen Listener aus der **listenerauflistung** .  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Ablauf Verfolgungs**](trace-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;[ **&nbsp;&nbsp;\<Listener >\** ](listeners-element-for-trace.md)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<entfernen >**

## <a name="syntax"></a>Syntax  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**name**|Erforderliches Attribut.<br /><br /> Der Name des Listener, der aus der **listenerauflistung** entfernt werden soll.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`listeners`|Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet. Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`trace`|Konfiguriert den ASP.net-Ablauf Verfolgungs Dienst.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Wenn Sie die <xref:System.Diagnostics.DefaultTraceListener> aus der `Listeners` Auflistung entfernen, ändert sich das Verhalten der Methoden <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>und <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>. Wenn Sie eine `Assert`-oder `Fail`-Methode aufrufen, wird normalerweise die Anzeige eines Meldungs Felds angezeigt. das Meldungs Feld wird jedoch nicht angezeigt, wenn die <xref:System.Diagnostics.DefaultTraceListener> nicht in der `Listeners` Auflistung enthalten ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie der Standardablaufverfolgungslistener aus der Auflistung der ablaufverfol  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](index.md)
