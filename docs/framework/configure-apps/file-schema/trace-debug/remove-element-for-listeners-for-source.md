---
title: <remove>-Element für <listeners> für<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 657e6db2af9b99b3bbf03afc6aab02c58a830f2d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153334"
---
# <a name="remove-element-for-listeners-for-source"></a>\<remove>-Element für \<listeners> für\<source>
Entfernt einen Listener aus der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a>Syntax  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`name`|Erforderliches Attribut.<br /><br /> Der Name des Listener, der aus der Auflistung entfernt werden soll `Listeners` .|  
  
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
  
## <a name="remarks"></a>Bemerkungen  
 Das- `<remove>` Element entfernt einen angegebenen Listener aus der-Auflistung `Listeners` für eine Ablauf Verfolgungs Quelle.  
  
 Sie können ein Element aus der-Auflistung `Listeners` für eine Ablauf Verfolgungs Quelle Programm gesteuert entfernen, indem Sie die- <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> Methode für die- <xref:System.Diagnostics.TraceSource.Listeners%2A> Eigenschaft der-Instanz aufrufen <xref:System.Diagnostics.TraceSource> .  
  
 Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das-Element verwendet wird, bevor das-Element verwendet wird, um der-Auflistung `<remove>` `<add>` `console` `Listeners` für die Ablauf Verfolgungs Quelle den Listener hinzuzufügen `TraceSourceApp` .  
  
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
- [Schema für Ablaufverfolgungs- und Debugeinstellungen](index.md)
- [\<clear>](clear-element-for-listeners-for-source.md)
- [Ablaufverfolgungslistener](../../../debug-trace-profile/trace-listeners.md)
