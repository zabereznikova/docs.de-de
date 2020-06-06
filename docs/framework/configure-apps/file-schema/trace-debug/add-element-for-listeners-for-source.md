---
title: <add>-Element für <listeners> für<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 883eef32172c5a7f900197995b4c57c3d5a84e19
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153684"
---
# <a name="add-element-for-listeners-for-source"></a>\<add>-Element für \<listeners> für\<source>
Fügt einen Listener zu der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a>Syntax  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`type`|Erforderliches Attribut, es sei denn, Sie verweisen in der Auflistung auf einen Listener `sharedListeners` . in diesem Fall müssen Sie nur anhand des Namens darauf verweisen (siehe [Beispiel](#example)).<br /><br /> Gibt den Typ des Listener an. Sie müssen eine Zeichenfolge verwenden, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.|  
|`initializeData`|Optionales Attribut.<br /><br /> Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wird. Eine <xref:System.Configuration.ConfigurationException> wird ausgelöst, wenn die Klasse über keinen Konstruktor verfügt, der eine Zeichenfolge annimmt.|  
|`name`|Optionales Attribut.<br /><br /> Gibt den Namen des Listener an.|  
|`traceOutputOptions`|Optionales Attribut.<br /><br /> Gibt den <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> Eigenschafts Wert für den Ablaufverfolgungslistener an.|  
|[benutzerdefinierte Attribute]|Optionale Attribute.<br /><br /> Gibt den Wert für listenerspezifische Attribute an, die von der- <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> Methode für diesen Listener identifiziert werden. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>ist ein Beispiel für ein zusätzliches Attribut, das für die-Klasse eindeutig ist <xref:System.Diagnostics.DelimitedListTraceListener> .|  
  
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
  
## <a name="remarks"></a>Bemerkungen  
 Die Listenerklassen, die mit dem .NET Framework ausgeliefert werden, werden von der- <xref:System.Diagnostics.TraceListener> Klasse abgeleitet  
  
 Wenn Sie das-Attribut des Ablaufverfolgungslistener nicht angeben `name` , wird <xref:System.Diagnostics.TraceListener.Name%2A> standardmäßig eine leere Zeichenfolge ("") für die-Eigenschaft des Ablaufverfolgungslistener verwendet Wenn die Anwendung nur über einen Listener verfügt, können Sie Sie hinzufügen, ohne einen Namen anzugeben, und Sie können Sie entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben. Wenn Ihre Anwendung jedoch über mehr als einen Listener verfügt, sollten Sie einen eindeutigen Namen für jeden Ablaufverfolgungslistener angeben, mit dem Sie einzelne Ablaufverfolgungslistener in der Sammlung identifizieren und verwalten können <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> .  
  
> [!NOTE]
> Das Hinzufügen von mehr als einem Ablaufverfolgungslistener desselben Typs und desselben Namens führt dazu, dass nur ein Ablaufverfolgungslistener dieses Typs und namens zur Auflistung hinzugefügt wird `Listeners` . Allerdings können Sie der Auflistung Programm gesteuert mehrere identische Listener hinzufügen `Listeners` .  
  
 Der Wert für das-Attribut ist abhängig vom `initializeData` Typ des von Ihnen erstellten Listener. Nicht alle Ablaufverfolgungslistener erfordern, dass `initializeData` Sie angeben  
  
> [!NOTE]
> Wenn Sie das- `initializeData` Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung, dass das initializeData-Attribut nicht deklariert ist. Diese Warnung tritt auf, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse überprüft werden <xref:System.Diagnostics.TraceListener> , die das- `initializeData` Attribut nicht erkennt. Normalerweise können Sie diese Warnung für Ablaufverfolgungslistener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt  
  
 In der folgenden Tabelle werden die Ablaufverfolgungslistener angezeigt, die im .NET Framework enthalten sind, und der Wert ihrer Attribute wird beschrieben `initializeData` .  
  
|Trace-Listenerklasse|initializeData-Attribut Wert|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Der `useErrorStream` Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.  Legen `initializeData` Sie das-Attribut auf "" fest, um die Ablauf `true` Verfolgung und Debugausgabe in den Standardfehlerstream zu schreiben. Legen Sie Sie auf " `false` " fest|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Der Name einer vorhandenen Ereignisprotokollquelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die <xref:System.Diagnostics.EventSchemaTraceListener> geschrieben wird.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die <xref:System.Diagnostics.TextWriterTraceListener> geschrieben wird.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die <xref:System.Diagnostics.XmlWriterTraceListener> geschrieben wird.|  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Elemente verwendet werden, `<add>` um die Listener `console` und der-Auflistung `textListener` `Listeners` für die Ablauf Verfolgungs Quelle hinzuzufügen `TraceSourceApp` . Der `textListener` Listener schreibt die Ablauf Verfolgungs Ausgabe in die Datei "MyListener. log".  
  
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
