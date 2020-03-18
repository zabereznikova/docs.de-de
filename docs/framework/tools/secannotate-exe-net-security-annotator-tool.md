---
title: SecAnnotate.exe (.NET Security Annotator-Tool)
ms.date: 03/30/2017
helpviewer_keywords:
- SecAnnotate.exe
- Security Annotator tool
ms.assetid: 8104d208-7813-4a1d-8a75-58f9a7bcb8c9
ms.openlocfilehash: ffc275c588775fb79da276be904ada90a5a31bad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75937924"
---
# <a name="secannotateexe-net-security-annotator-tool"></a>SecAnnotate.exe (.NET Security Annotator-Tool)
Das .NET Security Annotator-Tool (SecAnnotate.exe) ist eine Befehlszeilenanwendung, die die `SecurityCritical`- und `SecuritySafeCritical`-Teile einer oder mehrerer Assemblys identifiziert.  
  
 [Security Annotator,](https://marketplace.visualstudio.com/items?itemName=sheldonb.SecurityAnnotator) eine Visual Studio-Erweiterung, stellt eine grafische Benutzeroberfläche für „secAnnotate.exe“ bereit und ermöglicht die Ausführung des Tools in Visual Studio.  
  
 Dieses Tool wird automatisch mit Visual Studio installiert. Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein, wobei *Parameter* im folgenden Abschnitt beschrieben werden und *Assemblys* aus mindestens einem durch Leerzeichen getrennten Assemblynamen bestehen:  
  
## <a name="syntax"></a>Syntax  
  
```console  
SecAnnotate.exe [parameters] [assemblies]  
```  
  
## <a name="parameters"></a>Parameter  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`/a`<br /><br /> oder<br /><br /> `/showstatistics`|Zeigt eine Statistik zur Verwendung der Transparenz in Assemblys an, die analysiert werden.|  
|`/d:` *verzeichnis*<br /><br /> oder<br /><br /> `/referencedir:` *verzeichnis*|Gibt ein Verzeichnis an, das während der Anmerkung nach abhängigen Assemblys durchsucht werden soll.|  
|`/i`<br /><br /> oder<br /><br /> `/includesignatures`|Schließt erweiterte Signaturinformationen in die Anmerkungsberichtsdatei ein.|  
|`/n`<br /><br /> oder<br /><br /> `/nogac`|Unterdrückt die Suche nach Assemblys, auf die im globalen Assemblycache verwiesen wird.|  
|`/o:` *output.xml*<br /><br /> oder<br /><br /> `/out:` *output.xml*|Gibt die Ausgabeanmerkungsdatei an.|  
|`/p:` *maxpasses*<br /><br /> oder<br /><br /> `/maximumpasses:` *maxpasses*|Gibt die maximale Anzahl von Anmerkungsphasen für Assemblys an, bevor die Generierung von neuen Anmerkungen beendet wird.|  
|`/q`<br /><br /> oder<br /><br /> `/quiet`|Gibt den stillen Modus an, in dem die Anmerkungsfunktion keine Statusmeldungen, sondern nur Fehlerinformationen ausgibt.|  
|`/r:` *assembly*<br /><br /> oder<br /><br /> `/referenceassembly:` *assembly*|Schließt die angegebene Assembly beim Auflösen von abhängigen Assemblys während der Anmerkung ein. Verweisassemblys erhalten gegenüber Assemblys, die im Verweispfad gefunden werden, Priorität.|  
|`/s:` *regelname*<br /><br /> oder<br /><br /> `/suppressrule:` *regelname*|Unterdrückt das Ausführen der angegebenen Transparenzregel für die Eingabeassemblys.|  
|`/t`<br /><br /> oder<br /><br /> `/forcetransparent`|Zwingt das Annotator-Tool, alle Assemblys, die keine Transparenzanmerkungen aufweisen, so zu behandeln, als ob sie völlig transparent wären.|  
|`/t`:*assembly*<br /><br /> oder<br /><br /> `/forcetransparent`:*assembly*|Zwingt die gegebene Assembly, transparent zu sein, unabhängig von ihren aktuellen Anmerkungen auf Assemblyebene.|  
|||  
|`/v`<br /><br /> oder<br /><br /> `/verify`|Überprüft nur, ob die Anmerkungen einer Assembly korrekt sind. Es wird nicht versucht, mehrere Durchläufe auszuführen, um alle erforderlichen Anmerkungen zu finden, wenn die Assembly nicht überprüft wird.|  
|`/x`<br /><br /> oder<br /><br /> `/verbose`|Legt die ausführliche Ausgabe während des Kommentierens fest.|  
|`/y:` *verzeichnis*<br /><br /> oder<br /><br /> `/symbolpath:` *verzeichnis*|Schließt das angegebene Verzeichnis beim Suchen nach Symboldateien während der Anmerkung ein.|  
  
## <a name="remarks"></a>Hinweise  
 Parameter und Assemblys werden möglicherweise auch in einer Antwortdatei bereitgestellt, die in der Befehlszeile angegeben und der ein @-Zeichen vorangestellt wird. Jede Zeile in der Antwortdatei sollte einen einzelnen Parameter- oder Assemblynamen enthalten.  
  
 Weitere Informationen zu .NET Security Annotator finden Sie im Eintrag [Using SecAnnotate to Analyze Your Assemblies for Transparency Violations (Analysieren Ihrer Assemblys auf Transparenzverstöße mit SecAnnotate)](https://docs.microsoft.com/archive/blogs/shawnfa/using-secannotate-to-analyze-your-assemblies-for-transparency-violations-an-example) im .NET Security Blog.  
  
## <a name="examples"></a>Beispiele
