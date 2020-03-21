---
title: <add>-Element für <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153606"
---
# <a name="add-element-for-sharedlisteners"></a>\<Hinzufügen> \<Elements für sharedListeners>
Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu. `sharedListeners`ist eine Sammlung von [ \<](source-element.md) Listenern, auf die jede Quelle>oder [ \<Ablaufverfolgungs>](trace-element.md) verweisen kann.  Standardmäßig werden Listener `sharedListeners` in der Auflistung `Listeners` nicht in einer Auflistung platziert. Sie müssen dem [ \<Quell>](source-element.md) oder [ \<Ablaufverfolgungs->](trace-element.md)mit Namen hinzugefügt werden. Es ist nicht möglich, die `sharedListeners` Listener in der Auflistung zur Laufzeit im Code abrufe.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**

## <a name="syntax"></a>Syntax  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`name`|Erforderliches Attribut.<br /><br /> Gibt den Namen des Listeners an, der zum Hinzufügen `Listeners` des freigegebenen Listeners zu einer Auflistung verwendet wird.|  
|`type`|Erforderliches Attribut.<br /><br /> Gibt den Typ des Listeners an. Sie müssen eine Zeichenfolge verwenden, die die unter [Angeben von vollqualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen erfüllt.|  
|`initializeData`|Optionales Attribut.<br /><br /> Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wurde.|  
|`traceOutputOptions`|Optionales Attribut.<br/><br/>Die Zeichenfolgendarstellung eines <xref:System.Diagnostics.TraceOptions> oder mehrerer Enumerationsmember, die die Daten angibt, die in die Ablaufverfolgungsausgabe geschrieben werden sollen. Mehrere Elemente werden durch Kommas getrennt. Der Standardwert ist "Keine".|

### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Filter>](filter-element-for-add-for-sharedlisteners.md)|Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sharedListeners`|Eine Auflistung von Listenern, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die Listenerklassen, die mit .NET Framework <xref:System.Diagnostics.TraceListener> ausgeliefert wurden, leiten sich von der Klasse ab. Der Wert `name` für das Attribut wird verwendet, `Listeners` um den freigegebenen Listener zu einer Auflistung für eine Ablaufverfolgung oder eine Ablaufverfolgungsquelle hinzuzufügen. Der Wert `initializeData` für das Attribut hängt vom Typ des Listeners ab, den Sie erstellen. Nicht alle Ablaufverfolgungslistener erfordern, dass Sie angeben. `initializeData`  
  
> [!NOTE]
> Wenn Sie `initializeData` das Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung "Das Attribut 'initializeData' ist nicht deklariert." Diese Warnung wird angezeigt, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener>überprüft werden, die das `initializeData` Attribut nicht erkennt. In der Regel können Sie diese Warnung für Ablaufverfolgungslistenerimplementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt.  
  
 Die folgende Tabelle zeigt die Ablaufverfolgungslistener, die in `initializeData` .NET Framework enthalten sind, und beschreibt den Wert ihrer Attribute.  
  
|Ablaufverfolgungs-Listenerklasse|initializeData-Attributwert|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|Der `useErrorStream` Wert <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> für den Konstruktor.  Legen `initializeData` Sie das`true`Attribut auf " fest, um die Ablaufverfolgung sende- und Debugausgabe in den Standardfehlerstream zu schreiben. setzen Sie`false`es auf " , um in den Standardausgabestream zu schreiben.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Der Name einer vorhandenen Ereignisprotokollquelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die die <xref:System.Diagnostics.EventSchemaTraceListener> Datei schreibt.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die die <xref:System.Diagnostics.TextWriterTraceListener> Datei schreibt.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Der Name der Datei, in die die <xref:System.Diagnostics.XmlWriterTraceListener> Datei schreibt.|  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie <xref:System.Diagnostics.TextWriterTraceListener> `textListener` Elemente `sharedListeners` zum Hinzufügen der Elemente zur Auflistung verwendet `<add>` werden.   `textListener`wird der `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`nach Namen hinzugefügt. Der `textListener` Listener schreibt die Ablaufverfolgungsausgabe in die Datei myListener.log.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [Ablaufverfolgungs- und Debugeinstellungsschema](index.md)
- [Ablaufverfolgungslistener](../../../debug-trace-profile/trace-listeners.md)
