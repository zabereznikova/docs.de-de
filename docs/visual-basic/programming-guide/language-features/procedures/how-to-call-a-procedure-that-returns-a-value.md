---
title: "Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f6d408eed67fa417f42252bb49ecea28d4458382
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt (Visual Basic)
Ein `Function` Prozedur gibt einen Wert an den aufrufenden Code zurück. Rufen Sie sie einschließlich Name und Argumente entweder auf der rechten Seite einer zuweisungsanweisung oder in einem Ausdruck.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>Aufrufen eine Funktionsprozedur innerhalb eines Ausdrucks  
  
1.  Verwenden Sie die `Function` Prozedur benennen Sie die gleiche Weise verwenden Sie eine Variable. Sie können eine `Function` Prozeduraufruf anywhere können Sie eine Variable oder Konstante in einem Ausdruck verwenden.  
  
2.  Führen Sie den Namen der Prozedur mit Klammern einschließen, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen. Allerdings besser mit den Klammern Code lesen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein. Achten Sie darauf geben Sie die Argumente in der gleichen Reihenfolge, die die `Function` Prozedur definiert, die entsprechenden Parameter.  
  
     Alternativ können Sie anhand des Namens ein oder mehrere Argumente übergeben. Weitere Informationen finden Sie unter [übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md).  
  
4.  Von der Prozedur zurückgegebene Wert ist Teil des Ausdrucks wie den Wert einer Variablen oder Konstante.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>Aufrufen einer Funktion in einer zuweisungsanweisung  
  
1.  Verwenden der `Function` Prozedurnamen nach dem Gleichheitszeichen (`=`) die zuweisungsanweisung anmelden.  
  
2.  Führen Sie den Namen der Prozedur mit Klammern einschließen, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen. Allerdings besser mit den Klammern Code lesen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein. Achten Sie darauf geben Sie die Argumente in der gleichen Reihenfolge, die die `Function` Prozedur die entsprechenden Parameter definiert, es sei denn, Sie werden anhand des Namens übergeben.  
  
4.  Der von der Prozedur zurückgegebene Wert ist in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A> zum Abrufen des Werts einer Betriebssystem-Umgebungsvariablen. Die erste Zeile ruft `Environ` innerhalb eines Ausdrucks und die zweite Zeile ruft er in einer zuweisungsanweisung. `Environ`akzeptiert den Variablennamen als einziges Argument. Es gibt den Wert der Variablen an den aufrufenden Code zurück.  
  
 [!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Function-Prozeduren](./function-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt](./how-to-create-a-procedure-that-returns-a-value.md)  
 [Gewusst wie: Abrufen eines Werts aus einer Prozedur](./how-to-return-a-value-from-a-procedure.md)  
 [Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md)
