---
title: Rekursive Prozeduren
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
ms.openlocfilehash: 646d4e29ed7a0b6367d4b35a7f8641bcf659e616
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352556"
---
# <a name="recursive-procedures-visual-basic"></a>Rekursive Prozeduren (Visual Basic)

Eine *rekursive* Prozedur ist eine, die sich selbst aufruft. Im Allgemeinen ist dies nicht die effektivste Methode, Visual Basic Code zu schreiben.  
  
 Im folgenden Verfahren wird Rekursion verwendet, um die Fakultät des ursprünglichen Arguments zu berechnen.  
  
 [!code-vb[VbVbcnProcedures#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#51)]  
  
## <a name="considerations-with-recursive-procedures"></a>Überlegungen zu rekursiven Verfahren

 **Einschränkende Bedingungen**. Sie müssen eine rekursive Prozedur entwerfen, um mindestens eine Bedingung zu testen, die die Rekursion beenden kann. Außerdem müssen Sie den Fall behandeln, in dem eine solche Bedingung innerhalb einer angemessenen Anzahl von rekursiven Aufrufen nicht erfüllt wird. Wenn mindestens eine Bedingung nicht erfüllt werden kann, ohne dass ein Fehler auftritt, führt Ihre Prozedur ein hohes Risiko für die Ausführung in einer Endlosschleife aus.

 **Speichernutzung**. Die Anwendung verfügt über einen begrenzten Speicherplatz für lokale Variablen. Jedes Mal, wenn eine Prozedur sich selbst aufruft, verwendet Sie mehr von diesem Bereich für zusätzliche Kopien Ihrer lokalen Variablen. Wenn dieser Prozess unbegrenzt fortgesetzt wird, verursacht er letztendlich einen <xref:System.StackOverflowException> Fehler.

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
