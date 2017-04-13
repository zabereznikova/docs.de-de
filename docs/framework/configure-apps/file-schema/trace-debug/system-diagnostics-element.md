---
title: "&lt;system.diagnostics&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<system.diagnostics>-Element"
  - "system.diagnostics-Element"
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# &lt;system.diagnostics&gt;-Element
Gibt die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.  
  
## Syntax  
  
```  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<assert\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Legt fest, ob ein Meldungsfeld angezeigt wird, wenn die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>\-Methode aufgerufen wird; gibt darüber hinaus den Namen der Datei an, in die Meldungen geschrieben werden.|  
|[\<performanceCounters\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren gemeinsam genutzt wird.|  
|[\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Enthält Listener, auf die jedes source\- bzw. trace\-Element verweisen kann.  Listener, die als freigegeben gekennzeichnet sind, können anhand des Namens zu Quellen oder Ablaufverfolgungen hinzugefügt werden.|  
|[\<Quellen\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Gibt Ablaufverfolgungsquellen an, die Ablaufverfolgungsmeldungen initiieren.|  
|[\<Schalter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Enthält Ablaufverfolgungsschalter und die Ebenen, auf die die Ablaufverfolgungsschalter festgelegt werden.|  
|[\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Enthält Listener, die Verfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie einen Ablaufverfolgungsschalter und einen Ablaufverfolgungslistener im **\<system.diagnostics\>**\-Element eingebettet werden.  Der Ablaufverfolgungsschalter `General` wird auf die Ebene [TraceLevel.Error](frlrfSystemDiagnosticsTraceLevelClassTopic) festgelegt.  Der Ablaufverfolgungslistener `myListener` erstellt eine Datei mit der Bezeichnung `MyListener.log` und schreibt die Ausgabe in die Datei.  
  
> [!NOTE]
>  In .NET Framework Version 2.0 können Sie Text verwenden, um den Wert für einen Schalter anzugeben.  Sie können z. B. `true` für einen <xref:System.Diagnostics.BooleanSwitch> angeben oder den Text für einen Enumerationswert, z. B. `Error`, für einen <xref:System.Diagnostics.TraceSwitch> verwenden.  Die Zeile `<add name="myTraceSwitch" value="Error" />` ist äquivalent zu `<add name="myTraceSwitch" value="1" />`.  
  
```  
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
  
## Siehe auch  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.Debug>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)