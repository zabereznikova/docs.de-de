---
title: <system.diagnostics> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 4f831592d7d178276b1625e1ef7d8512085342af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153206"
---
# <a name="systemdiagnostics-element"></a>\<system.diagnostics> Element
Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.  
  
[**\<Konfiguration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.diagnostics>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.diagnostics>
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<>geltend machen](assert-element.md)|Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.|  
|[\<performanceCounters>](performancecounters-element.md)|Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.|  
|[\<sharedListeners>](sharedlisteners-element.md)|Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann. Listener, die als freigegebene Listener identifiziert wurden, können Quellen oder Ablaufverfolgungen nach Namen hinzugefügt werden.|  
|[\<Quellen>](sources-element.md)|Gibt Ablaufverfolgungsquellen an, die Ablaufverfolgungsnachrichten initiieren.|  
|[\<Switches>](switches-element.md)|Enthält Ablaufverfolgungsschalter und die Ebenen, auf denen die Ablaufverfolgungsschalter festgelegt sind.|  
|[\<Spur>](trace-element.md)|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie einen Ablaufverfolgungsschalter und einen Ablaufverfolgungslistener in das ** \<system.diagnostics>-Element** einbetten. Der `General` Ablaufverfolgungsschalter <xref:System.Diagnostics.TraceLevel> wird auf die Ebene eingestellt. Der Ablaufverfolgungslistener `myListener` `MyListener.log` erstellt eine Datei, die aufgerufen wird, und schreibt die Ausgabe in die Datei.  
  
> [!NOTE]
> In .NET Framework 2.0 können Sie Text verwenden, um den Wert eines Schalters anzugeben. Sie können z. `true` B. für eine <xref:System.Diagnostics.BooleanSwitch> angeben oder den Text `Error` verwenden, der einen Enumerationswert darstellt, z. B. für eine <xref:System.Diagnostics.TraceSwitch>. Die Zeile `<add name="myTraceSwitch" value="Error" />` ist gleichbedeutend mit `<add name="myTraceSwitch" value="1" />`.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [Ablaufverfolgungs- und Debugeinstellungsschema](index.md)
