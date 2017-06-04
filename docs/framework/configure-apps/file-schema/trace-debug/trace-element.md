---
title: "&lt;trace&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#trace"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<trace>-Element"
  - "Listener"
  - "trace-Element"
  - "Ablaufverfolgungslistener, <trace>-Element"
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;trace&gt;-Element
Enthält Listener, die Verfolgungsmeldungen sammeln, speichern und weiterleiten.  
  
## Syntax  
  
```  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`autoflush`|Optionales Attribut.<br /><br /> Gibt an, ob die Ablaufverfolgungslistener den Ausgabepuffer nach jedem Schreibvorgang automatisch löschen.|  
|`indentsize`|Optionales Attribut.<br /><br /> Gibt die Anzahl der Leerzeichen für den Einzug an.|  
|`useGlobalLock`|Optionales Attribut.<br /><br /> Gibt an, ob die globale Sperre verwendet werden soll.|  
  
## autoflush\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Der Ausgabepuffer wird nicht automatisch gelöscht.  Dies ist der Standardwert.|  
|`true`|Der Ausgabepuffer wird automatisch gelöscht.|  
  
## useGlobalLock\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Verwendet die globale Sperre nicht, wenn der Listener threadsicher ist; verwendet andernfalls die globale Sperre.|  
|`true`|Verwendet die globale Sperre unabhängig davon, ob der Listener threadsicher ist.  Dies ist der Standardwert.|  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<Überwachung\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Gibt einen Listener an, der Meldungen sammelt, speichert und weiterleitet.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie der `Listeners`\-Auflistung mithilfe des `<trace>`\-Elements der `MyListener`\-Listener hinzugefügt wird.  `MyListener` erstellt eine Datei mit der Bezeichnung `MyListener.log` und schreibt die Ausgabe in die Datei.  Das `useGlobalLock`\-Attribut wird auf `false` festgelegt, wodurch die globale Sperre nicht verwendet wird, wenn der Ablaufverfolgungslistener threadsicher ist.  Für das `autoflush`\-Attribut wird `true` festgelegt, wodurch der Ablaufverfolgungslistener unabhängig davon in die Datei schreibt, ob die <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=fullName>\-Methode aufgerufen wurde oder nicht.  Für das `indentsize`\-Attribut wird 0 \(null\) festgelegt, wodurch der Listener 0 Leerzeichen für den Einzug verwendet, wenn die <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=fullName>\-Methode aufgerufen wird.  
  
```  
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
  
## Siehe auch  
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.DefaultTraceListener>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)