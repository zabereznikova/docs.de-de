---
title: '&lt;Hinzufügen&gt; -Element für &lt;SharedListeners&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 27d83ba706b4d93b4ac5426bf5bae59b4bfc0d9a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltsharedlistenersgt"></a>&lt;Hinzufügen&gt; -Element für &lt;SharedListeners&gt;
Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu. `sharedListeners` eine Auflistung von Listenern, die von jedem ist [ \<Quelle >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) oder [ \<Trace >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) verweisen können.  Standardmäßig Listener in der `sharedListeners` Auflistung befinden sich keinem `Listeners` Auflistung. Sie müssen hinzugefügt werden, anhand des Namens der [ \<Quelle >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) oder [ \<Trace >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md). Es ist nicht möglich, den Listener zu erhalten, in der `sharedListeners` Auflistung im Code zur Laufzeit.  
  
 \<configuration>  
\<System.Diagnostics >  
\<SharedListeners >-Element  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`name`|Erforderliches Attribut.<br /><br /> Gibt den Namen des Listeners, den verwendet wird, um die freigegebene Listener zum Hinzufügen einer `Listeners` Auflistung.|  
|`type`|Erforderliches Attribut.<br /><br /> Gibt den Typ des Listeners. Müssen Sie eine Zeichenfolge, die im angegebenen Anforderungen erfüllt verwenden [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Optionales Attribut.<br /><br /> Die Zeichenfolge, die für die angegebene Klasse an den Konstruktor übergeben werden.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sharedListeners`|Eine Auflistung von Listenern, die jeder Quelle oder das Trace-Element verweisen können.|  
  
## <a name="remarks"></a>Hinweise  
 Die Listenerklassen, die im Lieferumfang von .NET Framework abgeleitet werden, aus der <xref:System.Diagnostics.TraceListener> Klasse. Der Wert für die `name` Attribut wird verwendet, um die freigegebene Listener zum Hinzufügen einer `Listeners` -Auflistung für eine Ablaufverfolgung oder eine Ablaufverfolgungsquelle. Der Wert für die `initializeData` Attribut hängt vom Typ des Listeners, die Sie erstellen. Nicht alle Ablaufverfolgungslistener erfordern die Angabe `initializeData`.  
  
> [!NOTE]
>  Bei Verwendung der `initializeData` -Attribut, erhalten Sie möglicherweise die compilerwarnung "das Attribut"InitializeData"ist nicht deklariert." Diese Warnung tritt auf, da die Konfigurationseinstellungen für die abstrakte Basisklasse überprüft werden <xref:System.Diagnostics.TraceListener>, die nicht erkennt die `initializeData` Attribut. In der Regel können Sie diese Warnung für Trace-Listener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter akzeptiert.  
  
 In der folgenden Tabelle werden die Ablaufverfolgungslistener, die mit .NET Framework enthalten sind, und beschreibt den Wert der ihre `initializeData` Attribute.  
  
|Trace Listenerklasse|InitializeData-Attribut-Wert|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|Die `useErrorStream` Wert für die <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.  Legen Sie die `initializeData` -Attribut auf "`true`"zum Schreiben von Ablaufverfolgung und Debuggen die Ausgabe des Standardfehlerstreams; legen Sie sie auf"`false`" zum Schreiben in den Standardausgabestream.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Der Name der Datei die <xref:System.Diagnostics.DelimitedListTraceListener> schreibt in.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Der Name einer vorhandenen Ereignisprotokoll-Quelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Der Name der Datei, die die <xref:System.Diagnostics.EventSchemaTraceListener> schreibt in.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, die die <xref:System.Diagnostics.TextWriterTraceListener> schreibt in.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Der Name der Datei, die die <xref:System.Diagnostics.XmlWriterTraceListener> schreibt in.|  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Computerkonfigurationsdatei ("Machine.config") und der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie `<add>` hinzuzufügenden Elemente der <xref:System.Diagnostics.TextWriterTraceListener> `textListener` auf die `sharedListeners` Auflistung.   `textListener` anhand des Namens hinzugefügt wird die `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`. Die `textListener` Listener schreibt die Ablaufverfolgungsausgabe in die Datei myListener.log.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [Trace Listeners (Ablaufverfolgungslistener)](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
