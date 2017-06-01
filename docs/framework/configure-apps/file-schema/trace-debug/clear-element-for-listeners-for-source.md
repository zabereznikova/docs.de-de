---
title: "&lt;clear&gt;-Element f&#252;r &lt;listeners&gt; f&#252;r &lt;source&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<clear>-Element für <listeners> für <source>"
  - "clear-Element für <listeners> für <source>"
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# &lt;clear&gt;-Element f&#252;r &lt;listeners&gt; f&#252;r &lt;source&gt;
Löscht die `Listeners`\-Auflistung für eine Ablaufverfolgungsquelle.  
  
## Syntax  
  
```  
<clear/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
|`sources`|Enthält Ablaufverfolgungsquellen, die Ablaufverfolgungsmeldungen initiieren.|  
|`source`|Gibt eine Ablaufverfolgungsquelle an, die Ablaufverfolgungsmeldungen initiiert.|  
|`listeners`|Gibt Listener an, die Meldungen sammeln, speichern und weiterleiten.|  
  
## Hinweise  
 Das `<clear>`\-Element entfernt alle Listener, einschließlich des <xref:System.Diagnostics.DefaultTraceListener>, aus der `Listeners`\-Auflistung für eine Ablaufverfolgungsquelle.  Verwenden Sie das `<clear>`\-Element vor der Verwendung des `<add>`\-Elements, um sicherzugehen, dass sich keine weiteren aktiven Listener in der Auflistung befinden.  
  
## Konfigurationsdatei  
 Dieses Element kann in der Computerkonfigurationsdatei \(**Machine.config**\) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie das `<clear>`\-Element verwendet wird, bevor der `Listeners`\-Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp` mithilfe der `<add>`\-Elemente die Listener `console` und `textListener` hinzugefügt werden.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## Siehe auch  
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.TraceListener>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)