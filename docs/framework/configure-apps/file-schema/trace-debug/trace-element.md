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
ms.openlocfilehash: 617b42a0be2be272a78b33be997cce632d1c6dcb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198924"
---
# <a name="trace-element"></a>\<trace>-Element

Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`autoflush`|Optionales Attribut.<br /><br /> Gibt an, ob die Ablaufverfolgungslistener den Ausgabepuffer nach jedem Schreibvorgang automatisch leeren.|  
|`indentsize`|Optionales Attribut.<br /><br /> Gibt die Anzahl der Leerzeichen für den Einzug an.|  
|`useGlobalLock`|Optionales Attribut.<br /><br /> Gibt an, ob die globale Sperre verwendet werden soll.|  
  
## <a name="autoflush-attribute"></a>AutoFlush-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Der Ausgabepuffer wird nicht automatisch geleert. Dies ist die Standardeinstellung.|  
|`true`|Leert den Ausgabepuffer automatisch.|  
  
## <a name="usegloballock-attribute"></a>UseGlobalLock-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Verwendet nicht die globale Sperre, wenn der Listener Thread sicher ist. Andernfalls verwendet die globale Sperre.|  
|`true`|Verwendet die globale Sperre, unabhängig davon, ob der Listener Thread sicher ist. Dies ist die Standardeinstellung.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-trace.md)|Gibt einen Listener an, der Nachrichten sammelt, speichert und weiterleitet.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie das-Element verwendet wird, `<trace>` um den Listener der Auflistung hinzuzufügen `MyListener` `Listeners` . `MyListener` erstellt eine Datei `MyListener.log` mit dem Namen und schreibt die Ausgabe in die Datei. Das- `useGlobalLock` Attribut ist auf festgelegt `false` . Dies bewirkt, dass die globale Sperre nicht verwendet wird, wenn der Ablaufverfolgungslistener Thread sicher ist. Das- `autoflush` Attribut ist auf festgelegt `true` , wodurch der Ablaufverfolgungslistener in die Datei schreibt, unabhängig davon, ob die- <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> Methode aufgerufen wird. Das- `indentsize` Attribut wird auf 0 (null) festgelegt, was bewirkt, dass der Listener beim Aufrufen der-Methode NULL-Leerzeichen <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> eingibt.  
  
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
- [Schema für Ablaufverfolgungs- und Debugeinstellungen](index.md)
