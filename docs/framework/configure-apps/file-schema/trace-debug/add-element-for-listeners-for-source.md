---
title: "&lt;add&gt;-Element f&#252;r &lt;listeners&gt; f&#252;r &lt;source&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add>-Element für <listeners> für <source>"
  - "add-Element für <listeners> für <source>"
  - "initializeData-Attribut"
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# &lt;add&gt;-Element f&#252;r &lt;listeners&gt; f&#252;r &lt;source&gt;
Fügt der `Listeners`\-Auflistung für eine Ablaufverfolgungsquelle einen Listener hinzu.  
  
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
|`type`|Erforderliches Attribut.<br /><br /> Gibt den Typ des Listeners an.  Sie müssen eine Zeichenfolge verwenden, die die in [Angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md) angegebenen Anforderungen erfüllt.|  
|`initializeData`|Optionales Attribut.<br /><br /> Die für die angegebene Klasse an den Konstruktor übergebene Zeichenfolge.  Wenn die Klasse über keinen Konstruktor verfügt, der eine Zeichenfolge akzeptiert, wird eine <xref:System.Configuration.ConfigurationException> ausgelöst.|  
|`name`|Optionales Attribut.<br /><br /> Gibt den Namen des Listeners an.|  
|`traceOutputOptions`|Optionales Attribut.<br /><br /> Gibt den <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A>\-Eigenschaftswert für den Ablaufverfolgungslistener an.|  
|\[benutzerdefinierte Attribute\]|Optionale Attribute.<br /><br /> Gibt den Wert der für den Listener spezifischen Attribute an, die von der <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A>\-Methode für diesen Listener ermittelt werden.  <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> ist ein Beispiel für ein zusätzliches Attribut, das für die <xref:System.Diagnostics.DelimitedListTraceListener>\-Klasse eindeutig ist.|  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|Fügt einem Listener in der `Listeners`\-Auflistung für eine Ablaufverfolgungsquelle einen Filter hinzu.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
|`sources`|Enthält Ablaufverfolgungsquellen, die Ablaufverfolgungsmeldungen initiieren.|  
|`source`|Gibt eine Ablaufverfolgungsquelle an, die Ablaufverfolgungsmeldungen initiiert.|  
|`listeners`|Gibt Listener an, die Meldungen sammeln, speichern und weiterleiten.|  
  
## Hinweise  
 Die im Lieferumfang des .NET Framework enthaltenen Listenerklassen sind von der <xref:System.Diagnostics.TraceListener>\-Klasse abgeleitet.  
  
 Wenn Sie kein `name`\-Attribut des Ablaufverfolgungslisteners angeben, entspricht die <xref:System.Diagnostics.TraceListener.Name%2A>\-Eigenschaft des Ablaufverfolgungslisteners standardmäßig einer leeren Zeichenfolge \(""\).  Wenn die Anwendung über nur einen Listener verfügt, können Sie ihn ohne Angabe eines Namens hinzufügen und unter Angabe einer leeren Zeichenfolge für den Namen entfernen.  Wenn die Anwendung hingegen mehrere Listener aufweist, müssen Sie für jeden Ablaufverfolgungslistener einen eindeutigen Namen angeben, sodass die einzelnen Ablaufverfolgungslistener in der <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=fullName>\-Auflistung ermittelt und verwaltet werden können.  
  
> [!NOTE]
>  Wenn Sie mehrere Ablaufverfolgungslistener mit dem gleichen Typ und Namen hinzufügen, wird der `Listeners`\-Auflistung nur ein einziger Ablaufverfolgungslistener dieses Typs und Namens hinzugefügt.  Sie können der `Listeners`\-Auflistung jedoch programmgesteuert mehrere identische Listener hinzufügen.  
  
 Der Wert des `initializeData`\-Attributs hängt von der Art des erstellten Listeners ab.  `initializeData` muss nicht für alle Ablaufverfolgungslistener angegeben werden.  
  
> [!NOTE]
>  Wenn Sie das `initializeData`\-Attribut verwenden, wird möglicherweise die Compilerwarnung "Das Attribut "initializeData" ist nicht deklariert" angezeigt. Diese Warnung wird angezeigt, da die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener> überprüft werden, die das `initializeData`\-Attribut nicht erkennt.  In der Regel können Sie diese Warnung für Implementierungen von Ablaufverfolgungslistenern ignorieren, die über einen Konstruktor mit einem Parameter verfügen.  
  
 In der folgenden Tabelle werden die im Lieferumfang des .NET Framework enthaltenen Ablaufverfolgungslistener aufgeführt und die Werte der zugehörigen `initializeData`\-Attribute erläutert.  
  
|Ablaufverfolgungslistener\-Klasse|initializeData\-Attributwert|  
|---------------------------------------|----------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName>|Der `useErrorStream`\-Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>\-Konstruktor.  Legen Sie das `initializeData`\-Attribut auf "`true`" fest, um die Ablaufverfolgungs\- und Debugausgabe in den Standardfehlerstream zu schreiben, oder legen Sie es auf "`false`" fest, um in den Standardausgabestream zu schreiben.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName>|Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName>|Der Name einer vorhandenen Ereignisprotokollquelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=fullName>|Der Name der Datei, in die von <xref:System.Diagnostics.EventSchemaTraceListener> geschrieben wird.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=fullName>|Der Name der Datei, in die von <xref:System.Diagnostics.TextWriterTraceListener> geschrieben wird.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName>|Der Name der Datei, in die von <xref:System.Diagnostics.XmlWriterTraceListener> geschrieben wird.|  
  
## Konfigurationsdatei  
 Dieses Element kann in der Computerkonfigurationsdatei \(**Machine.config**\) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie der `Listeners`\-Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp` mithilfe der `<add>`\-Elemente die Listener `console` und `textListener` hinzugefügt werden.  Der `textListener`\-Listener schreibt die Ablaufverfolgungsausgabe in die Datei myListener.log.  
  
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