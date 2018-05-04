---
title: '&lt;Hinzufügen&gt; -Element für &lt;Listener&gt; für &lt;Quelle&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ba8ff652003a9167ec370643797ac9300b83889a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-ltsourcegt"></a>&lt;Hinzufügen&gt; -Element für &lt;Listener&gt; für &lt;Quelle&gt;
Fügt einen Listener zu der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.  
  
 \<configuration>  
\<System.Diagnostics >  
\<Quellen >  
\<Quelle >  
\<Listener >  
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
|`type`|Attribut erforderlich, es sei denn, Sie einen Listener im verweisen die `sharedListeners` Auflistung, in dem Fall müssen nur anhand des Namens darauf verwiesen (finden Sie unter der [Beispiel](#example)).<br /><br /> Gibt den Typ des Listeners. Müssen Sie eine Zeichenfolge, die im angegebenen Anforderungen erfüllt verwenden [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Optionales Attribut.<br /><br /> Die Zeichenfolge, die für die angegebene Klasse an den Konstruktor übergeben werden. Ein <xref:System.Configuration.ConfigurationException> wird ausgelöst, wenn die Klasse keinen Konstruktor verfügt, der eine Zeichenfolge akzeptiert.|  
|`name`|Optionales Attribut.<br /><br /> Gibt den Namen des Listeners.|  
|`traceOutputOptions`|Optionales Attribut.<br /><br /> Gibt an, die <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> Eigenschaftswert für den Ablaufverfolgungslistener.|  
|[benutzerdefinierte Attribute]|Optionale Attribute.<br /><br /> Gibt den Wert für den Listener-spezifische Attribute durch die <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> Methode für diesen Listener. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> ist ein Beispiel für ein zusätzliches Attribut nur für die <xref:System.Diagnostics.DelimitedListTraceListener> Klasse.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|Fügt einen Filter zu einem Listener in der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sources`|Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.|  
|`source`|Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.|  
|`listeners`|Gibt die Listener, mit die sammeln, speichern und Weiterleiten von Nachrichten an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Listenerklassen, die im Lieferumfang von .NET Framework abgeleitet werden, aus der <xref:System.Diagnostics.TraceListener> Klasse.  
  
 Wenn Sie keinen angeben der `name` Attribut des Ablaufverfolgungslisteners, die <xref:System.Diagnostics.TraceListener.Name%2A> -Eigenschaft des Ablaufverfolgungslisteners verwendet standardmäßig eine leere Zeichenfolge (""). Wenn die Anwendung nur einen Listener verfügt, können Sie ihn ohne Angabe eines Namens hinzufügen und können Sie diesen entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben. Wenn die Anwendung mehr als einen Listener verfügt, Sie sollten jedoch angeben einen eindeutigen Namen für jeden Ablaufverfolgungslistener, wodurch Sie zum Erkennen und Verwalten einzelner Ablaufverfolgungslistener in der <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> Auflistung.  
  
> [!NOTE]
>  Hinzufügen von mehr als ein Ablaufverfolgungslistener des gleichen Typs und mit dem gleichen Namen nur ein einziger Ablaufverfolgungslistener dieses Typs, und nennen Sie die hinzugefügte der `Listeners` Auflistung. Allerdings können Sie programmgesteuert mehrere identische Listener hinzufügen der `Listeners` Auflistung.  
  
 Der Wert für die `initializeData` Attribut hängt vom Typ des Listeners, die Sie erstellen. Nicht alle Ablaufverfolgungslistener erfordern die Angabe `initializeData`.  
  
> [!NOTE]
>  Bei Verwendung der `initializeData` -Attribut, erhalten Sie möglicherweise die compilerwarnung "das Attribut"InitializeData"ist nicht deklariert." Diese Warnung tritt auf, da die Konfigurationseinstellungen für die abstrakte Basisklasse überprüft werden <xref:System.Diagnostics.TraceListener>, die nicht erkennt die `initializeData` Attribut. In der Regel können Sie diese Warnung für Trace-Listener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter akzeptiert.  
  
 In der folgenden Tabelle werden die Ablaufverfolgungslistener, die mit .NET Framework enthalten sind, und beschreibt den Wert der ihre `initializeData` Attribute.  
  
|Trace Listenerklasse|InitializeData-Attribut-Wert|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Die `useErrorStream` Wert für die <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.  Legen Sie die `initializeData` -Attribut auf "`true`"zum Schreiben von Ablaufverfolgung und Debuggen die Ausgabe des Standardfehlerstreams; legen Sie sie auf"`false`" zum Schreiben in den Standardausgabestream.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Der Name der Datei die <xref:System.Diagnostics.DelimitedListTraceListener> schreibt in.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Der Name einer vorhandenen Ereignisprotokoll-Quelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Der Name der Datei, die die <xref:System.Diagnostics.EventSchemaTraceListener> schreibt in.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, die die <xref:System.Diagnostics.TextWriterTraceListener> schreibt in.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, die die <xref:System.Diagnostics.XmlWriterTraceListener> schreibt in.|  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Computerkonfigurationsdatei ("Machine.config") und der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie `<add>` Elemente, die Listener hinzugefügt `console` und `textListener` auf die `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`. Die `textListener` Listener schreibt die Ablaufverfolgungsausgabe in die Datei myListener.log.  
  
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
