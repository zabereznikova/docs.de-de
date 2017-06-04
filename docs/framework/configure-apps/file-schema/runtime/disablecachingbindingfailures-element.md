---
title: "&lt;disableCachingBindingFailures&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<disableCachingBindingFailures>-Element"
  - "Assemblys [.NET Framework], Zwischenspeichern von Bindungsfehlern"
  - "Zwischenspeichern von Assemblybindungsfehlern"
  - "disableCachingBindingFailures-Element"
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# &lt;disableCachingBindingFailures&gt;-Element
Gibt an, ob die Zwischenspeicherung von Bindungsfehlern, die auftreten, da die Assembly durch Überprüfen nicht gefunden wurde, deaktiviert werden soll.  
  
## Syntax  
  
```  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob die Zwischenspeicherung von Bindungsfehlern, die auftreten, da die Assembly durch Überprüfen nicht gefunden wurde, deaktiviert werden soll.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|0|Zwischenspeichern von Assemblybindungsfehlern, die auftreten, weil die Assembly durch Überprüfen nicht gefunden wurde, nicht deaktivieren.  Dies ist das standardmäßige Bindungsverhalten, das mit .NET Framework, Version 2.0, beginnt.|  
|1|Zwischenspeichern von Assemblybindungsfehlern deaktivieren, die auftreten, weil die Assembly durch Überprüfen nicht gefunden wurde.  Diese Einstellung stellt das Bindungsverhalten von .NET Framework, Version 1.1, wieder her.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Ab .NET Framework, Version 2.0, besteht das Standardverhalten zum Laden von Assemblys im Zwischenspeichern von Bindungs\- und Ladefehlern.  Das heißt, wenn der Versuch, eine Assembly zu laden, nicht erfolgreich war, führen anschließende Anforderungen zum Laden derselben Assembly sofort zu einem Fehler, ohne dass versucht wird, die Assembly zu finden.  Dieses Element deaktiviert das Standardverhalten für Bindungsfehler, die auftreten, da die Assembly nicht im Überprüfungspfad gefunden werden konnte.  Diese Fehler lösen <xref:System.IO.FileNotFoundException> aus.  
  
 Einige Bindungs\- und Ladefehler sind durch dieses Element nicht betroffen. Sie werden immer zwischengespeichert.  Diese Fehler können auftreten, da die Assembly gefunden, jedoch nicht geladen wurde.  Sie lösen <xref:System.BadImageFormatException> oder <xref:System.IO.FileLoadException> aus.  Die folgende Liste enthält einige Beispiele für derartige Fehler.  
  
-   Wenn Sie versuchen, eine Datei zu laden, bei der es sich um keine gültige Assembly handelt, schlagen nachfolgende Versuche, die Assembly zu laden, fehl, auch wenn die ungültige Datei durch die richtige Assembly ersetzt wird.  
  
-   Wenn Sie versuchen, eine Assembly zu laden, die durch das Dateisystem gesperrt ist, schlagen nachfolgende Versuche, die Assembly zu laden, fehl, und zwar auch nach der Freigabe der Assembly durch das Dateisystem.  
  
-   Wenn sich mindestens eine Version der Assembly, die Sie laden möchten, im Suchpfad befindet, aber die konkrete Version, die Sie anfordern, darin nicht enthalten ist, schlagen nachfolgende Versuche, die Version zu laden, fehl, auch wenn die richtige Version in den Suchpfad verschoben wird.  
  
## Beispiel  
 Im folgenden Codebeispiel wird gezeigt, wie das Zwischenspeichern von Assemblybindungsfehlern, die auftreten, deaktiviert wird, da die Assembly durch Überprüfen nicht gefunden wurde.  
  
```  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)