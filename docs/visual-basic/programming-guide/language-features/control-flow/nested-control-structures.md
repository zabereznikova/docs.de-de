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
ms.openlocfilehash: 539ad639320615c1e53176fe47e5468864aa21d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414388"
---
# <a name="nested-control-structures-visual-basic"></a>Geschachtelte Steuerungsstrukturen (Visual Basic)
Sie können Steuerungs Anweisungen in andere Steuerungs Anweisungen einfügen, z. b `If...Then...Else` . einen-Block in einer- `For...Next` Schleife. Eine in einer anderen Steuerelement Anweisung *positionierte*Steuerelement Anweisung wird als geschachtelt bezeichnet.  
  
## <a name="nesting-levels"></a>Schachtelungs Ebenen  
 Steuerungsstrukturen in Visual Basic können beliebig viele Ebenen aufweisen. Es ist üblich, dass Sie die lesbaren Strukturen besser lesbar machen, indem Sie den Text der einzelnen einrücken. Der integrierte Entwicklungsumgebung (IDE)-Editor führt dies automatisch aus.  
  
 Im folgenden Beispiel fügt die Prozedur `sumRows` die positiven Elemente der einzelnen Zeilen der Matrix hinzu.  
  
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
  
 Im vorherigen Beispiel schließt die erste `Next` Anweisung die innere Schleife, `For` und die letzte `Next` Anweisung schließt die äußere `For` Schleife.  
  
 Entsprechend werden die Anweisungen in den-Anweisungen `If` `End If` automatisch auf die nächste vorherige- `If` Anweisung angewendet. Nested `Do` Loops funktionieren in ähnlicher Weise, wobei die innerste- `Loop` Anweisung mit der innersten-Anweisung übereinstimmt `Do` .  
  
> [!NOTE]
> Wenn Sie für viele Steuerungsstrukturen auf ein Schlüsselwort klicken, werden alle Schlüsselwörter in der Struktur hervorgehoben. Wenn Sie beispielsweise auf `If` eine Konstruktion klicken `If...Then...Else` , werden alle Instanzen von `If` , `Then` , `ElseIf` , `Else` und `End If` in der Konstruktion hervorgehoben. Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu wechseln, drücken Sie STRG + UMSCHALT + nach-unten oder STRG + UMSCHALT + nach-oben-Taste.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Schachteln verschiedener Arten von Steuerungsstrukturen  
 Sie können eine Art von Steuerelement Struktur in einer anderen Art Schachteln. Im folgenden Beispiel wird ein `With` -Block innerhalb einer `For Each` -Schleife und geschachtelte `If` Blöcke innerhalb des- `With` Blocks verwendet.  
  
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
 Sie können die Steuerelement Strukturen nicht überlappen. Dies bedeutet, dass jede geschachtelte Struktur vollständig in der nächsten innersten Struktur enthalten sein muss. Beispielsweise ist die folgende Anordnung ungültig, da die- `For` Schleife beendet wird, bevor der innere- `With` Block beendet wird.  
  
 ![Das Diagramm zeigt ein Beispiel für eine ungültige Schachtelung.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 Der Visual Basic-Compiler erkennt solche überlappenden Steuerungsstrukturen und signalisiert einen Kompilierzeitfehler.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablauf Steuerung](index.md)
- [Entscheidungsstrukturen](decision-structures.md)
- [Schleifenstrukturen](loop-structures.md)
- [Weitere Steuerungsstrukturen](other-control-structures.md)
