---
title: "&lt;filter&gt;-Element f&#252;r &lt;add&gt; f&#252;r &lt;listeners&gt; f&#252;r &lt;source&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#filter"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<filter>-Element für <add> für <listeners> für <source>"
  - "filter-Element für <add> für <listeners> für <source>"
  - "initializeData-Attribut"
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# &lt;filter&gt;-Element f&#252;r &lt;add&gt; f&#252;r &lt;listeners&gt; f&#252;r &lt;source&gt;
Fügt einem Listener in der `Listeners`\-Auflistung für eine Ablaufverfolgungsquelle einen Filter hinzu.  
  
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
|`sources`|Enthält Ablaufverfolgungsquellen, die Ablaufverfolgungsmeldungen initiieren.|  
|`source`|Gibt eine Ablaufverfolgungsquelle an, die Ablaufverfolgungsmeldungen initiiert.|  
|`listeners`|Enthält Listener, die Meldungen sammeln, speichern und weiterleiten.  Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel.|  
|`add`|Fügt der `Listeners`\-Auflistung für eine Ablaufverfolgungsquelle einen Listener hinzu.|  
  
## Hinweise  
 Das `<filter>`\-Element muss sich in einem `<add>`\-Element für einen Ablaufverfolgungsquellenlistener befinden, der den Typ des Listeners angibt, nicht nur den Namen eines in einem [\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md) definierten Listeners.  Wenn der Listener in einem [\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md) definiert ist, muss der Filter für diesen Listener in diesem Element definiert sein.  
  
 Dieses Element kann in der Computerkonfigurationsdatei \(**Machine.config**\) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie dem Listener `console` in der `Listeners`\-Auflistung für die Ablaufverfolgungsquelle `myTraceSource` mithilfe des `<filter>`\-Elements ein Filter hinzugefügt wird. Die Filterereignisebene wird dabei als `Error` angegeben.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"   
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
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.TraceFilter>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)