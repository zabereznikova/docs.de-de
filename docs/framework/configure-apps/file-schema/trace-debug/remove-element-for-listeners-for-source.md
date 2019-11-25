---
title: <remove> Element für <listeners> für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 75db45d4e868ce88e030ec6a43c8bdaf788a1102
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088853"
---
# <a name="remove-element-for-listeners-for-source"></a>\<> Element für \<Listener > für \<Quelle entfernen >
Entfernt einen Listener aus der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Quellen**](sources-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**Quelle**](source-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](listeners-element-for-source.md) Listener >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<entfernen >**

## <a name="syntax"></a>Syntax  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`name`|Erforderliches Attribut.<br /><br /> Der Name des Listener, der aus der `Listeners` Auflistung entfernt werden soll.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sources`|Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.|  
|`source`|Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.|  
|`listeners`|Gibt Listener an, die Nachrichten erfassen, speichern und weiterleiten.|  
  
## <a name="remarks"></a>Hinweise  
 Das `<remove>`-Element entfernt einen angegebenen Listener aus der `Listeners` Auflistung für eine Ablauf Verfolgungs Quelle.  
  
 Sie können ein Element aus der `Listeners` Auflistung für eine Ablauf Verfolgungs Quelle Programm gesteuert entfernen, indem Sie die <xref:System.Diagnostics.TraceListenerCollection.Remove%2A>-Methode für die <xref:System.Diagnostics.TraceSource.Listeners%2A>-Eigenschaft der <xref:System.Diagnostics.TraceSource> Instanz aufrufen.  
  
 Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das `<remove>`-Element verwendet wird, bevor das `<add>`-Element verwendet wird, um der `Listeners` Auflistung für die Ablauf Verfolgungs Quelle `TraceSourceApp`den Listener`console` hinzuzufügen.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](index.md)
- [\<clear>](clear-element-for-listeners-for-source.md)
- [Trace Listeners (Ablaufverfolgungslistener)](../../../debug-trace-profile/trace-listeners.md)
