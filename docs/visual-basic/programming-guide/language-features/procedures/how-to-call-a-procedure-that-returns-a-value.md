---
title: "Gewusst wie: Aufrufen einer Prozedur, die einen Wert (Visual Basic) zurückgibt. | Microsoft-Dokumentation"
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
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
- procedures, returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: df6bb1ed8acf5f86a290d67fec9c053cfe5245d2
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt (Visual Basic)
Ein `Function` Verfahren gibt einen Wert an den aufrufenden Code zurück. Rufen Sie sie einschließlich Name und Argumenten auf der rechten Seite einer zuweisungsanweisung oder in einem Ausdruck.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>Zum Aufrufen einer Funktionsprozedur innerhalb eines Ausdrucks  
  
1.  Verwenden Sie die `Function` Prozedur benennen Sie die gleiche Weise verwenden Sie eine Variable. Sie können eine `Function` Prozeduraufruf anywhere können Sie eine Variable oder Konstante in einem Ausdruck verwenden.  
  
2.  Führen Sie den Namen der Prozedur mit Klammern um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern auch weglassen. Allerdings vereinfacht die Verwendung der Klammern Code leichter zu lesen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt. Stellen Sie sicher, geben Sie die Argumente in der gleichen Reihenfolge, die `Function` -Prozedur die entsprechenden Parameter definiert.  
  
     Alternativ können Sie ein oder mehrere Argumente nach Namen übergeben. Weitere Informationen finden Sie unter [übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md).  
  
4.  Der von der Prozedur zurückgegebene Wert ist Teil des Ausdrucks ebenso wie der Wert einer Variablen oder Konstante.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>Zum Aufrufen einer Funktionsprozedur in eine Zuweisung  
  
1.  Verwenden der `Function` Name der Prozedur nach dem Gleichheitszeichen (`=`) melden Sie sich bei der Zuweisung.  
  
2.  Führen Sie den Namen der Prozedur mit Klammern um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern auch weglassen. Allerdings vereinfacht die Verwendung der Klammern Code leichter zu lesen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt. Stellen Sie sicher, geben Sie die Argumente in der Reihenfolge, die `Function` Prozedur die entsprechenden Parameter definiert, es sei denn, Sie über den Namen übergeben werden.  
  
4.  Der von der Prozedur zurückgegebene Wert ist in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A>zum Abrufen des Werts einer Betriebssystem-Umgebungsvariablen.</xref:Microsoft.VisualBasic.Interaction.Environ%2A> Die erste Zeile ruft `Environ` innerhalb eines Ausdrucks und die zweite Zeile ruft sie in eine Zuweisung. `Environ`erfordert den Variablennamen als einziges Argument. Der Wert der Variablen zurückgegeben an den aufrufenden Code.  
  
 [!code-vb[VbVbcnProcedures&#7;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Function-Prozeduren](./function-procedures.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt](./how-to-create-a-procedure-that-returns-a-value.md)   
 [Gewusst wie: Zurückgeben eines Werts aus einer Prozedur](./how-to-return-a-value-from-a-procedure.md)   
 [Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md)
