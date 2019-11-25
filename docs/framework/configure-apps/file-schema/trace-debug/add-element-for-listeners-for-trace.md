---
title: <add> Element für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: eb3e9cf4a6d138998cfde865cda8ed4146be26d0
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088983"
---
# <a name="add-element-for-listeners-for-trace"></a>\<> Element für \<Listener > für \<Ablauf Verfolgung hinzufügen >
Fügt der **listenerauflistung** einen Listener hinzu.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Ablauf Verfolgungs**](trace-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;[ **&nbsp;&nbsp;\<Listener >\** ](listeners-element-for-trace.md)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<hinzufügen >**

## <a name="syntax"></a>Syntax  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**Typ**|Erforderliches Attribut.<br /><br /> Gibt den Typ des Listener an. Sie müssen eine Zeichenfolge verwenden, die den unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)angegebenen Anforderungen entspricht.|  
|**initializeData**|Optionales Attribut.<br /><br /> Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wird.|  
|**name**|Optionales Attribut.<br /><br /> Gibt den Namen des Listener an.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|Fügt einen Filter zu einem Listener in der `Listeners`-Auflistung für eine Ablauf Verfolgung hinzu.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`listeners`|Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet. Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.|  
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|  
|`trace`|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
## <a name="remarks"></a>Hinweise  
 Die Klassen <xref:System.Diagnostics.Debug> und <xref:System.Diagnostics.Trace> **verwenden dieselbe Listener** -Auflistung. Wenn Sie der Auflistung in einer dieser Klassen ein Listenerobjekt hinzufügen, verwendet die andere Klasse denselben Listener. Die Listenerklassen werden vom <xref:System.Diagnostics.TraceListener>abgeleitet.  
  
 Wenn Sie das `name`-Attribut des Ablaufverfolgungslistener nicht angeben, wird der <xref:System.Diagnostics.TraceListener.Name%2A> des Ablaufverfolgungslistener standardmäßig auf eine leere Zeichenfolge ("") Wenn die Anwendung nur über einen Listener verfügt, können Sie Sie ohne Angabe eines Namens hinzufügen und entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben. Wenn Ihre Anwendung jedoch über mehr als einen Listener verfügt, sollten Sie eindeutige Namen für jeden Ablaufverfolgungslistener angeben, sodass Sie einzelne Ablaufverfolgungslistener in den <xref:System.Diagnostics.Debug.Listeners%2A>-und <xref:System.Diagnostics.Trace.Listeners%2A> Sammlungen identifizieren und verwalten können.  
  
> [!NOTE]
> Das Hinzufügen von mehr als einem Ablaufverfolgungslistener desselben Typs und desselben Namens führt dazu, dass nur ein Ablaufverfolgungslistener dieses Typs und namens zur `Listeners` Auflistung hinzugefügt wird. Allerdings können Sie der `Listeners` Auflistung Programm gesteuert mehrere identische Listener hinzufügen.  
  
 Der Wert für das **initializeData** -Attribut hängt vom Typ des von Ihnen erstellten Listener ab. Nicht alle Ablaufverfolgungslistener erfordern, dass Sie **initializeData**angeben.  
  
> [!NOTE]
> Wenn Sie das `initializeData`-Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung, dass das initializeData-Attribut nicht deklariert ist. Diese Warnung tritt auf, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener>überprüft werden, die das `initializeData`-Attribut nicht erkennt. Normalerweise können Sie diese Warnung für Ablaufverfolgungslistener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt  
  
 In der folgenden Tabelle werden die Ablaufverfolgungslistener angezeigt, die im .NET Framework enthalten sind, und der Wert Ihrer **initializeData** -Attribute wird beschrieben.  
  
|Trace-Listenerklasse|initializeData-Attribut Wert|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Der `useErrorStream` Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>-Konstruktor.  Legen Sie das `initializeData`-Attribut auf "`true`" fest, um die Ablaufverfolgungs-und Debugausgabe in <xref:System.Console.Error%2A?displayProperty=nameWithType>zu schreiben; "`false`", um in <xref:System.Console.Out%2A?displayProperty=nameWithType>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die der <xref:System.Diagnostics.DelimitedListTraceListener> schreibt.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Der Name des Namens einer vorhandenen Ereignisprotokoll Quelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die der <xref:System.Diagnostics.EventSchemaTraceListener> schreibt.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die der <xref:System.Diagnostics.TextWriterTraceListener> schreibt.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die der <xref:System.Diagnostics.XmlWriterTraceListener> schreibt.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie **\<Hinzufügen von >** Elementen zum hinzu **fügen der Listener** `MyListener` und `MyEventListener` zur Listener-Auflistung verwendet wird. `MyListener` erstellt eine Datei mit dem Namen `MyListener.log` und schreibt die Ausgabe in die Datei. `MyEventListener` erstellt einen Eintrag im Ereignisprotokoll.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](index.md)
- [Trace Listeners (Ablaufverfolgungslistener)](../../../debug-trace-profile/trace-listeners.md)
