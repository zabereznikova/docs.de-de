---
title: "&lt;switches&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#switches"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<switches>-Element"
  - "switches-Element"
  - "Ablaufverfolgungsschalter, <switches>-Element"
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &lt;switches&gt;-Element
Enthält Ablaufverfolgungsschalter und die Ebene, auf die die Ablaufverfolgungsschalter festgelegt werden.  
  
## Syntax  
  
```  
  
      <switches>   
</switches>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|Gibt die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`System.diagnostics`|Gibt die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
  
## Hinweise  
 Die Ebene eines Ablaufverfolgungsschalters können Sie ändern, indem Sie ihn in einer Konfigurationsdatei ablegen.  Wenn es sich bei dem Schalter um einen <xref:System.Diagnostics.BooleanSwitch> handelt, können Sie ihn ein\- und ausschalten.  Wenn es sich um einen <xref:System.Diagnostics.TraceSwitch> handelt, so können Sie ihm unterschiedliche Ebenen zuweisen, um die Art der von der Anwendung ausgegebenen Ablaufverfolgungs\- oder Debugmeldungen anzugeben.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das Element **\<switch\>** verwendet, um den `General` Ablaufverfolgungsschalter auf der [TraceLevel.Error](frlrfSystemDiagnosticsTraceLevelClassTopic) Ebene zu stellen, und den Ablaufverfolgungsschalter `Data` booleschen Werts zu aktivieren.  
  
```  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Diagnostics.Switch>   
 <xref:System.Diagnostics.TraceSwitch>   
 <xref:System.Diagnostics.BooleanSwitch>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)