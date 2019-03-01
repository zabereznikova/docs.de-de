---
title: 'Vorgehensweise: Erstellen Sie eine Prozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 0f3b0a793b2751b0ec9bb2b7cd6fedc12ae19e18
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970804"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Vorgehensweise: Erstellen Sie eine Prozedur (Visual Basic)
Schließen Sie eine Prozedur zwischen einer deklarationsanweisung ab (`Sub` oder `Function`) und eine abschließende deklarationsanweisung (`End Sub` oder `End Function`). Alle der Prozedur bei der Code liegt zwischen Anweisungen.  
  
 Eine Prozedur kann nicht einer anderen Prozedur enthalten, damit die Anfangs- und Endposition Anweisungen außerhalb einer anderen Prozedur sein müssen.  
  
 Wenn Sie über Code, die an verschiedenen Positionen in die gleiche Aufgabe ausführt verfügen, können Sie die Aufgabe einmal als Prozedur schreiben, und rufen es dann aus unterschiedlichen Quellen in Ihrem Code.  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>Zum Erstellen einer Prozedur, die keinen Wert zurückgibt  
  
1.  Verwendung außerhalb anderer Prozeduren ein `Sub` -Anweisung, gefolgt von einer `End Sub` Anweisung.  
  
2.  In der `Sub` -Anweisung, führen Sie die `Sub` Schlüsselwort durch den Namen der Prozedur, und klicken Sie dann auf die Parameterliste in Klammern angegeben.  
  
3.  Platzieren Sie Anweisungen von der Prozedur bei der Code zwischen den `Sub` und `End Sub` Anweisungen.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Zum Erstellen einer Prozedur, die einen Wert zurückgibt.  
  
1.  Verwendung außerhalb anderer Prozeduren ein `Function` -Anweisung, gefolgt von einer `End Function` Anweisung.  
  
2.  In der `Function` -Anweisung, führen Sie die `Function` Schlüsselwort durch den Namen der Prozedur, und klicken Sie dann auf die Parameterliste in Klammern ein, und klicken Sie dann eine `As` -Klausel, die den Datentyp des Rückgabewerts angibt.  
  
3.  Platzieren Sie Anweisungen von der Prozedur bei der Code zwischen den `Function` und `End Function` Anweisungen.  
  
4.  Verwenden einer `Return` -Anweisung den Wert an den aufrufenden Code zurückgegeben.  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>Ihre neue Prozedur mit der alten, sich wiederholenden Codeblöcke verbinden  
  
1.  Stellen Sie sicher, dass Sie die neue Prozedur an einer Stelle definieren, in denen der alte Code darauf zugreifen kann.  
  
2.  Ersetzen Sie in Ihrer alten, sich wiederholenden Codeblock, die Anweisungen, die die sich wiederholende Aufgabe mit einer einzigen Anweisung ausführen, die Aufrufe der `Sub` oder `Function` Verfahren.  
  
3.  Wenn die Prozedur ist eine `Function` , die einen Wert zurückgibt, stellen Sie sicher, dass die aufrufende Anweisung führt eine Aktion mit dem zurückgegebenen Wert, z. B. in einer Variablen speichern oder andernfalls der Wert verloren.  
  
## <a name="example"></a>Beispiel  
 Die folgenden `Function` Prozedur berechnet werden, die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, anhand der Werte der beiden anderen Seiten.  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Function-Prozeduren](./function-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Rekursive Prozeduren](./recursive-procedures.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Objektorientierte Programmierung (Visual Basic)](../../concepts/object-oriented-programming.md)
