---
title: 'Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 53589f84c6675d1e7ae2a593341e5dac747132a9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083976"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt (Visual Basic)

Eine `Function` Prozedur gibt einen Wert an den aufrufenden Code zurück. Sie werden aufgerufen, indem Sie den Namen und die Argumente entweder auf der rechten Seite einer Zuweisungsanweisung oder in einem Ausdruck einschließen.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>So greifen Sie eine Funktions Prozedur innerhalb eines Ausdrucks an  
  
1. Verwenden `Function` Sie den Prozedur Namen auf dieselbe Weise wie eine Variable. Sie können einen `Function` Prozedur aufrufen überall dort verwenden, wo Sie eine Variable oder Konstante in einem Ausdruck verwenden können.  
  
2. Befolgen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einzuschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen. Durch die Verwendung der Klammern wird der Code jedoch leichter lesbar.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas. Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die `Function` Prozedur die entsprechenden Parameter definiert.  
  
     Alternativ können Sie ein oder mehrere Argumente nach Namen übergeben. Weitere Informationen finden Sie unter [übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md).  
  
4. Der Wert, der von der-Prozedur zurückgegeben wird, nimmt genauso an, wie der Wert einer Variablen oder Konstanten.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>So greifen Sie eine Funktions Prozedur in einer Zuweisungsanweisung an  
  
1. Verwenden Sie den `Function` Namen der Prozedur nach dem Gleichheits `=` Zeichen () in der Zuweisungsanweisung.  
  
2. Befolgen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einzuschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen. Durch die Verwendung der Klammern wird der Code jedoch leichter lesbar.  
  
3. Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas. Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge angeben, in der die `Function` Prozedur die entsprechenden Parameter definiert, es sei denn, Sie übergeben Sie nach Namen.  
  
4. Der von der Prozedur zurückgegebene Wert wird in der Variablen oder der Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird der Visual Basic aufgerufen <xref:Microsoft.VisualBasic.Interaction.Environ%2A> , um den Wert einer Betriebssystem-Umgebungsvariablen abzurufen. Die erste Zeile ruft `Environ` innerhalb eines Ausdrucks auf, und die zweite Zeile ruft Sie in einer Zuweisungsanweisung auf. `Environ` nimmt den Variablennamen als das einzige Argument an. Der Wert der Variablen wird an den aufrufenden Code zurückgegeben.  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a>Siehe auch

- [Function-Prozeduren](./function-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Function-Anweisung](../../../language-reference/statements/function-statement.md)
- [Vorgehensweise: Erstellen einer Prozedur, die einen Wert zurückgibt](./how-to-create-a-procedure-that-returns-a-value.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Prozedur](./how-to-return-a-value-from-a-procedure.md)
- [Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md)
