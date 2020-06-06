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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153606"
---
# <a name="add-element-for-sharedlisteners"></a>\<add>-Element für \<sharedListeners>
Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu. `sharedListeners`eine Auflistung von Listenern, auf die Any [\<source>](source-element.md) oder [\<trace>](trace-element.md) verweisen kann.  Standardmäßig werden Listener in der Auflistung `sharedListeners` nicht in eine Auflistung eingefügt `Listeners` . Sie müssen mit dem Namen zu oder hinzugefügt werden [\<source>](source-element.md) [\<trace>](trace-element.md) . Es ist nicht möglich, die Listener in der Auflistung `sharedListeners` zur Laufzeit im Code zu erhalten.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

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
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`name`|Erforderliches Attribut.<br /><br /> Gibt den Namen des Listener an, der verwendet wird, um den freigegebenen Listener einer Auflistung hinzuzufügen `Listeners` .|  
|`type`|Erforderliches Attribut.<br /><br /> Gibt den Typ des Listener an. Sie müssen eine Zeichenfolge verwenden, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.|  
|`initializeData`|Optionales Attribut.<br /><br /> Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wird.|  
|`traceOutputOptions`|Optionales Attribut.<br/><br/>Die Zeichen folgen Darstellung eines oder mehrerer <xref:System.Diagnostics.TraceOptions> Enumerationsmember, die die Daten angibt, die in die Ablauf Verfolgungs Ausgabe geschrieben werden sollen. Mehrere Elemente werden durch Kommas getrennt. Der Standardwert ist "None".|

### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sharedListeners`|Eine Auflistung von Listenern, auf die beliebige Quell-oder Ablauf Verfolgungs Elemente verweisen können.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die Listenerklassen, die mit dem .NET Framework ausgeliefert werden, werden von der- <xref:System.Diagnostics.TraceListener> Klasse abgeleitet Der Wert für das- `name` Attribut wird verwendet, um den freigegebenen Listener einer Auflistung `Listeners` entweder für eine Ablauf Verfolgung oder eine Ablauf Verfolgungs Quelle hinzuzufügen. Der Wert für das-Attribut ist abhängig vom `initializeData` Typ des von Ihnen erstellten Listener. Nicht alle Ablaufverfolgungslistener erfordern, dass `initializeData` Sie angeben  
  
> [!NOTE]
> Wenn Sie das- `initializeData` Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung, dass das initializeData-Attribut nicht deklariert ist. Diese Warnung tritt auf, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse überprüft werden <xref:System.Diagnostics.TraceListener> , die das- `initializeData` Attribut nicht erkennt. Normalerweise können Sie diese Warnung für Ablaufverfolgungslistener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt  
  
 In der folgenden Tabelle werden die Ablaufverfolgungslistener angezeigt, die im .NET Framework enthalten sind, und der Wert ihrer Attribute wird beschrieben `initializeData` .  
  
|Trace-Listenerklasse|initializeData-Attribut Wert|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|Der `useErrorStream` Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.  Legen `initializeData` Sie das-Attribut auf "" fest, um die Ablauf `true` Verfolgung und Debugausgabe in den Standardfehlerstream zu schreiben. Legen Sie Sie auf " `false` " fest|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Der Name einer vorhandenen Ereignisprotokollquelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die <xref:System.Diagnostics.EventSchemaTraceListener> geschrieben wird.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die <xref:System.Diagnostics.TextWriterTraceListener> geschrieben wird.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Der Name der Datei, in die <xref:System.Diagnostics.XmlWriterTraceListener> geschrieben wird.|  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie-Elemente verwendet werden, `<add>` um der-Auflistung hinzuzufügen <xref:System.Diagnostics.TextWriterTraceListener> `textListener` `sharedListeners` .   `textListener`wird der-Auflistung `Listeners` für die Ablauf Verfolgungs Quelle nach Name hinzugefügt `TraceSourceApp` . Der `textListener` Listener schreibt die Ablauf Verfolgungs Ausgabe in die Datei "MyListener. log".  
  
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
- [Schema für Ablaufverfolgungs- und Debugeinstellungen](index.md)
- [Ablaufverfolgungslistener](../../../debug-trace-profile/trace-listeners.md)
