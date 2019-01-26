---
title: '&lt;Hinzufügen&gt; -Element für &lt;Listener&gt; für &lt;Ablaufverfolgung&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: 4edefcfdd56be56ccc0ccaf2bff118ba8266e226
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083638"
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-lttracegt"></a>&lt;Hinzufügen&gt; -Element für &lt;Listener&gt; für &lt;Ablaufverfolgung&gt;
Fügt einen Listener, damit die **Listener** Auflistung.  
  
 \<configuration>  
\<system.diagnostics>  
\<trace>  
\<listeners>  
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
|**Typ**|Erforderliches Attribut.<br /><br /> Gibt den Typ des Listeners. Sie müssen eine Zeichenfolge, die die in angegebenen Anforderungen erfüllt verwenden [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Optionales Attribut.<br /><br /> Die Zeichenfolge, die für die angegebene Klasse an den Konstruktor übergeben werden.|  
|**name**|Optionales Attribut.<br /><br /> Gibt den Namen des Listeners.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|Fügt einen Filter zu einem Listener in der `Listeners` Sammlung für eine Ablaufverfolgung.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`listeners`|Gibt an, einen Listener, der sammelt, speichert, und leitet Nachrichten. Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel.|  
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|  
|`trace`|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
## <a name="remarks"></a>Hinweise  
 Die <xref:System.Diagnostics.Debug> und <xref:System.Diagnostics.Trace> Klassen verwenden dieselbe **Listener** Auflistung. Wenn Sie einen Listener-Objekt der Auflistung in einer dieser Klassen hinzufügen, wird die andere Klasse den gleichen Listener verwendet. Die Listenerklassen leiten sich von der <xref:System.Diagnostics.TraceListener>.  
  
 Wenn Sie keinen angeben der `name` Attribut des Ablaufverfolgungslisteners, der <xref:System.Diagnostics.TraceListener.Name%2A> die Trace-Listener-Standardwerte in eine leere Zeichenfolge (""). Wenn Ihre Anwendung nur einen Listener verfügt, können Sie ohne Angabe eines Namens hinzufügen und entfernen sie, indem Sie eine leere Zeichenfolge für den Namen angeben. Wenn Ihre Anwendung mehr als einen Listener verfügt, Sie jedoch sollte angeben eindeutige Namen für jeden Ablaufverfolgungslistener, wodurch Sie zum Erkennen und Verwalten von einzelnen Ablaufverfolgungslistener in der <xref:System.Diagnostics.Debug.Listeners%2A> und <xref:System.Diagnostics.Trace.Listeners%2A> Sammlungen.  
  
> [!NOTE]
>  Hinzufügen von mehr als eine Ablaufverfolgungs-Listener des gleichen Typs und mit dem gleichen nennen Sie dieses Typs führt nur eine Ablaufverfolgungs-Listener und hinzugefügte der `Listeners` Auflistung. Allerdings können Sie programmgesteuert mehrere identische Listener hinzufügen der `Listeners` Auflistung.  
  
 Der Wert für die **InitializeData** -Attributs hängt der Typ des Listeners, die Sie erstellen. Nicht alle Ablaufverfolgungslistener erfordern die Angabe **InitializeData**.  
  
> [!NOTE]
>  Bei Verwendung der `initializeData` -Attribut, erhalten Sie möglicherweise die compilerwarnung "das Attribut"InitializeData"ist nicht deklariert." Diese Warnung tritt auf, da die Konfigurationseinstellungen für die abstrakte Basisklasse überprüft werden <xref:System.Diagnostics.TraceListener>, die nicht erkennt die `initializeData` Attribut. In der Regel können Sie Ablaufverfolgungs-Listener-Implementierungen diese Warnung ignorieren, die über einen Konstruktor verfügen, der einen Parameter akzeptiert.  
  
 In der folgende Tabelle werden die Ablaufverfolgungslistener, die mit .NET Framework enthalten sind, und beschreibt den Wert der ihre **InitializeData** Attribute.  
  
|Trace Listenerklasse|InitializeData-Attributwert|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Die `useErrorStream` Wert für die <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.  Legen Sie die `initializeData` -Attribut auf "`true`" Ablaufverfolgungs- und Debugeinstellungen schreiben die Ausgabe <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" zum Schreiben in <xref:System.Console.Out%2A?displayProperty=nameWithType>.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Der Name der Datei die <xref:System.Diagnostics.DelimitedListTraceListener> schreibt in.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Der Name des Namens einer vorhandenen Ereignisprotokollquelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Der Name der Datei, die die <xref:System.Diagnostics.EventSchemaTraceListener> schreibt in.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, die die <xref:System.Diagnostics.TextWriterTraceListener> schreibt in.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, die die <xref:System.Diagnostics.XmlWriterTraceListener> schreibt in.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie mit  **\<hinzufügen >** Elemente, die Listener hinzugefügt `MyListener` und `MyEventListener` auf die **Listener** Auflistung. `MyListener` erstellt eine Datei namens `MyListener.log` und schreibt die Ausgabe in der Datei. `MyEventListener` erstellt einen Eintrag im Ereignisprotokoll.  
  
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
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [Trace Listeners (Ablaufverfolgungslistener)](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
