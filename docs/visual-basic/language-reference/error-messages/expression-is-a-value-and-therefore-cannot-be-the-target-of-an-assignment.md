---
title: Der Ausdruck ist ein Wert und kann nicht als Ziel einer Zuweisung verwendet werden
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: 9e4dbaf2f2800454c673cd58ddec4cf0f6e5c6b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409506"
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

**Indirekter Zugriff.** Dieser Fehler kann auch durch indirekten Zugriff durch einen Werttyp generiert werden. Sehen Sie sich das folgende Codebeispiel an, das versucht, den Wert von festzulegen, <xref:System.Drawing.Point> indem Sie indirekt über darauf zugreifen <xref:System.Windows.Forms.Control.Location%2A> .

```vb
' Assume this code runs inside Form1.
Dim exitButton As New System.Windows.Forms.Button()
exitButton.Text = "Exit this form"
exitButton.Location.X = 140
' The preceding line is an ERROR because of no storage for Location.
```

Die letzte Anweisung des vorangehenden Beispiels schlägt fehl, da Sie nur eine temporäre Zuordnung für die-Struktur erstellt, die <xref:System.Drawing.Point> von der-Eigenschaft zurückgegeben wird <xref:System.Windows.Forms.Control.Location%2A> . Eine Struktur ist ein Werttyp, und die temporäre Struktur wird nicht beibehalten, nachdem die Anweisung ausgeführt wurde. Das Problem wird durch Deklarieren und Verwenden einer Variablen für gelöst <xref:System.Windows.Forms.Control.Location%2A> , wodurch eine permanente Zuordnung für die Struktur erstellt wird <xref:System.Drawing.Point> . Das folgende Beispiel zeigt Code, der die letzte-Anweisung des vorangehenden Beispiels ersetzen kann.

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

## <a name="see-also"></a>Weitere Informationen

- [Operatoren und Ausdrücke](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Anweisungen](../../programming-guide/language-features/statements.md)
- [Problembehandlung bei Prozeduren](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
