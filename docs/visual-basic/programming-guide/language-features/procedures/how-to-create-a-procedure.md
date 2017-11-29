---
title: 'Gewusst wie: Erstellen einer Prozedur (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 56a44918b7a1426d215cee0ff2981f5763432a48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Gewusst wie: Erstellen einer Prozedur (Visual Basic)
Sie setzen eine Prozedur zwischen einer Start-deklarationsanweisung (`Sub` oder `Function`) und ein Enddatum deklarationsanweisung (`End Sub` oder `End Function`). Alle Prozedur Code liegt zwischen diesen Anweisungen.  
  
 Eine Prozedur kann nicht einer anderen Prozedur enthalten, damit die Start- und Enddatum Anweisungen außerhalb eine beliebige andere Prozedur sein müssen.  
  
 Wenn Sie über Code, die an verschiedenen Positionen in die gleiche Aufgabe ausführt verfügen, können Sie die Aufgabe einmal als Prozedur schreiben, und von unterschiedlichen Stellen im Code aufrufen.  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>So erstellen Sie eine Prozedur, die keinen Wert zurückgibt  
  
1.  Außerhalb eine beliebige andere Prozedur verwendet eine `Sub` Anweisung, gefolgt von einem `End Sub` Anweisung.  
  
2.  In der `Sub` -Anweisung, befolgen Sie die `Sub` Schlüsselwort mit dem Namen der Prozedur, und klicken Sie dann auf die Parameterliste in Klammern.  
  
3.  Platzieren Sie die Prozedur codeanweisungen zwischen der `Sub` und `End Sub` Anweisungen.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>So erstellen Sie eine Prozedur, die einen Wert zurückgibt  
  
1.  Außerhalb eine beliebige andere Prozedur verwendet eine `Function` Anweisung, gefolgt von einem `End Function` Anweisung.  
  
2.  In der `Function` -Anweisung, befolgen Sie die `Function` Schlüsselwort mit dem Namen der Prozedur, und klicken Sie dann auf die Parameterliste in Klammern ein, und klicken Sie dann eine `As` -Klausel, in den Datentyp des Rückgabewerts.  
  
3.  Platzieren Sie die Prozedur codeanweisungen zwischen der `Function` und `End Function` Anweisungen.  
  
4.  Verwenden einer `Return` -Anweisung den Wert an den aufrufenden Code zurückgegeben.  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>Eine neue Prozedur mit alten, wiederkehrende Codeblöcke verbinden  
  
1.  Stellen Sie sicher, dass Sie die neue Prozedur an einer Stelle definieren, in denen der alte Code kann zugreifen.  
  
2.  Ersetzen Sie in Ihrer alten, wiederkehrende Codeblock, der Anweisungen, die sich wiederholende Aufgabe mit einer einzigen Anweisung durchführen, die aufruft der `Sub` oder `Function` Prozedur.  
  
3.  Wenn die Prozedur ist eine `Function` , die einen Wert zurückgibt, stellen Sie sicher, dass die aufrufende Anweisung führt eine Aktion mit dem zurückgegebenen Wert, z. B. in einer Variablen speichern, sonst wird der Wert verloren.  
  
## <a name="example"></a>Beispiel  
 Die folgenden `Function` Prozedur berechnet die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, anhand der Werte der beiden anderen Seiten.  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Sub-Prozeduren](./sub-procedures.md)  
 [Function-Prozeduren](./function-procedures.md)  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Operatorprozeduren](./operator-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Rekursive Prozeduren](./recursive-procedures.md)  
 [Prozedurüberladung](./procedure-overloading.md)  
 [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Objektorientierte Programmierung](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
