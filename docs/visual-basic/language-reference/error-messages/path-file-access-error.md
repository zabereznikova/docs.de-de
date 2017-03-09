---
title: "Path/File access error | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID75"
dev_langs: 
  - "VB"
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Path/File access error
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Das Betriebssystem konnte während eines Datei\- oder Datenträgerzugriffs keine Verbindung zwischen dem Pfad und dem Dateinamen herstellen.  
  
### So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass die Dateispezifikation richtig formatiert ist.  Ein Dateiname kann einen vollqualifizierten \(absoluten\) oder relativen Pfad enthalten.  Ein vollqualifizierter Pfad beginnt mit dem Laufwerknamen \(falls der Pfad zu einem anderen Laufwerk führt\) und listet den expliziten Pfad vom Stammverzeichnis zur Datei auf.  Jeder nicht vollqualifizierte Pfad verhält sich relativ zum aktuellen Laufwerk und Verzeichnis.  
  
2.  Vergewissern Sie sich, dass Sie keine Datei speichern wollten, durch die eine vorhandene schreibgeschützte Datei ersetzt würde.  In einem solchen Fall müssen Sie das Schreibschutzattribut der Zieldatei ändern oder die Datei unter einem anderen Namen speichern.  
  
3.  Stellen Sie sicher, dass Sie nicht versucht haben, eine schreibgeschützte Datei im sequenziellen `Output`\-Modus oder `Append`\-Modus zu öffnen.  In einem solchen Fall müssen Sie die Datei im `Input`\-Modus öffnen oder das Schreibschutzattribut der Datei ändern.  
  
4.  Stellen Sie außerdem sicher, dass Sie kein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Projekt innerhalb einer Datenbank oder eines Dokuments ändern wollten.  
  
## Siehe auch  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)