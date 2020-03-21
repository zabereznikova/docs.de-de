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
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="821e6-102">Geschachtelte Steuerungsstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="821e6-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="821e6-103">Sie können Steueranweisungen in anderen Steueranweisungen `If...Then...Else` platzieren, `For...Next` z. B. in einem Block innerhalb einer Schleife.</span><span class="sxs-lookup"><span data-stu-id="821e6-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="821e6-104">Eine Steueranweisung, die in einer anderen Steuerelementanweisung platziert wird, soll *geschachtelt*sein.</span><span class="sxs-lookup"><span data-stu-id="821e6-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="821e6-105">Nesting-Ebenen</span><span class="sxs-lookup"><span data-stu-id="821e6-105">Nesting Levels</span></span>  
 <span data-ttu-id="821e6-106">Steuerelementstrukturen in Visual Basic können auf bedienen können, die Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="821e6-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="821e6-107">Es ist üblich, verschachtelte Strukturen lesbarer zu machen, indem sie den Körper jedes einzelnen einablehnen.</span><span class="sxs-lookup"><span data-stu-id="821e6-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="821e6-108">Der IDE-Editor (Integrated Development Environment) tut dies automatisch.</span><span class="sxs-lookup"><span data-stu-id="821e6-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="821e6-109">Im folgenden Beispiel addiert die Prozedur `sumRows` die positiven Elemente jeder Zeile der Matrix.</span><span class="sxs-lookup"><span data-stu-id="821e6-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="821e6-110">Im vorherigen Beispiel schließt `Next` die erste `For` Anweisung die `Next` innere Schleife und `For` die letzte Anweisung die äußere Schleife.</span><span class="sxs-lookup"><span data-stu-id="821e6-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="821e6-111">Ebenso gelten die `If` `End If` Anweisungen in geschachtelten Anweisungen `If` automatisch für die nächste vorherige Anweisung.</span><span class="sxs-lookup"><span data-stu-id="821e6-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="821e6-112">Verschachtelte `Do` Schleifen funktionieren auf ähnliche Weise, `Loop` wobei die `Do` innerste Anweisung der innersten Anweisung entspricht.</span><span class="sxs-lookup"><span data-stu-id="821e6-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="821e6-113">Wenn Sie bei vielen Steuerelementstrukturen auf ein Schlüsselwort klicken, werden alle Schlüsselwörter in der Struktur hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="821e6-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="821e6-114">Wenn Sie beispielsweise `If` auf `If...Then...Else` eine Konstruktion klicken, werden `Else`alle `End If` Instanzen von `If`, `Then`, `ElseIf`, und in der Konstruktion hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="821e6-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="821e6-115">Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu wechseln, drücken Sie STRG+UMSCHALT+DOWN ARROW oder STRG+UMSCHALT+UP ARROW.</span><span class="sxs-lookup"><span data-stu-id="821e6-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="821e6-116">Verschachteln verschiedener Arten von Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="821e6-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="821e6-117">Sie können eine Art von Steuerelementstruktur innerhalb einer anderen Art verschachteln.</span><span class="sxs-lookup"><span data-stu-id="821e6-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="821e6-118">Im folgenden Beispiel `With` wird `For Each` ein Block `If` innerhalb einer `With` Schleife und verschachtelte Blöcke innerhalb des Blocks verwendet.</span><span class="sxs-lookup"><span data-stu-id="821e6-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="821e6-119">Überlappende Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="821e6-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="821e6-120">Sie können Steuerelementstrukturen nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="821e6-120">You cannot overlap control structures.</span></span> <span data-ttu-id="821e6-121">Dies bedeutet, dass jede verschachtelte Struktur vollständig in der nächsten innersten Struktur enthalten sein muss.</span><span class="sxs-lookup"><span data-stu-id="821e6-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="821e6-122">Die folgende Anordnung ist z. `For` B. ungültig, `With` da die Schleife beendet wird, bevor der innere Block beendet wird.</span><span class="sxs-lookup"><span data-stu-id="821e6-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![Diagramm, das ein Beispiel für ungültige Verschachtelung zeigt.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 <span data-ttu-id="821e6-124">Der Visual Basic-Compiler erkennt solche überlappenden Steuerungsstrukturen und signalisiert einen Kompilierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="821e6-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="821e6-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="821e6-125">See also</span></span>

- [<span data-ttu-id="821e6-126">Kontrollfluss</span><span class="sxs-lookup"><span data-stu-id="821e6-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="821e6-127">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="821e6-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="821e6-128">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="821e6-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="821e6-129">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="821e6-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
