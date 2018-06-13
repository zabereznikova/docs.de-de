---
title: '&lt;Trace&gt; Element'
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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 59d5083632630513d2afc1f8d78400310451e46f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746058"
---
# <a name="lttracegt-element"></a>&lt;Trace&gt; Element
Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.  
  
 \<configuration>  
\<System.Diagnostics >  
\<Trace >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`autoflush`|Optionales Attribut.<br /><br /> Gibt an, ob der Ablaufverfolgungslistener den Ausgabepuffer nach jedem Schreibvorgang automatisch geleert.|  
|`indentsize`|Optionales Attribut.<br /><br /> Gibt die Anzahl der Leerzeichen für den Einzug an.|  
|`useGlobalLock`|Optionales Attribut.<br /><br /> Gibt an, ob die globale Sperre verwendet werden soll.|  
  
## <a name="autoflush-attribute"></a>AutoFlush-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Der Ausgabepuffer nicht automatisch geleert. Dies ist die Standardeinstellung.|  
|`true`|Automatisch leert den Ausgabepuffer.|  
  
## <a name="usegloballock-attribute"></a>UseGlobalLock-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Die globale Sperre wird nicht verwendet werden, wenn der Listener threadsicher ist. Andernfalls wird die globale Sperre verwendet.|  
|`true`|Verwendet die globale Sperre unabhängig davon, ob der Listener threadsicher ist. Dies ist die Standardeinstellung.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Gibt an, einen Listener, der erfasst hat, speichert, und leitet Nachrichten.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die `<trace>` Element an den Listener hinzufügen `MyListener` auf die `Listeners` Auflistung. `MyListener` erstellt eine Datei mit dem Namen `MyListener.log` und schreibt die Ausgabe in die Datei. Die `useGlobalLock` -Attributsatz zur `false`, wodurch die globale Sperre nicht verwendet werden, wenn der Ablaufverfolgungslistener threadsicher ist. Die `autoflush` -Attributsatz zur `true`, dies bedeutet, dass den Ablaufverfolgungslistener zum Schreiben in die Datei, unabhängig davon, ob die <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> -Methode aufgerufen wird. Die `indentsize` -Attribut festgelegt ist, auf 0 (null), wodurch den Listener 0 Leerzeichen Einzug beim die <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> Methode wird aufgerufen.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
