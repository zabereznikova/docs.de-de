---
title: "&lt;sharedListeners&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<sharedListeners>-Element"
  - "Listener"
  - "Freigegebene Listener"
  - "sharedListeners-Element"
  - "Ablaufverfolgungslistener, <sharedListeners>-Element"
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# &lt;sharedListeners&gt;-Element
Enthält Listener, auf die jedes source\- bzw. trace\-Element verweisen kann.  Diese Listener empfangen standardmäßig keine Ablaufverfolgung und können zur Laufzeit nicht abgerufen werden.  Listener, die als freigegeben gekennzeichnet sind, können anhand des Namens zu Quellen oder Ablaufverfolgungen hinzugefügt werden.  
  
## Syntax  
  
```  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Fügt der `sharedListeners`\-Auflistung einen Listener hinzu.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`Configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET\-Konfigurationsabschnitt an.|  
  
## Hinweise  
 Ein Listener wird beim Hinzufügen zu einer freigegebenen Listener\-Auflistung noch nicht aktiv.  Er muss darüber hinaus einer Ablaufverfolgungsquelle oder einer Ablaufverfolgung hinzugefügt werden, indem er der `Listeners`\-Auflistung des entsprechenden Ablaufverfolgungselements hinzugefügt wird.  Die in .NET Framework enthaltenen Listenerklassen sind von der <xref:System.Diagnostics.TraceListener>\-Klasse abgeleitet.  
  
 Dieses Element kann in der Computerkonfigurationsdatei \(**Machine.config**\) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie der `Listeners`\-Auflistung für die <xref:System.Diagnostics.TraceSource>\-Klasse und die <xref:System.Diagnostics.Trace>\-Klasse mithilfe des `<sharedListeners>`\-Elements der Listener `console` hinzugefügt wird.  Der Ablaufverfolgungslistener für die Konsole gibt Ablaufverfolgungsinformationen durch Aufrufen von <xref:System.Diagnostics.TraceSource> oder <xref:System.Diagnostics.Trace> an die Konsole aus.  
  
```  
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
  
## Siehe auch  
 <xref:System.Diagnostics.TraceListener>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)