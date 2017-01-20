---
title: "Recursive Procedures (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, procedures"
  - "procedures, that call themselves"
  - "procedures, recursive"
  - "procedures, calling"
  - "recursive procedures"
  - "functions [Visual Basic], calling recursively"
  - "recursion"
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Recursive Procedures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*Rekursive* Prozeduren sind Prozeduren, die sich selbst aufrufen.  Im Allgemeinen ist dies nicht die effizienteste Art und Weise, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Code zu schreiben.  
  
 Die folgende Prozedur berechnet die Fakultät ihres ursprünglichen Arguments mithilfe der Rekursion.  
  
 [!code-vb[VbVbcnProcedures#51](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## Überlegungen hinsichtlich rekursiver Prozeduren  
 **Einschränkende Bedingungen**.  Sie müssen eine rekursive Prozedur so gestalten, dass sie mindestens eine Bedingung überprüft, mit der die Rekursion beendet wird. Berücksichtigen Sie auch den Fall, dass eine solche Bedingung auch nach einer hinlänglichen Anzahl rekursiver Aufrufe nicht erfüllt wird.  Wenn nicht mindestens eine Bedingung gegeben ist, die fehlerfrei erfüllt werden kann, dann besteht die Gefahr, dass die Prozedur in einer Endlosschleife ausgeführt wird.  
  
 **Speichernutzung**.  Anwendungen verfügen nur beschränkt über Speicherplatz für lokale Variablen.  Jedes Mal, wenn eine Prozedur sich selbst aufruft, verbraucht sie mehr von diesem Platz für zusätzliche Kopien ihrer lokalen Variablen.  Wenn sich dieser Vorgang unendlich lange fortsetzt, wird letztendlich ein <xref:System.StackOverflowException>\-Fehler ausgelöst.  
  
 **Effizienz**.  Rekursion lässt sich fast immer durch eine Schleife ersetzen.  Eine Schleife ist nicht mit dem Verwaltungsaufwand verbunden, den das Übergeben von Argumenten, das Initialisieren von zusätzlichem Speicher und das Zurückgeben von Werten bedeutet.  Das Leistungsverhalten kann ohne rekursive Aufrufe u. U. viel besser sein.  
  
 **Gegenseitige Rekursion**.  Sie werden ein sehr schlechtes Leistungsverhalten feststellen oder sogar eine Endlosschleife finden, wenn zwei Prozeduren einander aufrufen.  Eine solche Konstellation verursacht die gleichen Probleme wie eine einzelne rekursive Prozedur, ist aber möglicherweise schwerer zu erkennen und zu debuggen.  
  
 **Aufrufe mit Klammern**.  Wenn eine `Function`\-Prozedur sich rekursiv aufruft, müssen auch dann nach dem Prozedurnamen runde Klammern angegeben werden, wenn keine Argumentliste vorhanden ist.  Anderenfalls wird der Funktionsname als Rückgabewert der Funktion gedeutet.  
  
 **Testen**.  Beim Schreiben einer rekursiven Prozedur sollten Sie sehr sorgfältig testen, ob die Prozedur stets eine einschränkende Bedingung erfüllt.  Sie sollten auch sicherstellen, dass der Arbeitsspeicher nicht durch zu viele rekursive Aufrufe erschöpft wird.  
  
## Siehe auch  
 <xref:System.StackOverflowException>   
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function\-Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Troubleshooting Procedures](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Problembehandlung bei Ausnahmen: System.StackOverflowException](../Topic/Troubleshooting%20Exceptions:%20System.StackOverflowException.md)