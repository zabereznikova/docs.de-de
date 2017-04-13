---
title: "&lt;sources&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#sources"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<sources>-Element"
  - "sources-Element"
  - "Ablaufverfolgungsquellen"
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# &lt;sources&gt;-Element
Gibt Ablaufverfolgungsquellen an, die Ablaufverfolgungsmeldungen initiieren.  
  
## Syntax  
  
```  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|Erforderliches Element.<br /><br /> Gibt eine Ablaufverfolgungsquelle an, die Ablaufverfolgungsmeldungen initiiert.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
  
## Hinweise  
 Dieses Element kann in der Computerkonfigurationsdatei \(**Machine.config**\) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie die Ablaufverfolgungsquelle `mySource` mithilfe des `<sources>` \-Elements hinzugefügt wird und wie die Ebene für den Quellenschalter mit der Bezeichnung `sourceSwitch` festgelegt wird.  Außerdem wird ein Ablaufverfolgungslistener für eine Konsole hinzugefügt, der Ablaufverfolgungsinformationen an die Konsole ausgibt.  
  
```  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"   
            switchType="System.Diagnostics.SourceSwitch"  >  
            <listeners>  
               <add name="console"   
                  type="System.Diagnostics.ConsoleTraceListener" >  
                  <filter type="System.Diagnostics.EventTypeFilter"   
                     initializeData="Error" />  
               </add>  
               <remove name="Default" />  
            </listeners>  
         </source>  
      </sources>  
      <switches>  
         <add name="sourceSwitch" value="Warning" />  
      </switches>    
   </system.diagnostics>   
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.DefaultTraceListener>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.ConsoleTraceListener>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 <xref:System.Diagnostics.XmlWriterTraceListener>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)