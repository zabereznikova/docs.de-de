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
ms.openlocfilehash: b08a06a07f134b7c95251848862d39339e59fe61
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274340"
---
# <a name="recursive-procedures-visual-basic"></a>Rekursive Prozeduren (Visual Basic)

Eine *rekursive* Prozedur ist eine, die sich selbst aufruft. Im Allgemeinen ist dies nicht die effektivste Methode, Visual Basic Code zu schreiben.  
  
 Im folgenden Verfahren wird Rekursion verwendet, um die Fakultät des ursprünglichen Arguments zu berechnen.  
  
 [!code-vb[VbVbcnProcedures#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#51)]  
  
## <a name="considerations-with-recursive-procedures"></a>Überlegungen zu rekursiven Verfahren

 **Einschränkende Bedingungen**. Sie müssen eine rekursive Prozedur entwerfen, um mindestens eine Bedingung zu testen, die die Rekursion beenden kann. Außerdem müssen Sie den Fall behandeln, in dem eine solche Bedingung innerhalb einer angemessenen Anzahl von rekursiven Aufrufen nicht erfüllt wird. Wenn mindestens eine Bedingung nicht erfüllt werden kann, ohne dass ein Fehler auftritt, führt Ihre Prozedur ein hohes Risiko für die Ausführung in einer Endlosschleife aus.

 **Speichernutzung**. Die Anwendung verfügt über einen begrenzten Speicherplatz für lokale Variablen. Jedes Mal, wenn eine Prozedur sich selbst aufruft, verwendet Sie mehr von diesem Bereich für zusätzliche Kopien Ihrer lokalen Variablen. Wenn dieser Prozess unbegrenzt fortgesetzt wird, verursacht er <xref:System.StackOverflowException> letztendlich einen Fehler.

 **Effizienz**: Sie können eine Schleife fast immer für Rekursion ersetzen. Eine-Schleife hat nicht den mehr Aufwand, um Argumente zu übergeben, zusätzlichen Speicher zu initialisieren und Werte zurückzugeben. Die Leistung kann sich ohne rekursive Aufrufe erheblich verbessern.

 **Gegenseitige Rekursion**. Sie können eine sehr schlechte Leistung oder sogar eine Endlosschleife beobachten, wenn zwei Prozeduren einander aufzurufen. Ein solcher Entwurf zeigt dieselben Probleme wie eine einzelne rekursive Prozedur, kann jedoch schwieriger zu erkennen und zu debuggen sein.

 **Aufrufen von mit Klammern**. Wenn eine `Function` Prozedur sich selbst rekursiv aufruft, müssen Sie den Namen der Prozedur mit Klammern befolgen, auch wenn keine Argumentliste vorhanden ist. Andernfalls wird der Funktionsname als Darstellung des Rückgabewerts der Funktion verwendet.

 **Testen**. Wenn Sie eine rekursive Prozedur schreiben, sollten Sie Sie sehr sorgfältig testen, um sicherzustellen, dass Sie immer eine einschränkende Bedingung erfüllt. Sie sollten auch sicherstellen, dass nicht genügend Arbeitsspeicher verfügbar ist, weil zu viele rekursive Aufrufe vorhanden sind.

## <a name="see-also"></a>Siehe auch

- <xref:System.StackOverflowException>
- [Verfahren](index.md)
- [Sub-Prozeduren](sub-procedures.md)
- [Function-Prozeduren](function-procedures.md)
- [Eigenschaftenprozeduren](property-procedures.md)
- [Operatorprozeduren](operator-procedures.md)
- [Parameter und Argumente von Prozeduren](procedure-parameters-and-arguments.md)
- [Prozedurüberladung](procedure-overloading.md)
- [Problembehandlung bei Prozeduren](troubleshooting-procedures.md)
- [Schleifenstruktur](../control-flow/loop-structures.md)
