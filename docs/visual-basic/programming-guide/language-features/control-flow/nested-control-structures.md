---
title: "Nested Control Structures (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, control flow"
  - "control structures, nested"
  - "conditional statements, nested"
  - "statements [Visual Basic], control flow"
  - "control flow, nested control statements"
  - "structures, nested control"
  - "nested control statements"
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Nested Control Structures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Sie können Steuerungsanweisungen in andere Steuerungsanweisungen einfügen, wie z. B. einen `If...Then...Else`\-Block in eine `For...Next`\-Schleife.  Eine Steuerungsanweisung, die in eine andere Steuerungsanweisung eingefügt wurde, ist *geschachtelt*.  
  
## Schachtelungsebenen  
 Steuerungsstrukturen in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] können auf beliebig vielen Ebenen geschachtelt werden.  Es ist üblich, geschachtelte Strukturen lesbarer zu machen, indem der Text jeder Struktur eingerückt wird.  Dies wird automatisch vom Editor der integrierten Entwicklungsumgebung \(IDE\) erledigt.  
  
 Im folgenden Beispiel addiert die `sumRows`\-Prozedur die positiven Elemente jeder Zeile der Matrix.  
  
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
  
 Im vorhergehenden Beispiel schließt die erste `Next`\-Anweisung die innere `For`\-Schleife und die letzte `Next`\-Anweisung die äußere `For`\-Schleife.  
  
 Gleichermaßen gelten in geschachtelten `If`\-Anweisungen die `End If`\-Anweisungen automatisch für die nächste vorangegangene `If`\-Anweisung.  Geschachtelte `Do`\-Schleifen funktionieren ähnlich, wobei die innerste `Loop`\-Anweisung mit der innersten `Do`\-Anweisung übereinstimmt.  
  
> [!NOTE]
>  Bei vielen Steuerungsstrukturen werden beim Klicken auf ein Schlüsselwort alle Schlüsselwörter der Struktur hervorgehoben.  Wenn Sie in einer `If...Then...Else`\-Konstruktion beispielsweise auf `If` klicken, werden in der Konstruktion alle Instanzen von `If`, `Then`, `ElseIf`, `Else` und `End If` hervorgehoben.  Um zum nächsten oder vorherigen markierten Schlüsselwort zu springen, drücken Sie STRG\+UMSCHALT\+NACH\-UNTEN bzw. STRG\+UMSCHALT\+NACH\-OBEN.  
  
## Schachteln von verschiedenen Arten von Steuerungsstrukturen  
 Sie können eine Art von Steuerungsstruktur innerhalb einer anderen Art schachteln.  Im folgenden Beispiel werden ein `With`\-Block in einer `For Each`\-Schleife und geschachtelte `If`\-Blöcke im `With`\-Block verwendet.  
  
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
  
## Überlappende Steuerungsstrukturen  
 Steuerungsstrukturen können nicht überlappen.  Das bedeutet, dass alle geschachtelten Strukturen vollständig in der nächsten inneren Struktur enthalten sein müssen.  Die folgende Anordnung ist beispielsweise ungültig, weil die `For`\-Schleife vor dem inneren `With`\-Block abgeschlossen wird.  
  
 ![Grafisches Diagramm einer ungültigen Schachtelung](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.png "NestExampleInvalid")  
Ungültige Schachtelung von For\- und With\-Strukturen  
  
 Der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler erkennt diese überlappenden Steuerungsstrukturen und signalisiert beim Kompilieren einen Fehler.  
  
## Siehe auch  
 [Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)