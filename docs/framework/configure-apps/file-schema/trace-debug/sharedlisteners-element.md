---
title: '&lt;SharedListeners&gt; Element'
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
ms.openlocfilehash: 7eaeffb365dd2c9999d4faa6b28c6d50e8cd6a6e
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2019
ms.locfileid: "55084327"
---
# <a name="ltsharedlistenersgt-element"></a>&lt;SharedListeners&gt; Element
Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.  Diese Listener empfangen keine ablaufverfolgungen in der Standardeinstellung, und es ist nicht möglich, diese Listener zur Laufzeit abrufen. Listener, die als freigegebene Listener können anhand des Namens mit Quellen oder ablaufverfolgungen hinzugefügt werden.  
  
 \<configuration>  
\<system.diagnostics>  
\<sharedListeners>  
  
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
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`Configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|  
  
## <a name="remarks"></a>Hinweise  
 Hinzufügen eines Listeners zur gemeinsam genutzten Auflistung ist es keinen aktiven Listener einzurichten. Es muss immer noch eine Ablaufverfolgungsquelle zu einer Ablaufverfolgung hinzugefügt werden, fügen es zu den `Listeners` Auflistung für das Trace-Element. Die Listenerklassen in .NET Framework leiten sich von der <xref:System.Diagnostics.TraceListener> Klasse.  
  
 Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie mit der `<sharedListeners>` Element, um den Listener hinzuzufügen `console` auf die `Listeners` Auflistung für beide die <xref:System.Diagnostics.TraceSource> und <xref:System.Diagnostics.Trace> Klassen. Die Konsolen-Ablaufverfolgungslistener Schreibt Ablaufverfolgungsinformationen in die Konsole durch Aufrufen von <xref:System.Diagnostics.TraceSource> oder <xref:System.Diagnostics.Trace>.  
  
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
</configuration></system.diagnostics>   
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Diagnostics.TraceListener>
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [Trace Listeners (Ablaufverfolgungslistener)](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
