---
title: <listeners>-Element für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: fd12be1b775d7611ef3f16d23147470313bf9866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153372"
---
# <a name="listeners-element-for-trace"></a>\<Listener> \<Element für>
Gibt einen Listener an, der Nachrichten sammelt, speichert und leitet. Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel weiter.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<Spur>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Hörer>**

## <a name="syntax"></a>Syntax  
  
```xml  
<listeners>
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<hinzufügen>](add-element-for-listeners-for-trace.md)|Fügt einen Listener zu der `Listeners`-Sammlung hinzu.|  
|[\<klare>](clear-element-for-listeners-for-trace.md)|Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.|  
|[\<entfernen sie>](remove-element-for-listeners-for-trace.md)|Entfernt einen Listener `Listeners` aus der Auflistung.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|  
|`trace`|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace> und die Klassen verwenden dieselbe **Listeners-Auflistung.** Wenn Sie der Auflistung in einer dieser Klassen ein Listenerobjekt hinzufügen, verwendet die andere Klasse denselben Listener. Die Listenerklassen, die mit .NET Framework <xref:System.Diagnostics.TraceListener> ausgeliefert wurden, leiten sich von der Klasse ab.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie die `MyListener` `MyEventListener` ** \<Listener>** Element verwendet werden, um die Listener und die **Listener-Auflistung** hinzuzufügen. `MyListener`erstellt eine `MyListener.log` aufgerufene Datei und schreibt die Ausgabe in die Datei. `MyEventListener`erstellt einen Eintrag im Ereignisprotokoll.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"
          type="System.Diagnostics.TextWriterTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Diagnostics.TraceListener>
- [Ablaufverfolgungs- und Debugeinstellungsschema](index.md)
