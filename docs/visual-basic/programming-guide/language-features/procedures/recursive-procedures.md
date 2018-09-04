---
title: Rekursive Prozeduren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: 0bb89ac855d65d7677a062346db8665698dbb805
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514341"
---
# <a name="recursive-procedures-visual-basic"></a>Rekursive Prozeduren (Visual Basic)
Ein *rekursive* Verfahren ist ein, der sich selbst aufruft. Im Allgemeinen ist dies nicht die effektivste Möglichkeit, Visual Basic-Code zu schreiben.  
  
 Das folgende Verfahren verwendet die Rekursion berechnet die Fakultät des ursprünglichen Arguments.  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a>Überlegungen zu mit rekursive Prozeduren  
 **Beschränkenden Bedingungen**. Müssen Sie eine rekursive Prozedur zum Prüfen auf mindestens eine Bedingung, die die Rekursion beendet werden kann, entwerfen, und Sie müssen auch die Groß-/Kleinschreibung, keine solche Bedingung, in eine angemessene Anzahl von rekursiven Aufrufe erfüllt ist, behandeln. Ohne mindestens eine Bedingung, die ohne Fehler erfüllt werden können, führt Ihre Prozedur ein erhöhtes Risiko für die Ausführung in eine Endlosschleife.  
  
 **Speichernutzung**. Ihre Anwendung verfügt über eine begrenzte Menge an Speicherplatz für lokale Variablen. Jedes Mal eine Prozedur sich selbst aufruft wird weiterer Speicherplatz für zusätzliche Kopien der zugehörigen lokalen Variablen. Wenn dieser Prozess auf unbestimmte Zeit weiterhin besteht, wird letztendlich eine <xref:System.StackOverflowException> Fehler.  
  
 **Effizienz**. Sie können fast immer eine Schleife für die Rekursion ersetzen. Eine Schleife muss sich nicht auf den Aufwand für das Übergeben von Argumenten, initialisieren zusätzlichen Speicher und Zurückgeben von Werten aus. Die Leistung kann ohne rekursive Aufrufe viel besser sein.  
  
 **Gegenseitige Rekursion**. Sie können sehr schlechte Leistung oder sogar eine unendliche Schleife, beobachten, wenn zwei Prozeduren gegenseitig aufrufen. Ein solcher Entwurf stellt die gleichen Probleme wie eine einzelne rekursive Prozedur, aber Sie können nicht so leicht erkennen und zu debuggen.  
  
 **Aufrufen von in Klammern**. Wenn eine `Function` Prozedur rekursiv aufruft, müssen Sie den Namen der Prozedur mit Klammern, befolgen, auch wenn keine Argumentliste vorhanden ist. Der Funktionsname stammt, andernfalls als, das den Rückgabewert der Funktion darstellt.  
  
 **Testen von**. Wenn Sie eine rekursive Prozedur schreiben, sollten Sie sie sorgfältig testen, um sicherzustellen, dass es immer eine einschränkende Bedingung erfüllt. Sie sollten auch sicherstellen, dass Sie nicht genügend Arbeitsspeicher aufgrund zu viele rekursive Aufrufe nicht ausführen können.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.StackOverflowException>  
 [Verfahren](./index.md)  
 [Sub-Prozeduren](./sub-procedures.md)  
 [Function-Prozeduren](./function-procedures.md)  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Operatorprozeduren](./operator-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Prozedurüberladung](./procedure-overloading.md)  
 [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)  
 [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Problembehandlung bei Ausnahmen: System.StackOverflowException](https://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
