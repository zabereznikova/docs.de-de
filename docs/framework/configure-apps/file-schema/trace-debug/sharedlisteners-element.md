---
title: <sharedListeners>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: 69f15cc9583b397017ac30a0c567914495867c18
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153320"
---
# <a name="sharedlisteners-element"></a>\<sharedListeners>-Element
Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.  Diese Listener empfangen standardmäßig keine Ablauf Verfolgungen, und es ist nicht möglich, diese Listener zur Laufzeit abzurufen. Listener, die als freigegebene Listener identifiziert werden, können Quellen oder Ablauf Verfolgungen anhand des Namens hinzugefügt werden.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|`Configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|  
  
## <a name="remarks"></a>Bemerkungen  
 Durch das Hinzufügen eines Listener zur Auflistung der freigegebenen Listener wird er nicht zu einem aktiven Listener. Es muss dennoch einer Ablauf Verfolgungs Quelle oder einer Ablauf Verfolgung hinzugefügt werden, indem es der-Auflistung `Listeners` für dieses Trace-Element hinzugefügt wird. Die Listenerklassen in der .NET Framework von der- <xref:System.Diagnostics.TraceListener> Klasse abgeleitet.  
  
 Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das `<sharedListeners>` -Element verwendet wird, um den Listener der `console` `Listeners` -Auflistung für die <xref:System.Diagnostics.TraceSource> -Klasse und die- <xref:System.Diagnostics.Trace> Klasse hinzuzufügen. Der Ablaufverfolgungslistener der Konsole schreibt Ablauf Verfolgungs Informationen über Aufrufe von oder in die Konsole <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace> .  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Diagnostics.TraceListener>
- [Schema für Ablaufverfolgungs- und Debugeinstellungen](index.md)
- [Ablaufverfolgungslistener](../../../debug-trace-profile/trace-listeners.md)
