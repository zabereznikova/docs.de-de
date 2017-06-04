---
title: "&lt;add&gt;-Element f&#252;r &lt;switches&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add>-Element für <switches>"
  - "add-Element für <switches>"
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &lt;add&gt;-Element f&#252;r &lt;switches&gt;
Gibt die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.  
  
## Syntax  
  
```  
<add name="switch name"  
     value="value"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|**name**|Erforderliches Attribut.<br /><br /> Gibt den Namen des Schalters an.  Der Wert dieses Attributs entspricht dem Parameter *displayName*, der an den Schalterkonstruktor übergeben wird.|  
|**Wert**|Erforderliches Attribut.<br /><br /> Gibt die Ebene des Schalters an.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`switches`|Enthält Ablaufverfolgungsschalter und die Ebene, auf die die Ablaufverfolgungsschalter festgelegt werden.|  
|`system.diagnostics`|Gibt die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
  
## Hinweise  
 Die Ebene eines Ablaufverfolgungsschalters können Sie ändern, indem Sie ihn in einer Konfigurationsdatei ablegen.  Wenn es sich bei dem Schalter um einen <xref:System.Diagnostics.BooleanSwitch> handelt, können Sie ihn ein\- und ausschalten.  Wenn es sich um einen <xref:System.Diagnostics.TraceSwitch> handelt, so können Sie ihm unterschiedliche Ebenen zuweisen, um die Art der von der Anwendung ausgegebenen Ablaufverfolgungs\- oder Debugmeldungen anzugeben.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie das Element **\<Hinzufügen\>** verwendet, um den `General` Ablaufverfolgungsschalter auf Designebene [TraceLevel.Error](frlrfSystemDiagnosticsTraceLevelClassTopic) zu stellen und aktiviert den Ablaufverfolgungsschalter `Data` booleschen Werts.  
  
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