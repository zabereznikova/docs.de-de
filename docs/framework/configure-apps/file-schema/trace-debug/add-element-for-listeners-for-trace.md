---
title: <add>Element <listeners> für für<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: c64673908dc9afe67d97c08f93e5b9d9533bd34d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153671"
---
# <a name="add-element-for-listeners-for-trace"></a>\<Hinzufügen von \<> Element \<für Listener> für Ablaufverfolgungs->
Fügt der **Listeners-Auflistung** einen Listener hinzu.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<Spur>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Hörer>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**

## <a name="syntax"></a>Syntax  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|**Typ**|Erforderliches Attribut.<br /><br /> Gibt den Typ des Listeners an. Sie müssen eine Zeichenfolge verwenden, die die unter [Angeben von vollqualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen erfüllt.|  
|**Initializedata**|Optionales Attribut.<br /><br /> Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wurde.|  
|**Name**|Optionales Attribut.<br /><br /> Gibt den Namen des Listeners an.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Filter>](filter-element-for-add-for-listeners-for-trace.md)|Fügt einem Listener in `Listeners` der Auflistung einen Filter für eine Ablaufverfolgung hinzu.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`listeners`|Gibt einen Listener an, der Nachrichten sammelt, speichert und leitet. Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel weiter.|  
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|  
|`trace`|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace> und die Klassen verwenden dieselbe **Listeners-Auflistung.** Wenn Sie der Auflistung in einer dieser Klassen ein Listenerobjekt hinzufügen, verwendet die andere Klasse denselben Listener. Die Listenerklassen leiten <xref:System.Diagnostics.TraceListener>sich von der ab.  
  
 Wenn Sie das `name` Attribut des Ablaufverfolgungslisteners nicht angeben, wird der <xref:System.Diagnostics.TraceListener.Name%2A> Ablaufverfolgungslistener standardmäßig auf eine leere Zeichenfolge ("") festgelegt. Wenn Ihre Anwendung nur über einen Listener verfügt, können Sie sie hinzufügen, ohne einen Namen anzugeben, und sie entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben. Wenn Ihre Anwendung jedoch über mehr als einen Listener verfügt, sollten Sie eindeutige Namen für jeden <xref:System.Diagnostics.Debug.Listeners%2A> Ablaufverfolgungslistener angeben, mit dem Sie einzelne Ablaufverfolgungslistener innerhalb der und <xref:System.Diagnostics.Trace.Listeners%2A> der Sammlungen identifizieren und verwalten können.  
  
> [!NOTE]
> Das Hinzufügen von mehr als einem Ablaufverfolgungslistener desselben Typs und mit demselben Namen führt `Listeners` dazu, dass der Auflistung nur ein Ablaufverfolgungslistener dieses Typs und namens hinzugefügt wird. Sie können der `Listeners` Auflistung jedoch programmgesteuert mehrere identische Listener hinzufügen.  
  
 Der Wert für das **initializeData-Attribut** hängt vom Typ des Listeners ab, den Sie erstellen. Nicht alle Ablaufverfolgungslistener erfordern, dass Sie **initializeData**angeben.  
  
> [!NOTE]
> Wenn Sie `initializeData` das Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung "Das Attribut 'initializeData' ist nicht deklariert." Diese Warnung wird angezeigt, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener>überprüft werden, die das `initializeData` Attribut nicht erkennt. In der Regel können Sie diese Warnung für Ablaufverfolgungslistenerimplementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt.  
  
 Die folgende Tabelle zeigt die Ablaufverfolgungslistener, die in .NET Framework enthalten sind, und beschreibt den Wert ihrer **initializeData-Attribute.**  
  
|Ablaufverfolgungs-Listenerklasse|initializeData-Attributwert|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Der `useErrorStream` Wert <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> für den Konstruktor.  Legen `initializeData` Sie das`true`Attribut auf " fest, um die Ablaufverfolgung zu schreiben und die Ausgabe auf zu <xref:System.Console.Error%2A?displayProperty=nameWithType>debuggen. "`false`", um <xref:System.Console.Out%2A?displayProperty=nameWithType>an zu schreiben.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Der Name des Namens einer vorhandenen Ereignisprotokollquelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die die <xref:System.Diagnostics.EventSchemaTraceListener> Datei schreibt.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die die <xref:System.Diagnostics.TextWriterTraceListener> Datei schreibt.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die die <xref:System.Diagnostics.XmlWriterTraceListener> Datei schreibt.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie ** \<Sie>** `MyEventListener` Elemente zum Hinzufügen der Listener `MyListener` und zur **Listener-Auflistung** verwenden. `MyListener`erstellt eine `MyListener.log` aufgerufene Datei und schreibt die Ausgabe in die Datei. `MyEventListener`erstellt einen Eintrag im Ereignisprotokoll.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [Ablaufverfolgungs- und Debugeinstellungsschema](index.md)
- [Ablaufverfolgungslistener](../../../debug-trace-profile/trace-listeners.md)
