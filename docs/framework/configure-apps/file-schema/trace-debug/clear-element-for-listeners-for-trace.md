---
title: "&lt;clear&gt;-Element f&#252;r &lt;listeners&gt; f&#252;r &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<clear>-Element für <listeners> für <trace>"
  - "clear-Element für <listeners> für <trace>"
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;clear&gt;-Element f&#252;r &lt;listeners&gt; f&#252;r &lt;trace&gt;
Löscht die `Listeners`\-Auflistung für die Ablaufverfolgung.  
  
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
|`trace`|Enthält Listener, die Verfolgungsmeldungen sammeln, speichern und weiterleiten.|  
|`listeners`|Enthält Listener, die Meldungen sammeln, speichern und weiterleiten.  Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel.|  
  
## Hinweise  
 Das `<clear>`\-Element entfernt alle Listener aus der `Listeners`\-Auflistung für die Ablaufverfolgung.  Verwenden Sie das `<clear>`\-Element vor der Verwendung des `<add>`\-Elements, um sicherzugehen, dass sich keine weiteren aktiven Listener in der Auflistung befinden.  
  
 Sie können die `Listeners`\-Auflistung programmgesteuert löschen, indem Sie die <xref:System.Diagnostics.TraceListenerCollection.Clear%2A>\-Methode für die <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=fullName>\-Eigenschaft \(`System.Diagnostics.Trace.Listeners.Clear()`\) aufrufen.  
  
 Dieses Element kann in der Computerkonfigurationsdatei \(**Machine.config**\) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
> [!NOTE]
>  Das `<clear>`\-Element entfernt <xref:System.Diagnostics.DefaultTraceListener> aus der `Listeners`\-Auflistung und verändert damit das Verhalten folgender Methoden: <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> und <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName>.  Das Aufrufen der `Assert`\-Methode oder der `Fail`\-Methode führt normalerweise zur Anzeige eines Meldungsfelds.  Aber das Meldungsfeld wird nicht angezeigt, wenn <xref:System.Diagnostics.DefaultTraceListener> nicht in der `Listeners`\-Auflistung enthalten ist.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie das `<clear>`\-Element verwendet wird, bevor der `Listeners`\-Auflistung für die Ablaufverfolgung mithilfe des `<add>`\-Elements der Listener `console` hinzugefügt wird.  
  
```  
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
  
## Siehe auch  
 <xref:System.Diagnostics.Trace.Listeners%2A>   
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.Debug>   
 <xref:System.Diagnostics.TraceSource>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)