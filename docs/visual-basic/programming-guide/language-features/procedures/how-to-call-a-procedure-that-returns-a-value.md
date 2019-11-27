---
title: 'Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 7f5d46babf31ea3c6babb29c0f1c08a23e51d598
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340733"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt (Visual Basic)
Eine `Function` Prozedur gibt einen Wert an den aufrufenden Code zurück. Sie werden aufgerufen, indem Sie den Namen und die Argumente entweder auf der rechten Seite einer Zuweisungsanweisung oder in einem Ausdruck einschließen.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>So greifen Sie eine Funktions Prozedur innerhalb eines Ausdrucks an  
  
1. Verwenden Sie den `Function` Prozedur Namen auf dieselbe Weise wie eine Variable. Sie können einen `Function` Prozedur aufrufen überall dort verwenden, wo Sie eine Variable oder Konstante in einem Ausdruck verwenden können.  
  
2. Befolgen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einzuschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen. Durch die Verwendung der Klammern wird der Code jedoch leichter lesbar.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas. Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die `Function` Prozedur die entsprechenden Parameter definiert.  
  
     Alternativ können Sie ein oder mehrere Argumente nach Namen übergeben. Weitere Informationen finden Sie unter [übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md).  
  
4. Der Wert, der von der-Prozedur zurückgegeben wird, nimmt genauso an, wie der Wert einer Variablen oder Konstanten.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>So greifen Sie eine Funktions Prozedur in einer Zuweisungsanweisung an  
  
1. Verwenden Sie den Namen der `Function` Prozedur nach dem Gleichheitszeichen (`=`) in der Zuweisungsanweisung.  
  
2. Befolgen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einzuschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen. Durch die Verwendung der Klammern wird der Code jedoch leichter lesbar.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas. Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die `Function` Prozedur die entsprechenden Parameter definiert, es sei denn, Sie übergeben Sie nach Namen.  
  
4. Der von der Prozedur zurückgegebene Wert wird in der Variablen oder der Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> aufgerufen, um den Wert einer Betriebssystem-Umgebungsvariablen abzurufen. Die erste Zeile ruft `Environ` innerhalb eines Ausdrucks auf, und die zweite Zeile ruft Sie in einer Zuweisungsanweisung auf. `Environ` nimmt den Variablennamen als das einzige Argument an. Der Wert der Variablen wird an den aufrufenden Code zurückgegeben.  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a>Siehe auch

- [Function-Prozeduren](./function-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt](./how-to-create-a-procedure-that-returns-a-value.md)
- [Gewusst wie: Abrufen eines Werts aus einer Prozedur](./how-to-return-a-value-from-a-procedure.md)
- [Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md)
