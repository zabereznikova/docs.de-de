---
title: <add> Element für <listeners> für <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: c32205310f9fc451a5a55a943f925ee52f65c8a8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088999"
---
# <a name="add-element-for-listeners-for-source"></a>\<> Element für \<Listener > für \<Quelle hinzufügen >
Fügt einen Listener zu der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Quellen**](sources-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**Quelle**](source-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](listeners-element-for-source.md) Listener >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<hinzufügen >**

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
|`traceOutputOptions`|Optionales Attribut.<br /><br /> Gibt den <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A>-Eigenschafts Wert für den Ablaufverfolgungslistener an|  
|[benutzerdefinierte Attribute]|Optionale Attribute.<br /><br /> Gibt den Wert für listenerspezifische Attribute an, die durch die <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A>-Methode für diesen Listener identifiziert werden. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> ist ein Beispiel für ein zusätzliches Attribut, das für die Klasse <xref:System.Diagnostics.DelimitedListTraceListener> eindeutig ist.|  
  
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
 Die Listenerklassen, die mit dem .NET Framework ausgeliefert werden, werden von der <xref:System.Diagnostics.TraceListener> Klasse abgeleitet.  
  
 Wenn Sie das `name`-Attribut des Ablaufverfolgungslistener nicht angeben, wird für die <xref:System.Diagnostics.TraceListener.Name%2A>-Eigenschaft des Ablaufverfolgungslistener standardmäßig eine leere Zeichenfolge ("") verwendet Wenn die Anwendung nur über einen Listener verfügt, können Sie Sie hinzufügen, ohne einen Namen anzugeben, und Sie können Sie entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben. Wenn Ihre Anwendung jedoch über mehr als einen Listener verfügt, sollten Sie einen eindeutigen Namen für jeden Ablaufverfolgungslistener angeben, mit dem Sie einzelne Ablaufverfolgungslistener in der <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> Sammlung identifizieren und verwalten können.  
  
> [!NOTE]
> Das Hinzufügen von mehr als einem Ablaufverfolgungslistener desselben Typs und desselben Namens führt dazu, dass nur ein Ablaufverfolgungslistener dieses Typs und namens zur `Listeners` Auflistung hinzugefügt wird. Allerdings können Sie der `Listeners` Auflistung Programm gesteuert mehrere identische Listener hinzufügen.  
  
 Der Wert für das `initializeData`-Attribut ist abhängig vom Typ des von Ihnen erstellten Listener. Nicht alle Ablaufverfolgungslistener erfordern, dass Sie `initializeData`angeben  
  
> [!NOTE]
> Wenn Sie das `initializeData`-Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung, dass das initializeData-Attribut nicht deklariert ist. Diese Warnung tritt auf, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener>überprüft werden, die das `initializeData`-Attribut nicht erkennt. Normalerweise können Sie diese Warnung für Ablaufverfolgungslistener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt  
  
 Die folgende Tabelle zeigt die Ablaufverfolgungslistener, die im .NET Framework enthalten sind, und beschreibt den Wert ihrer `initializeData` Attribute.  
  
|Trace-Listenerklasse|initializeData-Attribut Wert|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Der `useErrorStream` Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>-Konstruktor.  Legen Sie das `initializeData`-Attribut auf "`true`" fest, um die Ablauf Verfolgung und Debugausgabe in den Standardfehlerstream zu schreiben Legen Sie Sie auf "`false`" fest, um in den Standardausgabestream zu schreiben|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Der Name einer vorhandenen Ereignisprotokoll Quelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die der <xref:System.Diagnostics.EventSchemaTraceListener> schreibt.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die der <xref:System.Diagnostics.TextWriterTraceListener> schreibt.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die der <xref:System.Diagnostics.XmlWriterTraceListener> schreibt.|  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie `<add>`-Elemente verwendet werden, um die Listener `console` und `textListener` der `Listeners` Auflistung für die Ablauf Verfolgungs Quelle `TraceSourceApp`hinzuzufügen. Der `textListener` Listener schreibt die Ablauf Verfolgungs Ausgabe in die Datei "MyListener. log".  
  
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
