---
title: '&lt;System.Diagnostics&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 54c20e56fa1729cb534821e263e316c26e01cde6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687315"
---
# <a name="ltsystemdiagnosticsgt-element"></a>&lt;System.Diagnostics&gt; Element
Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.  
  
 \<configuration>  
\<system.diagnostics>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<assert>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.|  
|[\<performanceCounters>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.|  
|[\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann. Listener, die als freigegebene Listener können anhand des Namens mit Quellen oder ablaufverfolgungen hinzugefügt werden.|  
|[\<sources>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Gibt die Ablaufverfolgungsquellen, die Ablaufverfolgungsmeldungen initiieren.|  
|[\<switches>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Enthält Ablaufverfolgungsschalter und die Ebenen, wo die Ablaufverfolgungsschalter festgelegt werden.|  
|[\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie einen Ablaufverfolgungsschalter sowie eines Ablaufverfolgungslisteners in Einbetten der  **\<system.diagnostics >** Element. Die `General` Ablaufverfolgungsschalter festgelegt ist, um die <xref:System.Diagnostics.TraceLevel> Ebene. Der Ablaufverfolgungslistener `myListener` erstellt eine Datei namens `MyListener.log` und schreibt die Ausgabe in der Datei.  
  
> [!NOTE]
>  In .NET Framework 2.0 können Sie Text verwenden, um den Wert eines Schalters anzugeben. Sie können z. B. angeben `true` für eine <xref:System.Diagnostics.BooleanSwitch> oder verwenden Sie den Text, der einem Enumerationswert entspricht z. B. `Error` für eine <xref:System.Diagnostics.TraceSwitch>. Die Zeile `<add name="myTraceSwitch" value="Error" />` ist gleichbedeutend mit `<add name="myTraceSwitch" value="1" />`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
