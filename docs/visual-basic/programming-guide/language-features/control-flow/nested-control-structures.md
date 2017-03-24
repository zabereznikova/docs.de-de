---
title: Geschachtelte Steuerungsstrukturen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, control flow
- control structures, nested
- conditional statements, nested
- statements [Visual Basic], control flow
- control flow, nested control statements
- structures, nested control
- nested control statements
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4afc0afc2ad63d03f2c4251640d3682b2b184504
ms.lasthandoff: 03/13/2017

---
# <a name="nested-control-structures-visual-basic"></a>Geschachtelte Steuerungsstrukturen (Visual Basic)
Sie fügen die Steueranweisungen in andere Steueranweisungen, z. B. ein `If...Then...Else` -Block in einer `For...Next` Schleife. Eine Steuerelement-Anweisung innerhalb einer anderen Steueranweisung platziert gilt als *geschachtelten*.  
  
## <a name="nesting-levels"></a>Schachteln von Ebenen  
 Steuerungsstrukturen in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] können geschachtelt werden, um so viele Ebenen wie gewünscht. Es ist üblich, geschachtelte Strukturen durch den Text jeder einzelnen einrücken besser lesbar zu machen. Integrierte Entwicklung Umgebung (IDE) Editor wird automatisch.  
  
 Im folgenden Beispiel, das Verfahren `sumRows` addiert die positiven Elemente jeder Zeile der Matrix.  
  
```  
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
  
 Im vorherigen Beispiel ist der erste `Next` Anweisung schließt die innere `For` -Schleife und die letzte `Next` Anweisung schließt die äußere `For` Schleife.  
  
 Ebenso in geschachtelten `If` -Anweisungen, die `End If` Aussagen gelten automatisch an den nächstgelegenen vorherigen `If` Anweisung. Geschachtelte `Do` -Schleifen funktionieren ähnlich, wobei die innerste `Loop` Anweisung entsprechen die innerste `Do` Anweisung.  
  
> [!NOTE]
>  Für viele Steuerungsstrukturen werden beim Klicken auf ein Schlüsselwort alle Schlüsselwörter in der Struktur hervorgehoben. Z. B. beim Klicken auf `If` in einer `If...Then...Else` Konstruktion, alle Instanzen von `If`, `Then`, `ElseIf`, `Else`, und `End If` bei der Erstellung werden hervorgehoben. Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu wechseln, drücken Sie STRG + UMSCHALT + nach-unten oder STRG + UMSCHALT + nach-oben-Taste.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Schachteln von verschiedenen Arten von Steuerungsstrukturen  
 Sie können eine Art von Steuerungsstruktur innerhalb einer anderen Art schachteln. Im folgenden Beispiel wird ein `With` -Block innerhalb einer `For Each` -Schleife und geschachtelte `If` blockiert innerhalb der `With` Block.  
  
```  
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
 Steuerungsstrukturen sich nicht überschneiden. Dies bedeutet, dass alle geschachtelten Strukturen vollständig innerhalb der nächsten inneren Struktur enthalten sein muss. Die folgende Anordnung ist beispielsweise ungültig da die `For` -Schleife vor dem inneren `With` Block beendet wird.  
  
 ![Grafisches Diagramm einer ungültigen Schachtelung](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")  
Ungültige Schachtelung von for- und Strukturen  
  
 Die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler erkennt diese überlappenden Steuerungsstrukturen und signalisiert einen Fehler während der Kompilierung.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Entscheidungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Weitere Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
