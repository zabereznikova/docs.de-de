---
title: Rekursive Prozeduren (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, that call themselves
- procedures, recursive
- procedures, calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9fc95cd5f7cfd5637f6282c6ef571eb81bac1816
ms.lasthandoff: 03/13/2017

---
# <a name="recursive-procedures-visual-basic"></a>Rekursive Prozeduren (Visual Basic)
Ein *rekursive* Prozedur ist eine, die sich selbst aufruft. Im Allgemeinen, dies ist nicht die effizienteste Methode zum Schreiben [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Code.  
  
 Die folgende Prozedur verwendet die Rekursion berechnet die Fakultät ihres ursprünglichen Arguments.  
  
 [!code-vb[VbVbcnProcedures&51;](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a>Zu rekursive Prozeduren  
 **Beschränkenden Bedingungen**. Sie müssen eine rekursive Prozedur für mindestens eine Bedingung zu testen, die die Rekursion beendet entwerfen, und Sie müssen auch den Fall, in dem keine solchen Bedingung, innerhalb einer angemessenen Anzahl von rekursiven Aufrufen erfüllt ist, behandeln. Ohne mindestens eine Bedingung, die fehlerfrei erfüllt werden kann, wird die Prozedur ein erhöhtes Risiko für die Ausführung in einer Endlosschleife ausgeführt.  
  
 **Speicherverwendung**. Ihre Anwendung hat eine begrenzte Menge an Speicherplatz für lokale Variablen. Jedes Mal eine Prozedur aufruft, wird weiterer Speicherplatz für zusätzliche Kopien ihrer lokalen Variablen. Wenn dieser Vorgang unendlich lange fortsetzt, wird letztendlich eine <xref:System.StackOverflowException>Fehler.</xref:System.StackOverflowException>  
  
 **Effizienz**. Sie können fast immer eine Schleife für die Rekursion ersetzen. Eine Schleife muss nicht den Aufwand für das Übergeben von Argumenten, Initialisieren von zusätzlichem Speicher und das Zurückgeben von Werten. Die Leistung kann ohne rekursive Aufrufe viel besser sein.  
  
 **Gegenseitige Rekursion**. Sie können eine sehr schlechte Leistung oder sogar eine Endlosschleife, beobachten, wenn zwei Prozeduren einander aufrufen. Ein solcher Entwurf stellt die gleichen Probleme wie eine einzelne rekursive Prozedur, aber möglicherweise schwerer zu erkennen und zu debuggen.  
  
 **Aufrufe mit Klammern**. Wenn ein `Function` Prozedur ruft sich selbst rekursiv, Sie müssen den Namen der Prozedur mit Klammern folgen, selbst wenn keine Argumentliste vorhanden ist. Andernfalls stammt der Funktionsname als Rückgabewert der Funktion.  
  
 **Testen von**. Wenn Sie eine rekursive Prozedur schreiben, sollten Sie es sehr sorgfältig testen, um sicherzustellen, dass es immer eine einschränkende Bedingung erfüllt. Sie sollten auch sicherstellen, dass nicht genügend Arbeitsspeicher nicht durch zu viele rekursive Aufrufe ausgeführt werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.StackOverflowException></xref:System.StackOverflowException>   
 [Verfahren](./index.md)   
 [Sub-Prozeduren](./sub-procedures.md)   
 [Function-Prozeduren](./function-procedures.md)   
 [Property-Prozeduren](./property-procedures.md)   
 [Operatorprozeduren](./operator-procedures.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Prozedurüberladung](./procedure-overloading.md)   
 [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)   
 [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Problembehandlung bei Ausnahmen: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
