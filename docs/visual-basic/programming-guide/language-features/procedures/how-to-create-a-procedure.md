---
title: 'Vorgehensweise: Erstellen einer Prozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 2cf4c788ec421c1e74ef7198496a92149e049752
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216722"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Vorgehensweise: Erstellen einer Prozedur (Visual Basic)

Sie schließen eine Prozedur zwischen einer Anweisung zum Starten der Deklaration `Function`(`Sub` oder) und einer endedeklarations Anweisung (`End Sub` oder `End Function`) ein. Der gesamte Code der Prozedur liegt zwischen diesen Anweisungen.

 Eine Prozedur kann keine andere Prozedur enthalten, sodass Ihre Start-und End-Anweisungen außerhalb anderer Prozeduren liegen müssen.

 Wenn Sie über Code verfügen, mit dem dieselbe Aufgabe an unterschiedlichen Stellen durchführt, können Sie die Aufgabe einmal als Prozedur schreiben und Sie dann von unterschiedlichen Stellen im Code aus aufzurufen.

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>So erstellen Sie eine Prozedur, die keinen Wert zurückgibt

1. Verwenden Sie außerhalb einer anderen Prozedur eine `Sub` -Anweisung, gefolgt von `End Sub` einer-Anweisung.

2. Befolgen Sie `Sub` in der-Anweisung `Sub` das-Schlüsselwort mit dem Namen der Prozedur und der Parameterliste in Klammern.

3. Platzieren Sie die Code Anweisungen der Prozedur zwischen `Sub` der `End Sub` -Anweisung und der-Anweisung.

### <a name="to-create-a-procedure-that-returns-a-value"></a>So erstellen Sie eine Prozedur, die einen Wert zurückgibt

1. Verwenden Sie außerhalb einer anderen Prozedur eine `Function` -Anweisung, gefolgt von `End Function` einer-Anweisung.

2. Befolgen Sie `Function` in der-Anweisung `Function` das-Schlüsselwort mit dem Namen der Prozedur, anschließend die Parameterliste in Klammern und eine `As` -Klausel, die den Datentyp des Rückgabewerts angibt.

3. Platzieren Sie die Code Anweisungen der Prozedur zwischen `Function` der `End Function` -Anweisung und der-Anweisung.

4. Verwenden Sie `Return` eine-Anweisung, um den Wert an den aufrufenden Code zurückzugeben.

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>So verbinden Sie die neue Prozedur mit den alten, sich wiederholenden Code Blöcken

1. Stellen Sie sicher, dass Sie die neue Prozedur an einem Ort definieren, an dem der alte Code darauf zugreifen kann.

2. Ersetzen Sie in Ihrem alten, sich wiederholenden Codeblock die-Anweisungen, die die wiederkehrende Aufgabe ausführen, durch `Sub` eine `Function` einzelne Anweisung, die die-oder-Prozedur aufruft.

3. Wenn Ihre Prozedur eine `Function` ist, die einen Wert zurückgibt, stellen Sie sicher, dass die aufrufende Anweisung eine Aktion mit dem zurückgegebenen Wert ausführt, z. b. Wenn Sie in einer Variablen gespeichert wird. Andernfalls geht der Wert verloren.

## <a name="example"></a>Beispiel

 Im folgenden `Function` Verfahren wird die längste Seite (Hypotenuse) eines Rechts Dreiecks berechnet, wobei die Werte für die beiden anderen Seiten berücksichtigt werden:

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a>Siehe auch

- [Verfahren](index.md)
- [Sub-Prozeduren](sub-procedures.md)
- [Function-Prozeduren](function-procedures.md)
- [Eigenschaftenprozeduren](property-procedures.md)
- [Operatorprozeduren](operator-procedures.md)
- [Parameter und Argumente von Prozeduren](procedure-parameters-and-arguments.md)
- [Rekursive Prozeduren](recursive-procedures.md)
- [Prozedurüberladung](procedure-overloading.md)
- [Objekte und Klassen](../objects-and-classes/index.md)
- [Objektorientierte Programmierung (Visual Basic)](../../concepts/object-oriented-programming.md)
