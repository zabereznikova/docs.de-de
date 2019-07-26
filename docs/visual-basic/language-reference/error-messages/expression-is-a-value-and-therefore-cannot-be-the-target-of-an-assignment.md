---
title: Der Ausdruck ist ein Wert und kann nicht als Ziel einer Zuweisung verwendet werden
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: d5aae4d30abbf9ed2af260412352a5e0452e0dcc
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513034"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a>Der Ausdruck ist ein Wert und kann nicht als Ziel einer Zuweisung verwendet werden

Eine Anweisung versucht, einem Ausdruck einen Wert zuzuweisen. Sie können einen Wert nur einer beschreibbaren Variablen, einer Eigenschaft oder einem Array Element zur Laufzeit zuweisen. Im folgenden Beispiel wird veranschaulicht, wie dieser Fehler auftreten kann.

```vb
Dim yesterday As Integer
ReadOnly maximum As Integer = 45
yesterday + 1 = DatePart(DateInterval.Day, Now)
' The preceding line is an ERROR because of an expression on the left.
maximum = 50
' The preceding line is an ERROR because maximum is declared ReadOnly.
```

Ähnliche Beispiele können auf Eigenschaften und Array Elemente angewendet werden.

**Indirekter Zugriff.** Dieser Fehler kann auch durch indirekten Zugriff durch einen Werttyp generiert werden. Sehen Sie sich das folgende Codebeispiel an, das versucht, den <xref:System.Drawing.Point> Wert von festzulegen, <xref:System.Windows.Forms.Control.Location%2A>indem Sie indirekt über darauf zugreifen.

```vb
' Assume this code runs inside Form1.
Dim exitButton As New System.Windows.Forms.Button()
exitButton.Text = "Exit this form"
exitButton.Location.X = 140
' The preceding line is an ERROR because of no storage for Location.
```

Die letzte Anweisung des vorangehenden Beispiels schlägt fehl, da Sie nur eine temporäre Zuordnung für <xref:System.Drawing.Point> die-Struktur erstellt <xref:System.Windows.Forms.Control.Location%2A> , die von der-Eigenschaft zurückgegeben wird. Eine Struktur ist ein Werttyp, und die temporäre Struktur wird nicht beibehalten, nachdem die Anweisung ausgeführt wurde. Das Problem wird durch Deklarieren und Verwenden einer Variablen für <xref:System.Windows.Forms.Control.Location%2A>gelöst, wodurch eine permanente Zuordnung für die <xref:System.Drawing.Point> Struktur erstellt wird. Das folgende Beispiel zeigt Code, der die letzte-Anweisung des vorangehenden Beispiels ersetzen kann.

```vb
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)
exitButton.Location = exitLocation
```

**Fehler-ID:** BC30068

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Wenn die Anweisung einem Ausdruck einen Wert zuweist, ersetzen Sie den Ausdruck durch eine einzelne beschreibbare Variable, eine Eigenschaft oder ein Array Element.

- Wenn die Anweisung indirekten Zugriff über einen Werttyp (in der Regel eine Struktur) gewährt, erstellen Sie eine Variable, die den Werttyp enthält.

- Weisen Sie der Variablen die entsprechende Struktur (oder einen anderen Werttyp) zu.

- Verwenden Sie die-Variable, um auf die-Eigenschaft zuzugreifen, um ihr einen Wert zuzuweisen.

## <a name="see-also"></a>Siehe auch

- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
- [Problembehandlung bei Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
