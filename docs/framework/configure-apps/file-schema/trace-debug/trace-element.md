---
title: <trace>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: 7d8a989219d84e8604e767456c84c0092bc73b22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153165"
---
# <a name="trace-element"></a>\<Ablaufverfolgung> Element
Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.  
  
[**\<Konfiguration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<Spur>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`autoflush`|Optionales Attribut.<br /><br /> Gibt an, ob die Ablaufverfolgungslistener den Ausgabepuffer nach jedem Schreibvorgang automatisch leeren.|  
|`indentsize`|Optionales Attribut.<br /><br /> Gibt die Anzahl der einrückenden Leerzeichen an.|  
|`useGlobalLock`|Optionales Attribut.<br /><br /> Gibt an, ob die globale Sperre verwendet werden soll.|  
  
## <a name="autoflush-attribute"></a>autoflush-Attribut  
  
|value|Beschreibung|  
|-----------|-----------------|  
|`false`|Spült den Ausgabepuffer nicht automatisch. Dies ist die Standardoption.|  
|`true`|Spült den Ausgabepuffer automatisch.|  
  
## <a name="usegloballock-attribute"></a>VerwendenDesGlobalLock-Attribut  
  
|value|Beschreibung|  
|-----------|-----------------|  
|`false`|Verwendet die globale Sperre nicht, wenn der Listener threadsicher ist. Andernfalls wird die globale Sperre verwendet.|  
|`true`|Verwendet die globale Sperre unabhängig davon, ob der Listener threadsicher ist. Dies ist die Standardoption.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Hörer>](listeners-element-for-trace.md)|Gibt einen Listener an, der Nachrichten sammelt, speichert und leitet.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, `<trace>` wie sie das `MyListener` Element `Listeners` zum Hinzufügen des Listeners zur Auflistung verwenden. `MyListener`erstellt eine Datei `MyListener.log` mit dem Namen und schreibt die Ausgabe in die Datei. Das `useGlobalLock` Attribut ist `false`auf festgelegt, wodurch die globale Sperre nicht verwendet wird, wenn der Ablaufverfolgungslistener threadsicher ist. Das `autoflush` Attribut ist `true`auf festgelegt, wodurch der Ablaufverfolgungslistener <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> unabhängig davon, ob die Methode aufgerufen wird, in die Datei geschrieben wird. Das `indentsize` Attribut wird auf 0 (Null) gesetzt, wodurch der <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> Listener beim Aufruf der Methode Leerzeichen einrücken lässt.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [Ablaufverfolgungs- und Debugeinstellungsschema](index.md)
