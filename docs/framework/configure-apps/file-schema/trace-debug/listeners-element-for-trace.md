---
title: <listeners>-Element für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: e4550d4c4cd9ff37c5937ad366cccf91387c0e3f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927022"
---
# <a name="listeners-element-for-trace"></a>\<Listener > Element für \<die Ablauf Verfolgungs >
Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet. Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.  
  
 \<Configuration >-Element  
\<System. Diagnostics >-Element  
\<Trace > Element  
\<Listener > Element für \<die Ablauf Verfolgungs >  
  
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
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|Fügt einen Listener zu der `Listeners`-Sammlung hinzu.|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|Entfernt einen Listener aus der `Listeners` Auflistung.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|  
|`trace`|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
## <a name="remarks"></a>Hinweise  
 Die <xref:System.Diagnostics.Debug> - <xref:System.Diagnostics.Trace> Klasse und die- Klasse verwenden dieselbe Listener-Auflistung. Wenn Sie der Auflistung in einer dieser Klassen ein Listenerobjekt hinzufügen, verwendet die andere Klasse denselben Listener. Die Listenerklassen, die mit dem .NET Framework ausgeliefert <xref:System.Diagnostics.TraceListener> werden, werden von der-Klasse abgeleitet  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das  **\<Listener >** `MyListener` -Element verwendet wird, um `MyEventListener` die Listener und der Listener-Auflistung hinzuzufügen. `MyListener`erstellt eine Datei mit `MyListener.log` dem Namen und schreibt die Ausgabe in die Datei. `MyEventListener`erstellt einen Eintrag im Ereignisprotokoll.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.TraceListener>
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](index.md)
