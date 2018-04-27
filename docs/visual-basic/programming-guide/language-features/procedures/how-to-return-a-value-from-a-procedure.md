---
title: 'Gewusst wie: Zurückgeben eines Werts aus einer Prozedur (Visual Basic)'
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
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: affcb25951a6647604286bc91dcaec8898fe2e30
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Gewusst wie: Zurückgeben eines Werts aus einer Prozedur (Visual Basic)
Ein `Function` Prozedur gibt einen Wert an den aufrufenden Code entweder durch das Ausführen einer `Return` Anweisung oder beim Auftreten einer `Exit Function` oder `End Function` Anweisung.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Einen Wert, der mithilfe der Return-Anweisung zurückgegeben  
  
1.  Versetzen einer `Return` Anweisung, an dem Punkt, bei dem die Aufgabe der Prozedur abgeschlossen ist.  
  
2.  Führen Sie die `Return` Schlüsselwort durch einen Ausdruck, der den Wert ergibt, an den aufrufenden Code zurückgegeben werden sollen.  
  
3.  Es können sich mehrere `Return`-Anweisungen in derselben Prozedur befinden.  
  
     Die folgenden `Function` Prozedur berechnet die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, und gibt ihn an den aufrufenden Code zurück.  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     Das folgende Beispiel zeigt einen typischen Aufruf `hypotenuse`, die den zurückgegebenen Wert speichert.  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Einen Wert, der mit Exit Function oder End Function zurückgegeben  
  
1.  Mindestens ein direkt in die `Function` Prozedur, weisen Sie einen Wert, der Name der Prozedur.  
  
2.  Beim Ausführen einer `Exit Function` oder `End Function` -Anweisung, Visual Basic gibt den Namen der Prozedur zuletzt zugewiesenen Wert zurück.  
  
3.  Es können sich mehrere `Exit Function`-Anweisungen in derselben Prozedur befinden. Außerdem können sich sowohl `Return`- als auch `Exit Function`-Anweisungen in derselben Prozedur befinden.  
  
4.  Sie sind nur möglich `End Function` -Anweisung in einem `Function` Prozedur.  
  
     Weitere Informationen und ein Beispiel finden Sie unter "Rückgabewert" in [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Sub-Prozeduren](./sub-procedures.md)  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Operatorprozeduren](./operator-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Return-Anweisung](../../../../visual-basic/language-reference/statements/return-statement.md)  
 [Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt](./how-to-create-a-procedure-that-returns-a-value.md)  
 [Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)
