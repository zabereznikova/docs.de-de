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
ms.openlocfilehash: 116a9633d16b8dd36c82f07a8e727f6f9f98f0ee
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088965"
---
# <a name="add-element-for-sharedlisteners"></a>\<> Element für \<sharedlistener hinzufügen >
Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu. `sharedListeners` ist eine Sammlung von Listenern, auf die alle [\<Quell >](source-element.md) oder [\<Ablauf Verfolgungs >](trace-element.md) verweisen können.  Standardmäßig werden Listener in der `sharedListeners` Sammlung nicht in einer `Listeners` Auflistung platziert. Sie müssen dem [\<Quell >](source-element.md) oder [\<Ablauf Verfolgungs >](trace-element.md)als Name hinzugefügt werden. Es ist nicht möglich, die Listener in der `sharedListeners`-Auflistung zur Laufzeit im Code zu erhalten.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sharedlistener >** ](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Hinzufügen >**

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
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`name`|Erforderliches Attribut.<br /><br /> Gibt den Namen des Listener an, der verwendet wird, um den freigegebenen Listener einer `Listeners` Auflistung hinzuzufügen.|  
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
  
## <a name="remarks"></a>Hinweise  
 Die Listenerklassen, die mit dem .NET Framework ausgeliefert werden, werden von der <xref:System.Diagnostics.TraceListener> Klasse abgeleitet. Der Wert für das `name`-Attribut wird verwendet, um den freigegebenen Listener einer `Listeners` Auflistung entweder für eine Ablauf Verfolgung oder eine Ablauf Verfolgungs Quelle hinzuzufügen. Der Wert für das `initializeData`-Attribut ist abhängig vom Typ des von Ihnen erstellten Listener. Nicht alle Ablaufverfolgungslistener erfordern, dass Sie `initializeData`angeben  
  
> [!NOTE]
> Wenn Sie das `initializeData`-Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung, dass das initializeData-Attribut nicht deklariert ist. Diese Warnung tritt auf, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener>überprüft werden, die das `initializeData`-Attribut nicht erkennt. Normalerweise können Sie diese Warnung für Ablaufverfolgungslistener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt  
  
 Die folgende Tabelle zeigt die Ablaufverfolgungslistener, die im .NET Framework enthalten sind, und beschreibt den Wert ihrer `initializeData` Attribute.  
  
|Trace-Listenerklasse|initializeData-Attribut Wert|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|Der `useErrorStream` Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>-Konstruktor.  Legen Sie das `initializeData`-Attribut auf "`true`" fest, um die Ablauf Verfolgung und Debugausgabe in den Standardfehlerstream zu schreiben Legen Sie Sie auf "`false`" fest, um in den Standardausgabestream zu schreiben|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Der Name einer vorhandenen Ereignisprotokoll Quelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die der <xref:System.Diagnostics.EventSchemaTraceListener> schreibt.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die der <xref:System.Diagnostics.TextWriterTraceListener> schreibt.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Der Name der Datei, in die der <xref:System.Diagnostics.XmlWriterTraceListener> schreibt.|  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie `<add>`-Elemente verwendet werden, um die <xref:System.Diagnostics.TextWriterTraceListener>`textListener` der `sharedListeners` Auflistung hinzuzufügen.   `textListener` wird der `Listeners` Auflistung für die `TraceSourceApp`der Ablauf Verfolgungs Quelle nach Name hinzugefügt. Der `textListener` Listener schreibt die Ablauf Verfolgungs Ausgabe in die Datei "MyListener. log".  
  
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
