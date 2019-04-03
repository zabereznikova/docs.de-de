---
title: 'Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: ee80ae48a9b9bfae0afe8f0a2c6e7ebf047d9d36
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820385"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt (Visual Basic)
Ein `Function` Prozedur gibt einen Wert an den aufrufenden Code zurück. Rufen Sie sie einschließlich der Namen und die Argumente entweder auf der rechten Seite einer zuweisungsanweisung oder in einem Ausdruck.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>Um eine Funktion innerhalb eines Ausdrucks aufzurufen  
  
1.  Verwenden Sie die `Function` Prozedur benennen Sie die gleiche Weise verwenden Sie eine Variable. Sie können eine `Function` Prozedur aufrufen anywhere können Sie eine Variable oder Konstante in einem Ausdruck.  
  
2.  Führen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen. Allerdings wird bei der Klammern verwenden die Ihr Code einfacher zu lesen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein. Werden Sie sicher, dass Sie die Argumente in der gleichen Reihenfolge angeben, die die `Function` Prozedur definiert, die entsprechenden Parameter.  
  
     Alternativ können Sie ein oder mehrere Argumente anhand des Namens übergeben. Weitere Informationen finden Sie unter [übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md).  
  
4.  Der von der Prozedur zurückgegebene Wert ist Teil des Ausdrucks ebenso wie der Wert einer Variablen oder Konstanten würde.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>Um eine Funktion in einer zuweisungsanweisung aufzurufen  
  
1.  Verwenden der `Function` Prozedurnamen folgen den Gleichheitsoperator (`=`) melden Sie sich die zuweisungsanweisung.  
  
2.  Führen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen. Allerdings wird bei der Klammern verwenden die Ihr Code einfacher zu lesen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein. Werden Sie sicher, dass Sie die Argumente in der gleichen Reihenfolge angeben, die die `Function` Prozedur definiert die entsprechenden Parameter, es sei denn, Sie über den Namen übergeben werden.  
  
4.  Der von der Prozedur zurückgegebene Wert ist in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> zum Abrufen des Werts einer Betriebssystem-Umgebungsvariablen. Die erste Zeile ruft `Environ` in einen Ausdruck ein, und die zweite Zeile ruft es in einer zuweisungsanweisung. `Environ` akzeptiert den Namen den Variablen als einziges Argument. Der Wert der Variablen zurückgegeben an den aufrufenden Code.  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a>Siehe auch

- [Function-Prozeduren](./function-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Vorgehensweise: Erstellen Sie eine Prozedur, die einen Wert zurückgibt.](./how-to-create-a-procedure-that-returns-a-value.md)
- [Vorgehensweise: Zurückgeben eines Werts aus einer Prozedur](./how-to-return-a-value-from-a-procedure.md)
- [Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md)
