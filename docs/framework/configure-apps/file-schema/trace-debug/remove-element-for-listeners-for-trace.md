---
title: "&lt;remove&gt;-Element f&#252;r &lt;listeners&gt; f&#252;r &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<remove>-Element"
  - "remove-Element"
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# &lt;remove&gt;-Element f&#252;r &lt;listeners&gt; f&#252;r &lt;trace&gt;
Entfernt einen Listener aus der **Listeners**\-Auflistung.  
  
## Syntax  
  
```  
  
<remove name="listener name" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|**name**|Erforderliches Attribut.<br /><br /> Der Name des Listeners, der aus der **Listeners**\-Auflistung entfernt werden soll.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`listeners`|Gibt einen Listener an, der Meldungen sammelt, speichert und weiterleitet.  Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel.|  
|`system.diagnostics`|Gibt die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
|`trace`|Konfiguriert den ASP.NET\-Ablaufverfolgungsdienst.|  
  
## Hinweise  
  
> [!NOTE]
>  Das Entfernen von <xref:System.Diagnostics.DefaultTraceListener> aus der `Listeners`\-Auflistung ändert das Verhalten folgender Methoden: <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> und <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName>.  Das Aufrufen einer `Assert`\-Methode oder einer `Fail`\-Methode führt normalerweise zur Anzeige einer Meldung. Die Meldung wird jedoch nicht angezeigt, wenn <xref:System.Diagnostics.DefaultTraceListener> sich nicht in der `Listeners`\-Auflistung befindet.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie der standardmäßige Ablaufverfolgungslistener aus der Auflistung der Ablaufverfolgungslistener entfernt wird.  
  
```  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.DefaultTraceListener>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)