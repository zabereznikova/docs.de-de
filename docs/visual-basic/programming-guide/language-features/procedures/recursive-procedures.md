---
title: Rekursive Prozeduren (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 471746f4412b61c9782e8019aa8a9ec6221afb04
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="recursive-procedures-visual-basic"></a>Rekursive Prozeduren (Visual Basic)
Ein *rekursive* Prozedur ist eine, die sich selbst aufruft. Im Allgemeinen ist dies nicht die effizienteste Methode, Visual Basic-Code zu schreiben.  
  
 Im folgenden Verfahren wird die Rekursion berechnet die Fakultät des ursprünglichen Arguments.  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a>Überlegungen zu mit rekursive Prozeduren  
 **Beschränkenden Bedingungen**. Sie müssen eine rekursive Prozedur für mindestens eine Bedingung zu testen, die die Rekursion beendet entwerfen, und müssen Sie auch die Groß-/Kleinschreibung, in denen keine solche Bedingung, in eine angemessene Anzahl von rekursiven Aufrufen erfüllt ist, behandeln. Ohne mindestens eine Bedingung, die ohne Fehler erfüllt werden kann, wird die Prozedur ein erhöhtes Risiko der Ausführung in einer Endlosschleife ausgeführt.  
  
 **Speichernutzung**. Die Anwendung verfügt über eine begrenzte Menge an Speicherplatz für lokale Variablen. Jedes Mal eine Prozedur aufruft, verwendet es weiterer Speicherplatz für zusätzliche Kopien ihrer lokalen Variablen. Wenn dieser Prozess unbestimmte Zeit weiterhin besteht, wird letztendlich eine <xref:System.StackOverflowException> Fehler.  
  
 **Effizienz**. Sie können fast immer eine Schleife für die Rekursion ersetzen. Eine Schleife muss sich nicht auf den Aufwand für das Übergeben von Argumenten, Initialisieren von zusätzlichem Speicher und Zurückgeben von Werten aus. Die Leistung kann sich wesentlich besser ohne rekursive Aufrufe sein.  
  
 **Gegenseitige Rekursion**. Sie können eine sehr schlechte Leistung oder sogar eine unendliche Schleife beobachten, ob zwei Prozeduren gegenseitig aufrufen. Ein solcher Entwurf bietet die gleichen Probleme als ein rekursives Prozedur, aber möglicherweise schwerer zu erkennen und zu debuggen.  
  
 **Aufrufen mit Klammern**. Wenn eine `Function` Prozedur ruft sich selbst rekursiv, Sie müssen den Prozedurnamen mit Klammern folgen, auch wenn es keine Argumentliste enthalten. Der Funktionsname stammt, andernfalls als, das den Rückgabewert der Funktion darstellt.  
  
 **Testen von**. Wenn Sie eine rekursive Prozedur schreiben, sollten Sie es sehr sorgfältig testen, um sicherzustellen, dass es immer eine einschränkende Bedingung erfüllt. Sie sollten auch sicherstellen, dass nicht genügend Arbeitsspeicher aufgrund von zu viele rekursive Aufrufe ausgeführt werden kann.  
  
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
 [Problembehandlung bei Ausnahmen: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
