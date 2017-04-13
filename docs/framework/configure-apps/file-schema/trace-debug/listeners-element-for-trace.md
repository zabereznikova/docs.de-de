---
title: "&lt;listeners&gt;-Element f&#252;r &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<listeners>-Element"
  - "listeners-Element"
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# &lt;listeners&gt;-Element f&#252;r &lt;trace&gt;
Gibt einen Listener an, der Meldungen sammelt, speichert und weiterleitet.  Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel.  
  
## Syntax  
  
```  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Fügt der `Listeners`\-Auflistung einen Listener hinzu.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|Löscht die `Listeners`\-Auflistung für die Ablaufverfolgung.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|Entfernt einen Listener aus der `Listeners`\-Auflistung.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET\-Konfigurationsabschnitt an.|  
|`trace`|Enthält Listener, die Verfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
## Hinweise  
 Die <xref:System.Diagnostics.Debug>\- Klasse und die <xref:System.Diagnostics.Trace>\-Klasse verwenden die gleiche **Listeners**\-Auflistung.  Wenn Sie der Auflistung in einer dieser Klassen ein Listener\-Objekt hinzufügen, verwendet die andere Klasse denselben Listener.  Die im Lieferumfang des .NET Framework enthaltenen Listenerklassen sind von der <xref:System.Diagnostics.TraceListener>\-Klasse abgeleitet.  
  
## Konfigurationsdatei  
 Dieses Element kann in der Computerkonfigurationsdatei \(**Machine.config**\) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie das Element **\<listeners\>** verwendet, um den Listener `MyListener``MyEventListener` und der **Listeners**\-Auflistung hinzuzufügen.  `MyListener` erstellt eine Datei mit der Bezeichnung `MyListener.log` und schreibt die Ausgabe in die Datei.  `MyEventListener` erstellt einen Eintrag im Ereignisprotokoll.  
  
```  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"   
          type="System.Diagnostics.TextWriterTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"   
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Diagnostics.TraceListener>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)