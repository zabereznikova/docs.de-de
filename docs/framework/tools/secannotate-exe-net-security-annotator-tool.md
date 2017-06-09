---
title: "SecAnnotate.exe (.NET Security Annotator Tool) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "SecAnnotate.exe"
  - "Security Annotator tool"
ms.assetid: 8104d208-7813-4a1d-8a75-58f9a7bcb8c9
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# SecAnnotate.exe (.NET Security Annotator Tool)
Das .NET Security Annotator\-Tool \(SecAnnotate.exe\) ist eine Befehlszeilenanwendung, die die `SecurityCritical`\- und `SecuritySafeCritical`\-Teile einer oder mehrerer Assemblys identifiziert.  
  
 [Security Annotator](http://go.microsoft.com/fwlink/?LinkId=198007), eine Visual Studio\-Erweiterung, stellt eine grafische Benutzeroberfläche für "SecAnnotate.exe" bereit und ermöglicht die Ausführung des Tools in Visual Studio.  
  
 Dieses Tool wird automatisch mit Visual Studio installiert.  Zum Ausführen des Tools verwenden Sie die Developer\-Eingabeaufforderung \(oder die Visual Studio\-Eingabeaufforderung in Windows 7\).  Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein, wobei *parameters* im folgenden Abschnitt beschrieben werden und *assemblies* aus mindestens einem durch Leerzeichen getrennten Assemblynamen bestehen:  
  
## Syntax  
  
```  
SecAnnotate.exe [parameters] [assemblies]  
```  
  
#### Parameter  
  
|Option|Beschreibung|  
|------------|------------------|  
|`/a`<br /><br /> oder<br /><br /> `/showstatistics`|Zeigt eine Statistik zur Verwendung der Transparenz in Assemblys an, die analysiert werden.|  
|`/d:` *directory*<br /><br /> oder<br /><br /> `/referencedir:` *directory*|Gibt ein Verzeichnis an, das während der Anmerkung nach abhängigen Assemblys durchsucht werden soll.|  
|`/i`<br /><br /> oder<br /><br /> `/includesignatures`|Schließt erweiterte Signaturinformationen in die Anmerkungsberichtsdatei ein.|  
|`/n`<br /><br /> oder<br /><br /> `/nogac`|Unterdrückt die Suche nach Assemblys, auf die im globalen Assemblycache verwiesen wird.|  
|`/o:` *output.xml*  ``<br /><br /> oder<br /><br /> `/out:` *output.xml*|Gibt die Ausgabeanmerkungsdatei an.|  
|`/p:` *maxpasses*  ``<br /><br /> oder<br /><br /> `/maximumpasses:` *maxpasses*|Gibt die maximale Anzahl von Anmerkungsphasen für Assemblys an, bevor die Generierung von neuen Anmerkungen beendet wird.|  
|`/q`<br /><br /> oder<br /><br /> `/quiet`|Gibt den stillen Modus an, in dem die Anmerkungsfunktion keine Statusmeldungen, sondern nur Fehlerinformationen ausgibt.|  
|`/r:` *assembly*<br /><br /> oder<br /><br /> `/referenceassembly:` *assembly*|Schließt die angegebene Assembly beim Auflösen von abhängigen Assemblys während der Anmerkung ein.  Verweisassemblys erhalten gegenüber Assemblys, die im Verweispfad gefunden werden, Priorität.|  
|`/s:` *rulename*  ``<br /><br /> oder<br /><br /> `/suppressrule:` *rulename*|Unterdrückt das Ausführen der angegebenen Transparenzregel für die Eingabeassemblys.|  
|`/t`<br /><br /> oder<br /><br /> `/forcetransparent`|Zwingt das Annotator\-Tool, alle Assemblys, die keine Transparenzanmerkungen aufweisen, so zu behandeln, als ob sie völlig transparent wären.|  
|`/t`:*assembly*<br /><br /> oder<br /><br /> `/forcetransparent`:*assembly*|Zwingt die gegebene Assembly, transparent zu sein, unabhängig von ihren aktuellen Anmerkungen auf Assemblyebene.|  
|||  
|`/v`<br /><br /> oder<br /><br /> `/verify`|Überprüft nur, ob die Anmerkungen einer Assembly korrekt sind. Es wird nicht versucht, mehrere Durchläufe auszuführen, um alle erforderlichen Anmerkungen zu finden, wenn die Assembly nicht überprüft wird.|  
|`/x`<br /><br /> oder<br /><br /> `/verbose`|Legt die ausführliche Ausgabe während des Kommentierens fest.|  
|`/y:` *directory*  ``<br /><br /> oder<br /><br /> `/symbolpath:` *directory*|Schließt das angegebene Verzeichnis beim Suchen nach Symboldateien während der Anmerkung ein.|  
  
## Hinweise  
 Parameter und Assemblys werden möglicherweise auch in einer Antwortdatei bereitgestellt, die in der Befehlszeile angegeben und der ein @\-Zeichen vorangestellt wird.  Jede Zeile in der Antwortdatei sollte einen einzelnen Parameter\- oder Assemblynamen enthalten.  
  
 Weitere Informationen zu .NET Security Annotator finden Sie im Eintrag [Using SecAnnotate to Analyze Your Assemblies for Transparency Violations](http://go.microsoft.com/fwlink/?LinkId=187648) im .NET Security Blog.  
  
## Beispiele