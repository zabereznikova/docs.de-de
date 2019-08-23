---
title: <add>-Element <listeners> für für<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: d4ff919991ab1505b2845a225706d32cc1e57d0a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920570"
---
# <a name="add-element-for-listeners-for-trace"></a>\<Fügen Sie > Element \<für Listener > \<für die Ablauf Verfolgung hinzu >
Fügt der listenerauflistung einen Listener hinzu.  
  
 \<configuration>  
\<system.diagnostics>  
\<Ablauf Verfolgungs >  
\<Listener >  
\<add>  
  
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
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|Fügt einen Filter zu einem Listener in der `Listeners` -Auflistung für eine Ablauf Verfolgung hinzu.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`listeners`|Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet. Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.|  
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|  
|`trace`|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
## <a name="remarks"></a>Hinweise  
 Die <xref:System.Diagnostics.Debug> - <xref:System.Diagnostics.Trace> Klasse und die- Klasse verwenden dieselbe Listener-Auflistung. Wenn Sie der Auflistung in einer dieser Klassen ein Listenerobjekt hinzufügen, verwendet die andere Klasse denselben Listener. Die Listenerklassen werden von <xref:System.Diagnostics.TraceListener>abgeleitet.  
  
 Wenn Sie das `name` -Attribut des Ablaufverfolgungslistener <xref:System.Diagnostics.TraceListener.Name%2A> nicht angeben, wird für den Ablaufverfolgungslistener standardmäßig eine leere Zeichenfolge ("") Wenn die Anwendung nur über einen Listener verfügt, können Sie Sie ohne Angabe eines Namens hinzufügen und entfernen, indem Sie eine leere Zeichenfolge für den Namen angeben. Wenn Ihre Anwendung jedoch über mehr als einen Listener verfügt, sollten Sie eindeutige Namen für jeden Ablaufverfolgungslistener angeben, sodass Sie einzelne Ablaufverfolgungslistener innerhalb der <xref:System.Diagnostics.Debug.Listeners%2A> -und- <xref:System.Diagnostics.Trace.Listeners%2A> Auflistung identifizieren und verwalten können.  
  
> [!NOTE]
> Das Hinzufügen von mehr als einem Ablaufverfolgungslistener desselben Typs und desselben Namens führt dazu, dass nur ein Ablaufverfolgungslistener dieses Typs und namens zur `Listeners` Auflistung hinzugefügt wird. Allerdings können Sie der `Listeners` Auflistung Programm gesteuert mehrere identische Listener hinzufügen.  
  
 Der Wert für das **initializeData** -Attribut hängt vom Typ des von Ihnen erstellten Listener ab. Nicht alle Ablaufverfolgungslistener erfordern, dass Sie **initializeData**angeben.  
  
> [!NOTE]
> Wenn Sie das `initializeData` -Attribut verwenden, erhalten Sie möglicherweise die Compilerwarnung, dass das initializeData-Attribut nicht deklariert ist. Diese Warnung tritt auf, weil die Konfigurationseinstellungen anhand der abstrakten Basisklasse <xref:System.Diagnostics.TraceListener>überprüft werden, die das `initializeData` -Attribut nicht erkennt. Normalerweise können Sie diese Warnung für Ablaufverfolgungslistener-Implementierungen ignorieren, die über einen Konstruktor verfügen, der einen Parameter annimmt  
  
 In der folgenden Tabelle werden die Ablaufverfolgungslistener angezeigt, die im .NET Framework enthalten sind, und der Wert Ihrer **initializeData** -Attribute wird beschrieben.  
  
|Trace-Listenerklasse|initializeData-Attribut Wert|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Der `useErrorStream` Wert für den <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Konstruktor.  Legen Sie `initializeData` das-Attribut`true`auf "" fest, um die Ablauf <xref:System.Console.Error%2A?displayProperty=nameWithType>Verfolgung und Debugausgabe in "`false`", in die <xref:System.Console.Out%2A?displayProperty=nameWithType>geschrieben werden soll.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Der Name der Datei, in <xref:System.Diagnostics.DelimitedListTraceListener> die geschrieben wird.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Der Name des Namens einer vorhandenen Ereignisprotokoll Quelle.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die <xref:System.Diagnostics.EventSchemaTraceListener> geschrieben wird.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die <xref:System.Diagnostics.TextWriterTraceListener> geschrieben wird.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Der Name der Datei, in die <xref:System.Diagnostics.XmlWriterTraceListener> geschrieben wird.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie  **\<Sie > Elementen hinzufügen** verwenden `MyListener` , um `MyEventListener` die Listener und der Listener-Auflistung hinzuzufügen. `MyListener`erstellt eine Datei mit `MyListener.log` dem Namen und schreibt die Ausgabe in die Datei. `MyEventListener`erstellt einen Eintrag im Ereignisprotokoll.  
  
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
