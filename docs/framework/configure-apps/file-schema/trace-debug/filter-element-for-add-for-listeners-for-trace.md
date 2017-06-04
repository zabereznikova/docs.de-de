---
title: "&lt;filter&gt;-Element f&#252;r &lt;add&gt; f&#252;r &lt;listeners&gt; f&#252;r &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<filter>-Element für <add> für <listeners> für <trace>"
  - "filter-Element für <add> für <listeners> für <trace>"
  - "initializeData-Attribut"
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &lt;filter&gt;-Element f&#252;r &lt;add&gt; f&#252;r &lt;listeners&gt; f&#252;r &lt;trace&gt;
Fügt einem Listener in der `Listeners`\-Auflistung für eine Ablaufverfolgung einen Filter hinzu.  
  
## Syntax  
  
```  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`type`|Erforderliches Attribut.<br /><br /> Gibt den Typ des Filters an, der von der <xref:System.Diagnostics.TraceFilter>\-Klasse erben soll.  Verwenden Sie hierfür entweder den Namespace\-qualifizierten Namen des Typs, der der <xref:System.Type.FullName%2A>\-Eigenschaft des Typs entspricht, oder den vollqualifizierten Typnamen einschließlich der Assemblyinformationen, der der <xref:System.Type.AssemblyQualifiedName%2A>\-Eigenschaft entspricht.  Informationen über vollqualifizierte Typnamen finden Sie unter [Angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Optionales Attribut.<br /><br /> Die für die angegebene Filterklasse an den Konstruktor übergebene Zeichenfolge.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
|`trace`|Enthält Listener, die Verfolgungsmeldungen sammeln, speichern und weiterleiten.|  
|`listeners`|Enthält Listener, die Meldungen sammeln, speichern und weiterleiten.  Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel.|  
|`add`|Fügt der `Listeners`\-Auflistung einen Listener hinzu.|  
  
## Hinweise  
 Das `<filter>`\-Element muss sich in einem `<add>`\-Element für einen Ablaufverfolgungslistener befinden, der den Typ des Listeners angibt, nicht nur den Namen eines in einem [\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md) definierten Listeners.  Wenn der Listener in einem [\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md) definiert ist, muss der Filter für diesen Listener in diesem Element definiert sein.  
  
 Dieses Element kann in der Computerkonfigurationsdatei \(**Machine.config**\) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie dem Listener `console` in der `Listeners`\-Auflistung für die Ablaufverfolgung mithilfe des `<filter>` \-Elements ein Filter hinzugefügt wird. Die Filterereignisebene wird dabei als `Error` angegeben.  
  
```  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.TraceFilter>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)