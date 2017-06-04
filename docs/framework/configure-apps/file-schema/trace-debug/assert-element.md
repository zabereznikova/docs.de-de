---
title: "&lt;assert&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#assert"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assert>-Element"
  - "assert-Element"
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &lt;assert&gt;-Element
Legt fest, ob ein Meldungsfeld angezeigt wird, wenn die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>\-Methode aufgerufen wird; gibt darüber hinaus den Namen der Datei an, in die Meldungen geschrieben werden.  
  
## Syntax  
  
```  
  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`assertuienabled`|Optionales Attribut.<br /><br /> Gibt an, ob ein Meldungsfeld angezeigt werden soll, wenn der Wert der **Debug.Assert**\-Methode **false** lautet.|  
|`logfilename`|Optionales Attribut.<br /><br /> Gibt den Namen der Datei an, in die die Meldung geschrieben wird, wenn für **Debug.Assert** der Wert **false** angegeben ist.|  
  
## assertuienabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`true`|Zeigt das Meldungsfeld an.  Dies ist der Standardwert.|  
|`false`|Zeigt das Meldungsfeld nicht an.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
  
## Hinweise  
 Beide Attribute im **\<assert\>**\-Element sind optional.  Meldungsfelder können deaktiviert werden, ohne eine Datei anzugeben, in der die Meldungen gespeichert werden. Sie können aber auch eine Datei angeben, in die Meldungen geschrieben werden, während die Meldungsfelder aktiviert bleiben.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie angezeigte Meldungsfelder deaktiviert werden, wenn Sie **Debug.Assert** aufrufen und die Meldungen in `c:\log.txt` schreiben.  
  
```  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Diagnostics.Debug>   
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)