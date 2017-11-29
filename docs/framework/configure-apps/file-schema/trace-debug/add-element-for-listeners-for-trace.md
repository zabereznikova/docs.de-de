---
title: "&lt;Hinzufügen&gt; -Element für &lt;Listener&gt; für &lt;Trace&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
caps.latest.revision: "24"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bbb74d9a542833a96c61bcc09f6e4e5f0807843d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-lttracegt"></a>&lt;Hinzufügen&gt; -Element für &lt;Listener&gt; für &lt;Trace&gt;
Fügt einen Listener, damit die **Listener** Auflistung.  
  
 \<configuration>  
\<System.Diagnostics >  
\<Trace >  
\<Listener >  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**Typ**|Erforderliches Attribut.<br /><br /> Gibt den Typ des Listeners. Müssen Sie eine Zeichenfolge, die im angegebenen Anforderungen erfüllt verwenden [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Optionales Attribut.<br /><br /> Die Zeichenfolge, die für die angegebene Klasse an den Konstruktor übergeben werden.|  
|**name**|Optionales Attribut.<br /><br /> Gibt den Namen des Listeners.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|Fügt einen Filter mit einem Listener in der `Listeners` Auflistung für eine Ablaufverfolgung.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`listeners`|Gibt an, einen Listener, der erfasst hat, speichert, und leitet Nachrichten. Listener leiten die Ablaufverfolgungsausgabe an ein geeignetes Ziel an.|  
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|  
|`trace`|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
## <a name="remarks"></a>Hinweise  
 Die <xref:System.Diagnostics.Debug> und <xref:System.Diagnostics.Trace> Klassen verwenden dieselbe **Listener** Auflistung. Wenn Sie der Auflistung in einer dieser Klassen ein Listener-Objekt hinzugefügt haben, verwendet die andere Klasse denselben Listener. Die Listenerklassen abgeleitet werden, aus der <xref:System.Diagnostics.TraceListener>.  
  
 Wenn Sie keinen angeben der `name` Attribut des Ablaufverfolgungslisteners, die <xref:System.Diagnostics.TraceListener.Name%2A> die Trace-Listener-Standardwerte in eine leere Zeichenfolge (""). Wenn Ihre Anwendung nur einen Listener verfügt, können Sie ihn ohne Angabe eines Namens hinzufügen und entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben. Wenn die Anwendung mehr als einen Listener verfügt, Sie sollten jedoch angeben eindeutige Namen für jeden Ablaufverfolgungslistener, wodurch Sie zum Erkennen und Verwalten von einzelnen Ablaufverfolgungslistener in der <xref:System.Diagnostics.Debug.Listeners%2A> und <xref:System.Diagnostics.Trace.Listeners%2A> Sammlungen.  
  
> [!NOTE]
>  Hinzufügen von mehr als ein Ablaufverfolgungslistener des gleichen Typs und mit dem gleichen Namen nur ein einziger Ablaufverfolgungslistener dieses Typs, und nennen Sie die hinzugefügte der `Listeners` Auflistung. Allerdings können Sie programmgesteuert mehrere identische Listener hinzufügen der `Listeners` Auflistung.  
  
 Der Wert für die **InitializeData** Attribut hängt vom Typ des Listeners, die Sie erstellen. Nicht alle Ablaufverfolgungslistener erfordern die Angabe **InitializeData**.  
  
> [!NOTE]
>  Bei Verwendung der `initializeData` -Attribut, erhalten Sie möglicherweise die compilerwarnung "das Attribut"InitializeData"ist nicht deklariert." Diese Warnung tritt auf, da die Konfigurationseinstellungen für die abstrakte Basisklasse überprüft werden <xref:System.Diagnostics.TraceListener>, die nicht erkennt die `initializeData` Attribut. In der Regel können Sie diese Warnung für Trace-Listener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter akzeptiert.  
  
 In der folgenden Tabelle werden die Ablaufverfolgungslistener, die mit .NET Framework enthalten sind, und beschreibt den Wert der ihre **InitializeData** Attribute.  
  
|Trace Listenerklasse|InitializeData-Attribut-Wert|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Die `useErrorStream` Wert für die <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.  Legen Sie die `initializeData` -Attribut auf "`true`" zum Schreiben von Ablaufverfolgung und Debug-Ausgabe in <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" zum Schreiben in <xref:System.Console.Out%2A?displayProperty=nameWithType>.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Der Name der Datei die <xref:System.Diagnostics.DelimitedListTraceListener> schreibt in.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Der Name des Namens einer vorhandenen Ereignisprotokoll-Quelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Der Name der Datei, die die <xref:System.Diagnostics.EventSchemaTraceListener> schreibt in.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, die die <xref:System.Diagnostics.TextWriterTraceListener> schreibt in.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, die die <xref:System.Diagnostics.XmlWriterTraceListener> schreibt in.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie  **\<hinzufügen >** Elemente, die Listener hinzugefügt `MyListener` und `MyEventListener` auf die **Listener** Auflistung. `MyListener`erstellt eine Datei namens `MyListener.log` und schreibt die Ausgabe in die Datei. `MyEventListener`erstellt einen Eintrag im Ereignisprotokoll.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [Trace Listeners (Ablaufverfolgungslistener)](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
