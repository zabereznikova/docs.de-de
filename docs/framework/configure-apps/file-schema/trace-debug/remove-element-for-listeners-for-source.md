---
title: "&lt;remove&gt;-Element f&#252;r &lt;listeners&gt; f&#252;r &lt;source&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<remove>-Element für <listeners> für <source>"
  - "remove-Element für <listeners> für <source>"
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# &lt;remove&gt;-Element f&#252;r &lt;listeners&gt; f&#252;r &lt;source&gt;
Entfernt einen Listener aus der `Listeners`\-Auflistung für eine Ablaufverfolgungsquelle.  
  
## Syntax  
  
```  
<remove name="listenerName" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`name`|Erforderliches Attribut.<br /><br /> Der Name des Listeners, der aus der `Listeners`\-Auflistung entfernt werden soll.|  
  
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
 Das `<remove>`\-Element entfernt einen angegebenen Listener aus der `Listeners`\-Auflistung für eine Ablaufverfolgungsquelle.  
  
 Ein Element kann programmgesteuert aus der `Listeners`\-Auflistung für eine Ablaufverfolgungsquelle entfernt werden, indem die <xref:System.Diagnostics.TraceListenerCollection.Remove%2A>\-Methode für die <xref:System.Diagnostics.TraceSource.Listeners%2A>\-Eigenschaft der <xref:System.Diagnostics.TraceSource>\-Instanz aufgerufen wird.  
  
 Dieses Element kann in der Computerkonfigurationsdatei \(**Machine.config**\) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie das `<remove>`\-Element verwendet wird, bevor der `Listeners`\-Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp` der Listener `console` mithilfe des `<add>`\-Elements hinzugefügt wird.  
  
```  
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
  
## Siehe auch  
 <xref:System.Diagnostics.TraceSource.Listeners%2A>   
 <xref:System.Diagnostics.TraceSource>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)