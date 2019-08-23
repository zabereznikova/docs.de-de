---
title: <add>-Element <listeners> für für<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 96bfde3ec425f6f77d1d655808d155eb0e6fcd0f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927194"
---
# <a name="add-element-for-listeners-for-source"></a>\<> Element für \<Listener > für \<Quell > Hinzufügen
Fügt einen Listener zu der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.  
  
 \<configuration>  
\<system.diagnostics>  
\<Quellen >  
\<Quell >  
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
|`type`|Erforderliches Attribut, es sei denn, Sie verweisen in der `sharedListeners` Auflistung auf einen Listener. in diesem Fall müssen Sie nur anhand des Namens darauf verweisen (siehe [Beispiel](#example)).<br /><br /> Gibt den Typ des Listener an. Sie müssen eine Zeichenfolge verwenden, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.|  
|`initializeData`|Optionales Attribut.<br /><br /> Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wird. Eine <xref:System.Configuration.ConfigurationException> wird ausgelöst, wenn die Klasse über keinen Konstruktor verfügt, der eine Zeichenfolge annimmt.|  
|`name`|Optionales Attribut.<br /><br /> Gibt den Namen des Listener an.|  
|`traceOutputOptions`|Optionales Attribut.<br /><br /> Gibt den <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> Eigenschafts Wert für den Ablaufverfolgungslistener an.|  
|[benutzerdefinierte Attribute]|Optionale Attribute.<br /><br /> Gibt den Wert für listenerspezifische Attribute an, die <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> von der-Methode für diesen Listener identifiziert werden. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>ist ein Beispiel für ein zusätzliches Attribut, das für <xref:System.Diagnostics.DelimitedListTraceListener> die-Klasse eindeutig ist.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|Fügt einen Filter zu einem Listener in der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sources`|Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.|  
|`source`|Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.|  
|`listeners`|Gibt Listener an, die Nachrichten erfassen, speichern und weiterleiten.|  
  
## <a name="remarks"></a>Hinweise  
 Die Listenerklassen, die mit dem .NET Framework ausgeliefert <xref:System.Diagnostics.TraceListener> werden, werden von der-Klasse abgeleitet  
  
 Wenn Sie das `name` -Attribut des Ablaufverfolgungslistener <xref:System.Diagnostics.TraceListener.Name%2A> nicht angeben, wird standardmäßig eine leere Zeichenfolge ("") für die-Eigenschaft des Ablaufverfolgungslistener verwendet Wenn die Anwendung nur über einen Listener verfügt, können Sie Sie hinzufügen, ohne einen Namen anzugeben, und Sie können Sie entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben. Wenn Ihre Anwendung jedoch über mehr als einen Listener verfügt, sollten Sie einen eindeutigen Namen für jeden Ablaufverfolgungslistener angeben, mit dem Sie einzelne Ablaufverfolgungslistener in der <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> Sammlung identifizieren und verwalten können.  
  
> [!NOTE]
> Das Hinzufügen von mehr als einem Ablaufverfolgungslistener desselben Typs und desselben Namens führt dazu, dass nur ein Ablaufverfolgungslistener dieses Typs und namens zur `Listeners` Auflistung hinzugefügt wird. Allerdings können Sie der `Listeners` Auflistung Programm gesteuert mehrere identische Listener hinzufügen.  
  
 Der Wert für das `initializeData` -Attribut ist abhängig vom Typ des von Ihnen erstellten Listener. Nicht alle Ablaufverfolgungslistener erfordern, dass Sie angeben `initializeData`  
  
> [!NOTE]
> Wenn Sie das `initializeData` -Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung, dass das initializeData-Attribut nicht deklariert ist. Diese Warnung tritt auf, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener>überprüft werden, die das `initializeData` -Attribut nicht erkennt. Normalerweise können Sie diese Warnung für Ablaufverfolgungslistener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt  
  
 In der folgenden Tabelle werden die Ablaufverfolgungslistener angezeigt, die im .NET Framework enthalten `initializeData` sind, und der Wert ihrer Attribute wird beschrieben.  
  
|Trace-Listenerklasse|initializeData-Attribut Wert|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Der `useErrorStream` Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.  Legen Sie `initializeData` das-Attribut`true`auf "" fest, um die Ablauf Verfolgung und Debugausgabe in den Standardfehlerstream zu schreiben. Legen Sie Sie auf "`false`" fest|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Der Name der Datei, in <xref:System.Diagnostics.DelimitedListTraceListener> die geschrieben wird.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Der Name einer vorhandenen Ereignisprotokoll Quelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die <xref:System.Diagnostics.EventSchemaTraceListener> geschrieben wird.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die <xref:System.Diagnostics.TextWriterTraceListener> geschrieben wird.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die <xref:System.Diagnostics.XmlWriterTraceListener> geschrieben wird.|  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie `<add>` Elemente verwendet werden, um `console` die `textListener` Listener und `Listeners` der-Auflistung für die `TraceSourceApp`Ablauf Verfolgungs Quelle hinzuzufügen. Der `textListener` Listener schreibt die Ablauf Verfolgungs Ausgabe in die Datei "MyListener. log".  
  
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

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](index.md)
- [Trace Listeners (Ablaufverfolgungslistener)](../../../debug-trace-profile/trace-listeners.md)
