---
title: "&lt;filter&gt;-Element f&#252;r &lt;add&gt; f&#252;r &lt;sharedListeners&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<filter>-Element für <add> für <sharedListeners>"
  - "filter-Element für <add> für <sharedListeners>"
  - "Filter, Ablaufverfolgungslistener"
  - "initializeData-Attribut"
  - "Ablaufverfolgungslistener, Filter"
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# &lt;filter&gt;-Element f&#252;r &lt;add&gt; f&#252;r &lt;sharedListeners&gt;
Fügt einem Listener in der `sharedListeners`\-Auflistung einen Filter hinzu.  
  
## Syntax  
  
```  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|**type**|Erforderliches Attribut.<br /><br /> Gibt den Typ des Filters an.  Sie können entweder nur den vollständigen Namen des Typs \(im Format der <xref:System.Type.FullName%2A?displayProperty=fullName>\-Eigenschaft\) oder den vollqualifizierten Typnamen einschließlich der Assemblyinformationen \(im Format der <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName>\-Eigenschaft\) verwenden.  Informationen über das Erstellen eines vollqualifizierten Typnamens finden Sie unter [Angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Optionales Attribut.<br /><br /> Die für die angegebene Klasse an den Konstruktor übergebene Zeichenfolge.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
|`sharedListeners`|Eine Auflistung von Listenern, auf die jedes source\-Element bzw. trace\-Element verweisen kann.|  
|`add`|Fügt der **sharedListeners**\-Auflistung einen Listener hinzu.|  
  
## Hinweise  
 Wenn ein Listener in einem `<add>`\-Element des `<sharedListeners>`\-Elements definiert ist, muss der Filter für diesen Listener in einem `<filter>`\-Element definiert werden, der ein untergeordnetes Element des `<add>`\-Elements ist.  
  
 Dieses Element kann in der Computerkonfigurationsdatei \(**Machine.config**\) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie dem Ablaufverfolgungslistener `console` in der `sharedListeners`\-Auflistung mithilfe des `<filter>`\-Elements ein Filter hinzugefügt wird.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Diagnostics.TraceFilter>   
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.TraceSource>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)