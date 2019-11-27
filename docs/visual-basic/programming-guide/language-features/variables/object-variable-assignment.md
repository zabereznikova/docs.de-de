---
title: Zuweisen von Objektvariablen
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
ms.openlocfilehash: 93de17490935d6d5cad01000e9ee3e2fe55bd16c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351820"
---
# <a name="object-variable-assignment-visual-basic"></a>Zuweisen von Objektvariablen (Visual Basic)

Sie verwenden eine normale Zuweisungsanweisung, um ein Objekt einer Objektvariablen zuzuweisen. Sie können einen Objekt Ausdruck oder das [Nothing](../../../../visual-basic/language-reference/nothing.md) -Schlüsselwort zuweisen, wie im folgenden Beispiel veranschaulicht.

```vb
Dim thisObject As Object
' The following statement assigns an object reference.
thisObject = Form1
' The following statement discontinues association with any object.
thisObject = Nothing
```

`Nothing` bedeutet, dass der Variablen zurzeit kein-Objekt zugewiesen ist.

## <a name="initialization"></a>Initialisierung

Wenn Ihr Code gestartet wird, werden die Objektvariablen mit `Nothing`initialisiert. Diejenigen, deren Deklarationen die Initialisierung einschließen, werden auf die Werte, die Sie beim Ausführen der Deklarations Anweisungen angeben, erneut initialisiert.

Sie können die Initialisierung in die Deklaration einschließen, indem Sie das [New](../../../../visual-basic/language-reference/operators/new-operator.md) -Schlüsselwort verwenden. Die folgenden Deklarations Anweisungen deklarieren Objektvariablen `testUri` und `ver` und weisen Ihnen bestimmte Objekte zu. Jeder verwendet einen der überladenen Konstruktoren der entsprechenden-Klasse, um das Objekt zu initialisieren.

```vb
Dim testUri As New System.Uri("https://www.microsoft.com")
Dim ver As New System.Version(6, 1, 0)
```

## <a name="disassociation"></a>Aufhebung

Wenn eine Objekt Variable auf `Nothing` festgelegt wird, wird die Zuordnung der Variablen zu einem bestimmten Objekt aufgehoben. Dadurch wird verhindert, dass das Objekt versehentlich geändert wird, indem die Variable geändert wird. Außerdem können Sie überprüfen, ob die Objekt Variable auf ein gültiges Objekt verweist, wie im folgenden Beispiel gezeigt.

```vb
If otherObject IsNot Nothing Then
    ' otherObject refers to a valid object, so your code can use it.
End If
```

Wenn sich das Objekt, auf das sich Ihre Variable bezieht, in einer anderen Anwendung befindet, kann dieser Test nicht bestimmen, ob die Anwendung beendet wurde oder das Objekt nur für ungültig erklärt hat.

Eine Objekt Variable mit dem Wert `Nothing` wird auch als NULL- *Verweis*bezeichnet.

## <a name="current-instance"></a>Aktuelle Instanz

Die *aktuelle Instanz* eines Objekts ist die Instanz, in der der Code gerade ausgeführt wird. Da der gesamte Code innerhalb einer Prozedur ausgeführt wird, ist die aktuelle Instanz diejenige, in der die Prozedur aufgerufen wurde.

Das `Me`-Schlüsselwort fungiert als Objekt Variable, die auf die aktuelle Instanz verweist. Wenn eine Prozedur nicht frei [gegeben](../../../../visual-basic/language-reference/modifiers/shared.md)wird, kann Sie das `Me`-Schlüsselwort verwenden, um einen Zeiger auf die aktuelle Instanz zu erhalten. Freigegebene Prozeduren können nicht mit einer bestimmten Instanz einer Klasse verknüpft werden.

Die Verwendung von `Me` ist besonders nützlich, um die aktuelle Instanz an eine Prozedur in einem anderen Modul zu übergeben. Angenommen, Sie verfügen über eine Reihe von XML-Dokumenten und möchten allen Standardtext hinzufügen. Im folgenden Beispiel wird eine Vorgehensweise definiert.

```vb
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)
    XmlDoc.CreateTextNode("This text goes into every XML document.")
End Sub
```

Jedes XML-Dokument Objekt könnte dann die Prozedur aufzurufen und die aktuelle Instanz als Argument übergeben. Dies wird im folgenden Beispiel veranschaulicht:

```vb
addStandardText(Me)
```

## <a name="see-also"></a>Siehe auch

- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Gewusst wie: Deklarieren einer Objektvariablen und Zuweisen eines Objekts in Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [Gewusst wie: Entfernen aller Verweise einer Objektvariablen auf Instanzen](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
