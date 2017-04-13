---
title: "&lt;add&gt;-Element f&#252;r &lt;sharedListeners&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add>-Element für <sharedListeners>"
  - "add-Element für <sharedListeners>"
  - "initializeData-Attribut"
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;add&gt;-Element f&#252;r &lt;sharedListeners&gt;
Fügt der `sharedListeners`\-Auflistung einen Listener hinzu.  `sharedListeners` ist eine Auflistung von Listenern, auf die jedes [\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) bzw. [\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) verweisen kann.  Listener in der `sharedListeners`\-Auflistung werden standardmäßig nicht in eine `Listeners`\-Auflistung eingefügt.  Sie müssen [\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) oder [\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) anhand des Namens hinzugefügt werden.  Die Listener in der `sharedListeners`\-Auflistung können zur Laufzeit nicht im Code abgerufen werden.  
  
## Syntax  
  
```  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`name`|Erforderliches Attribut.<br /><br /> Gibt den Namen des Listeners an, anhand dessen der freigegebene Listener einer `Listeners`\-Auflistung hinzugefügt wird.|  
|`type`|Erforderliches Attribut.<br /><br /> Gibt den Typ des Listeners an.  Sie müssen eine Zeichenfolge verwenden, die die in [Angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md) angegebenen Anforderungen erfüllt.|  
|`initializeData`|Optionales Attribut.<br /><br /> Die für die angegebene Klasse an den Konstruktor übergebene Zeichenfolge.|  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|Fügt einem Listener in der `sharedListeners`\-Auflistung einen Filter hinzu.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
|`sharedListeners`|Eine Auflistung von Listenern, auf die jedes source\-Element bzw. trace\-Element verweisen kann.|  
  
## Hinweise  
 Die im Lieferumfang des .NET Framework enthaltenen Listenerklassen sind von der <xref:System.Diagnostics.TraceListener>\-Klasse abgeleitet.  Der freigegebene Listener wird der `Listeners`\-Auflistung für eine Ablaufverfolgung oder Ablaufverfolgungsquelle anhand des Werts des `name`\-Attributs hinzugefügt.  Der Wert des `initializeData`\-Attributs hängt von der Art des erstellten Listeners ab.  `initializeData` muss nicht für alle Ablaufverfolgungslistener angegeben werden.  
  
> [!NOTE]
>  Wenn Sie das `initializeData`\-Attribut verwenden, wird möglicherweise die Compilerwarnung "Das Attribut "initializeData" ist nicht deklariert" angezeigt. Diese Warnung wird angezeigt, da die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener> überprüft werden, die das `initializeData`\-Attribut nicht erkennt.  In der Regel können Sie diese Warnung für Implementierungen von Ablaufverfolgungslistenern ignorieren, die über einen Konstruktor mit einem Parameter verfügen.  
  
 In der folgenden Tabelle werden die im Lieferumfang des .NET Framework enthaltenen Ablaufverfolgungslistener aufgeführt und die Werte der zugehörigen `initializeData`\-Attribute erläutert.  
  
|Ablaufverfolgungslistener\-Klasse|initializeData\-Attributwert|  
|---------------------------------------|----------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|Der `useErrorStream`\-Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>\-Konstruktor.  Legen Sie das `initializeData`\-Attribut auf "`true`" fest, um die Ablaufverfolgungs\- und Debugausgabe in den Standardfehlerstream zu schreiben, oder legen Sie es auf "`false`" fest, um in den Standardausgabestream zu schreiben.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName>|Der Name einer vorhandenen Ereignisprotokollquelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=fullName>|Der Name der Datei, in die von <xref:System.Diagnostics.EventSchemaTraceListener> geschrieben wird.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=fullName>|Der Name der Datei, in die von <xref:System.Diagnostics.TextWriterTraceListener> geschrieben wird.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Der Name der Datei, in die von <xref:System.Diagnostics.XmlWriterTraceListener> geschrieben wird.|  
  
## Konfigurationsdatei  
 Dieses Element kann in der Computerkonfigurationsdatei \(**Machine.config**\) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie `<add>`\-Elemente verwendet, um <xref:System.Diagnostics.TextWriterTraceListener> \- `textListener` der `sharedListeners`\-Auflistung hinzuzufügen.   `textListener` wird nach zur `Listeners`\-Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp` hinzugefügt.  Der `textListener`\-Listener schreibt die Ablaufverfolgungsausgabe in die Datei myListener.log.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## Siehe auch  
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.TraceListener>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)