---
title: Geschachtelte Steuerungsstrukturen
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
ms.openlocfilehash: b696c79cd3cada4416b3f4b6cdf96f00b89a5a0a
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266923"
---
# <a name="nested-control-structures-visual-basic"></a>Geschachtelte Steuerungsstrukturen (Visual Basic)
Sie können Steueranweisungen in anderen Steueranweisungen `If...Then...Else` platzieren, `For...Next` z. B. in einem Block innerhalb einer Schleife. Eine Steueranweisung, die in einer anderen Steuerelementanweisung platziert wird, soll *geschachtelt*sein.  
  
## <a name="nesting-levels"></a>Nesting-Ebenen  
 Steuerelementstrukturen in Visual Basic können auf bedienen können, die Sie möchten. Es ist üblich, verschachtelte Strukturen lesbarer zu machen, indem sie den Körper jedes einzelnen einablehnen. Der IDE-Editor (Integrated Development Environment) tut dies automatisch.  
  
 Im folgenden Beispiel addiert die Prozedur `sumRows` die positiven Elemente jeder Zeile der Matrix.  
  
```vb
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 Im vorherigen Beispiel schließt `Next` die erste `For` Anweisung die `Next` innere Schleife und `For` die letzte Anweisung die äußere Schleife.  
  
 Ebenso gelten die `If` `End If` Anweisungen in geschachtelten Anweisungen `If` automatisch für die nächste vorherige Anweisung. Verschachtelte `Do` Schleifen funktionieren auf ähnliche Weise, `Loop` wobei die `Do` innerste Anweisung der innersten Anweisung entspricht.  
  
> [!NOTE]
> Wenn Sie bei vielen Steuerelementstrukturen auf ein Schlüsselwort klicken, werden alle Schlüsselwörter in der Struktur hervorgehoben. Wenn Sie beispielsweise `If` auf `If...Then...Else` eine Konstruktion klicken, werden `Else`alle `End If` Instanzen von `If`, `Then`, `ElseIf`, und in der Konstruktion hervorgehoben. Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu wechseln, drücken Sie STRG+UMSCHALT+DOWN ARROW oder STRG+UMSCHALT+UP ARROW.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Verschachteln verschiedener Arten von Steuerungsstrukturen  
 Sie können eine Art von Steuerelementstruktur innerhalb einer anderen Art verschachteln. Im folgenden Beispiel `With` wird `For Each` ein Block `If` innerhalb einer `With` Schleife und verschachtelte Blöcke innerhalb des Blocks verwendet.  
  
```vb
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a>Überlappende Steuerungsstrukturen  
 Sie können Steuerelementstrukturen nicht überlappen. Dies bedeutet, dass jede verschachtelte Struktur vollständig in der nächsten innersten Struktur enthalten sein muss. Die folgende Anordnung ist z. `For` B. ungültig, `With` da die Schleife beendet wird, bevor der innere Block beendet wird.  
  
 ![Diagramm, das ein Beispiel für ungültige Verschachtelung zeigt.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 Der Visual Basic-Compiler erkennt solche überlappenden Steuerungsstrukturen und signalisiert einen Kompilierungsfehler.  
  
## <a name="see-also"></a>Weitere Informationen

- [Kontrollfluss](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Entscheidungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Weitere Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
