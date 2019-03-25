---
title: Geschachtelte Steuerungsstrukturen (Visual Basic)
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
ms.openlocfilehash: 13e2c5c8d818a09ec5e77ec47fe8a2c83b675d82
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409795"
---
# <a name="nested-control-structures-visual-basic"></a>Geschachtelte Steuerungsstrukturen (Visual Basic)
Können Sie die Anweisungen in anderen Anweisungen, z. B. Platzieren einer `If...Then...Else` -Block in einem `For...Next` Schleife. Eine steuerungsanweisung, die in einer anderen Kontrollmaßnahme platziert gilt als *geschachtelte*.  
  
## <a name="nesting-levels"></a>Schachtelungsebenen  
 Steuerungsstrukturen in Visual Basic können geschachtelt werden, um so viele Ebenen wie gewünscht. Es ist üblich, geschachtelte Strukturen besser lesbar zu machen, durch den Text der einzelnen einrücken. Der integrated Development Environment (IDE)-Editor wird automatisch.  
  
 Im folgenden Beispiel, das Verfahren `sumRows` gemeinsam positive Elemente von jeder Zeile der Matrix hinzugefügt.  
  
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
  
 Im vorherigen Beispiel ist die erste `Next` Anweisung schließt die innere `For` -Schleife und die letzte `Next` Anweisung schließt die äußere `For` Schleife.  
  
 Auch in geschachtelten `If` -Anweisungen, die `End If` Anweisungen gelten automatisch auf die nächste vor `If` Anweisung. Geschachtelte `Do` Schleifen funktionieren auf ähnliche Weise, mit der innersten `Loop` Anweisung, die die innerste übereinstimmende `Do` Anweisung.  
  
> [!NOTE]
>  Für viele Steuerungsstrukturen Wenn Sie ein Schlüsselwort, klicken Sie auf werden alle Schlüsselwörter in der Struktur hervorgehoben. Z. B. beim Klicken auf `If` in einer `If...Then...Else` Konstruktion, die alle Instanzen von `If`, `Then`, `ElseIf`, `Else`, und `End If` bei der Erstellung werden hervorgehoben. Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu verschieben, drücken Sie STRG + UMSCHALT + nach-unten oder STRG + UMSCHALT + nach-oben-Taste.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Verschiedene Arten von Steuerungsstrukturen schachteln  
 Sie können eine bestimmte Art von Steuerelement-Struktur in eine andere Art schachteln. Im folgenden Beispiel wird eine `With` -Block in einer `For Each` -Schleife und geschachtelte `If` blockiert, die innerhalb der `With` Block.  
  
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
 Steuerungsstrukturen sich nicht überschneiden. Dies bedeutet, dass alle geschachtelten Strukturen vollständig innerhalb der nächsten innere Struktur enthalten sein muss. Z. B. die folgende Anordnung ist ungültig. da die `For` -Schleife wird beendet, bevor Sie die innere `With` Block beendet wird.  
  
 ![Diagramm ein Beispiel einer ungültigen Schachtelung zeigt.](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 Visual Basic-Compiler erkennt diese überlappende Steuerungsstrukturen und signalisiert einen Fehler während der Kompilierung.  
  
## <a name="see-also"></a>Siehe auch
- [Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Entscheidungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Weitere Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
