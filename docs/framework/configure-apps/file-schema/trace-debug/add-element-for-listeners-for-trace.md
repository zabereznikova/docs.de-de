---
title: "&lt;add&gt;-Element f&#252;r &lt;listeners&gt; f&#252;r &lt;trace&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add>-Element für <listeners>"
  - "add-Element für <listeners>"
  - "initializeData-Attribut"
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
caps.latest.revision: 24
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 22
---
# &lt;add&gt;-Element f&#252;r &lt;listeners&gt; f&#252;r &lt;trace&gt;
Fügt der **Listeners**\-Auflistung einen Listener hinzu.  
  
## Syntax  
  
```  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|**type**|Erforderliches Attribut.<br /><br /> Gibt den Typ des Listeners an.  Sie müssen eine Zeichenfolge verwenden, die die unter [Angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md) aufgeführten Anforderungen erfüllt.|  
|**initializeData**|Optionales Attribut.<br /><br /> Die für die angegebene Klasse an den Konstruktor übergebene Zeichenfolge.|  
|**name**|Optionales Attribut.<br /><br /> Gibt den Namen des Listeners an.|  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|Fügt einem Listener in der `Listeners`\-Auflistung für eine Ablaufverfolgung einen Filter hinzu.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`listeners`|Gibt einen Listener an, der Meldungen sammelt, speichert und weiterleitet.  Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel.|  
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET\-Konfigurationsabschnitt an.|  
|`trace`|Enthält Listener, die Verfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
## Hinweise  
 Die <xref:System.Diagnostics.Debug>\- Klasse und die <xref:System.Diagnostics.Trace>\-Klasse verwenden die gleiche **Listeners**\-Auflistung.  Wenn Sie der Auflistung in einer dieser Klassen ein Listener\-Objekt hinzufügen, verwendet die andere Klasse denselben Listener.  Die Listenerklassen werden von der [TraceListener\-Klasse](frlrfSystemDiagnosticsTraceListenerClassTopic) abgeleitet.  
  
 Wenn Sie das `nam`e\-Attribut des Ablaufverfolgungslisteners nicht angeben, entspricht der <xref:System.Diagnostics.TraceListener.Name%2A> des Ablaufverfolgungslisteners standardmäßig einer leeren Zeichenfolge \(""\).  Wenn die Anwendung über nur einen Listener verfügt, können Sie ihn ohne Angabe eines Namens hinzufügen und unter Angabe einer leeren Zeichenfolge für den Namen entfernen.  Wenn die Anwendung hingegen mehrere Listener aufweist, sollten Sie für jeden Ablaufverfolgungslistener einen eindeutigen Namen angeben, sodass die einzelnen Ablaufverfolgungslistener in der <xref:System.Diagnostics.Debug.Listeners%2A>\-Auflistung und der <xref:System.Diagnostics.Trace.Listeners%2A>\-Auflistung identifiziert und verwaltet werden können.  
  
> [!NOTE]
>  Wenn Sie mehrere Ablaufverfolgungslistener mit dem gleichen Typ und Namen hinzufügen, wird der `Listeners`\-Auflistung nur ein einziger Ablaufverfolgungslistener dieses Typs und Namens hinzugefügt.  Sie können der `Listeners`\-Auflistung jedoch programmgesteuert mehrere identische Listener hinzufügen.  
  
 Der Wert des **initializeData**\-Attributs hängt von der Art des Listeners ab, den Sie erstellen.  **initializeData** muss nicht für alle Ablaufverfolgungslistener angegeben werden.  
  
> [!NOTE]
>  Wenn Sie das `initializeData`\-Attribut verwenden, wird möglicherweise die Compilerwarnung "Das Attribut "initializeData" ist nicht deklariert" angezeigt. Diese Warnung wird angezeigt, da die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener> überprüft werden, die das `initializeData`\-Attribut nicht erkennt.  In der Regel können Sie diese Warnung für Implementierungen von Ablaufverfolgungslistenern ignorieren, die über einen Konstruktor mit einem Parameter verfügen.  
  
 In der folgenden Tabelle werden die im Lieferumfang von .NET Framework enthaltenen Ablaufverfolgungslistener aufgeführt und die Werte der zugehörigen **initializeData**\-Attribute erläutert.  
  
|Ablaufverfolgungslistener\-Klasse|initializeData\-Attributwert|  
|---------------------------------------|----------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName>|Der `useErrorStream`\-Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>\-Konstruktor.  Legen Sie das `initializeData`\-Attribut auf "`true`" fest, damit Ablaufverfolgungs\- und Debugausgabe in <xref:System.Console.Error%2A?displayProperty=fullName> geschrieben werden. Wenn Sie es auf "`false`" festlegen, erfolgt die Ausgabe in <xref:System.Console.Out%2A?displayProperty=fullName>.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName>|Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName>|Der Name einer vorhandenen Ereignisprotokollquelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=fullName>|Der Name der Datei, in die von <xref:System.Diagnostics.EventSchemaTraceListener> geschrieben wird.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=fullName>|Der Name der Datei, in die von <xref:System.Diagnostics.TextWriterTraceListener> geschrieben wird.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName>|Der Name der Datei, in die von <xref:System.Diagnostics.XmlWriterTraceListener> geschrieben wird.|  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie **\<Hinzufügen\>**\-Elemente verwendet, um den Listener `MyListener``MyEventListener` und der **Listeners**\-Auflistung hinzuzufügen.  `MyListener` erstellt eine Datei mit der Bezeichnung `MyListener.log` und schreibt die Ausgabe in die Datei.  `MyEventListener` erstellt einen Eintrag im Ereignisprotokoll.  
  
```  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.Debug>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 <xref:System.Diagnostics.ConsoleTraceListener>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)