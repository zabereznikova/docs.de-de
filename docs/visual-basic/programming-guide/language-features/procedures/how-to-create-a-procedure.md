---
title: 'Gewusst wie: Erstellen einer Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: a831814c18f97991fca8067f1c9c8e491da1b665
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344911"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Gewusst wie: Erstellen einer Prozedur (Visual Basic)

Sie schließen eine Prozedur zwischen einer Start Deklarations Anweisung (`Sub` oder `Function`) und einer Anweisung zum Beenden der Deklaration (`End Sub` oder `End Function`) ein. Der gesamte Code der Prozedur liegt zwischen diesen Anweisungen.

 Eine Prozedur kann keine andere Prozedur enthalten, sodass Ihre Start-und End-Anweisungen außerhalb anderer Prozeduren liegen müssen.

 Wenn Sie über Code verfügen, mit dem dieselbe Aufgabe an unterschiedlichen Stellen durchführt, können Sie die Aufgabe einmal als Prozedur schreiben und Sie dann von unterschiedlichen Stellen im Code aus aufzurufen.

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>So erstellen Sie eine Prozedur, die keinen Wert zurückgibt

1. Verwenden Sie außerhalb einer anderen Prozedur eine `Sub`-Anweisung, gefolgt von einer `End Sub`-Anweisung.

2. Befolgen Sie in der `Sub`-Anweisung das `Sub`-Schlüsselwort mit dem Namen der Prozedur und der Parameterliste in Klammern.

3. Platzieren Sie die Code Anweisungen der Prozedur zwischen den Anweisungen `Sub` und `End Sub`.

### <a name="to-create-a-procedure-that-returns-a-value"></a>So erstellen Sie eine Prozedur, die einen Wert zurückgibt

1. Verwenden Sie außerhalb einer anderen Prozedur eine `Function`-Anweisung, gefolgt von einer `End Function`-Anweisung.

2. Befolgen Sie in der `Function`-Anweisung das `Function`-Schlüsselwort mit dem Namen der Prozedur, anschließend die Parameterliste in Klammern und dann eine `As`-Klausel, die den Datentyp des Rückgabewerts angibt.

3. Platzieren Sie die Code Anweisungen der Prozedur zwischen den Anweisungen `Function` und `End Function`.

4. Verwenden Sie eine `Return`-Anweisung, um den Wert an den aufrufenden Code zurückzugeben.

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>So verbinden Sie die neue Prozedur mit den alten, sich wiederholenden Code Blöcken

1. Stellen Sie sicher, dass Sie die neue Prozedur an einem Ort definieren, an dem der alte Code darauf zugreifen kann.

2. Ersetzen Sie in Ihrem alten, sich wiederholenden Codeblock die-Anweisungen, die die wiederkehrende Aufgabe ausführen, durch eine einzelne Anweisung, die die `Sub` oder `Function` Prozedur aufruft.

3. Wenn die Prozedur ein `Function` ist, der einen Wert zurückgibt, stellen Sie sicher, dass die aufrufende Anweisung eine Aktion mit dem zurückgegebenen Wert ausführt, z. b. Wenn Sie in einer Variablen gespeichert wird, oder wenn der Wert verloren geht.

## <a name="example"></a>Beispiel

 Mit der folgenden `Function` Prozedur wird die längste Seite (Hypotenuse) eines rechten Dreiecks berechnet, wobei die Werte für die beiden anderen Seiten berücksichtigt werden:

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
