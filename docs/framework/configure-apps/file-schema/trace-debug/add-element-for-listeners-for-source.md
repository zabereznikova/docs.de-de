---
title: <add>Element <listeners> für für<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 883eef32172c5a7f900197995b4c57c3d5a84e19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153684"
---
# <a name="add-element-for-listeners-for-source"></a>\<Hinzufügen> \<Elements für \<Listener> für>
Fügt einen Listener zu der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<Quellen>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Quelle>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Hörer>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**

## <a name="syntax"></a>Syntax  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`type`|Erforderliches Attribut, es sei denn, Sie `sharedListeners` verweisen auf einen Listener in der Auflistung, in diesem Fall müssen Sie nur mit dem Namen darauf verweisen (siehe [Beispiel](#example)).<br /><br /> Gibt den Typ des Listeners an. Sie müssen eine Zeichenfolge verwenden, die die unter [Angeben von vollqualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen erfüllt.|  
|`initializeData`|Optionales Attribut.<br /><br /> Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wurde. A <xref:System.Configuration.ConfigurationException> wird ausgelöst, wenn die Klasse keinen Konstruktor hat, der eine Zeichenfolge annimmt.|  
|`name`|Optionales Attribut.<br /><br /> Gibt den Namen des Listeners an.|  
|`traceOutputOptions`|Optionales Attribut.<br /><br /> Gibt den <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> Eigenschaftswert für den Ablaufverfolgungslistener an.|  
|[benutzerdefinierte Attribute]|Optionale Attribute.<br /><br /> Gibt den Wert für Listener-spezifische Attribute <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> an, die von der Methode für diesen Listener identifiziert werden. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>ist ein Beispiel für ein <xref:System.Diagnostics.DelimitedListTraceListener> zusätzliches Attribut, das für die Klasse eindeutig ist.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Filter>](filter-element-for-add-for-listeners-for-source.md)|Fügt einen Filter zu einem Listener in der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sources`|Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.|  
|`source`|Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.|  
|`listeners`|Gibt Listener an, die Nachrichten sammeln, speichern und weiterleiten.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die Listenerklassen, die mit .NET Framework <xref:System.Diagnostics.TraceListener> ausgeliefert wurden, leiten sich von der Klasse ab.  
  
 Wenn Sie das `name` Attribut des Ablaufverfolgungslisteners nicht angeben, wird die <xref:System.Diagnostics.TraceListener.Name%2A> Eigenschaft des Ablaufverfolgungslisteners standardmäßig auf eine leere Zeichenfolge ("") festgelegt. Wenn Ihre Anwendung nur über einen Listener verfügt, können Sie sie hinzufügen, ohne einen Namen anzugeben, und Sie können ihn entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben. Wenn Ihre Anwendung jedoch über mehr als einen Listener verfügt, sollten Sie für jeden Ablaufverfolgungslistener <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> einen eindeutigen Namen angeben, mit dem Sie einzelne Ablaufverfolgungslistener in der Auflistung identifizieren und verwalten können.  
  
> [!NOTE]
> Das Hinzufügen von mehr als einem Ablaufverfolgungslistener desselben Typs und mit demselben Namen führt `Listeners` dazu, dass der Auflistung nur ein Ablaufverfolgungslistener dieses Typs und namens hinzugefügt wird. Sie können der `Listeners` Auflistung jedoch programmgesteuert mehrere identische Listener hinzufügen.  
  
 Der Wert `initializeData` für das Attribut hängt vom Typ des Listeners ab, den Sie erstellen. Nicht alle Ablaufverfolgungslistener erfordern, dass Sie angeben. `initializeData`  
  
> [!NOTE]
> Wenn Sie `initializeData` das Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung "Das Attribut 'initializeData' ist nicht deklariert." Diese Warnung wird angezeigt, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener>überprüft werden, die das `initializeData` Attribut nicht erkennt. In der Regel können Sie diese Warnung für Ablaufverfolgungslistenerimplementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt.  
  
 Die folgende Tabelle zeigt die Ablaufverfolgungslistener, die in `initializeData` .NET Framework enthalten sind, und beschreibt den Wert ihrer Attribute.  
  
|Ablaufverfolgungs-Listenerklasse|initializeData-Attributwert|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Der `useErrorStream` Wert <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> für den Konstruktor.  Legen `initializeData` Sie das`true`Attribut auf " fest, um die Ablaufverfolgung sende- und Debugausgabe in den Standardfehlerstream zu schreiben. setzen Sie`false`es auf " , um in den Standardausgabestream zu schreiben.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Der Name einer vorhandenen Ereignisprotokollquelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die die <xref:System.Diagnostics.EventSchemaTraceListener> Datei schreibt.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die die <xref:System.Diagnostics.TextWriterTraceListener> Datei schreibt.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die die <xref:System.Diagnostics.XmlWriterTraceListener> Datei schreibt.|  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Elemente `console` `textListener` zum Hinzufügen der Listener und zur `Listeners` Auflistung für die Ablaufverfolgungsquelle `TraceSourceApp`verwendet `<add>` werden. Der `textListener` Listener schreibt die Ablaufverfolgungsausgabe in die Datei myListener.log.  
  
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
