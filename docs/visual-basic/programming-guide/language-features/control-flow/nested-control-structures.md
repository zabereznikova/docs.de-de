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
ms.openlocfilehash: f559bf603605873f1b9155e9a96cb367e5420343
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941685"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="6a49d-102">Geschachtelte Steuerungsstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a49d-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="6a49d-103">Sie können Steuerungs Anweisungen in andere Steuerungs Anweisungen einfügen, z. b `If...Then...Else` . einen- `For...Next` Block in einer-Schleife.</span><span class="sxs-lookup"><span data-stu-id="6a49d-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="6a49d-104">Eine in einer anderen Steuerelement Anweisung positionierte Steuerelement Anweisungwird als geschachtelt bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6a49d-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="6a49d-105">Schachtelungs Ebenen</span><span class="sxs-lookup"><span data-stu-id="6a49d-105">Nesting Levels</span></span>  
 <span data-ttu-id="6a49d-106">Steuerungsstrukturen in Visual Basic können beliebig viele Ebenen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6a49d-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="6a49d-107">Es ist üblich, dass Sie die lesbaren Strukturen besser lesbar machen, indem Sie den Text der einzelnen einrücken.</span><span class="sxs-lookup"><span data-stu-id="6a49d-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="6a49d-108">Der integrierte Entwicklungsumgebung (IDE)-Editor führt dies automatisch aus.</span><span class="sxs-lookup"><span data-stu-id="6a49d-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="6a49d-109">Im folgenden Beispiel fügt die Prozedur `sumRows` die positiven Elemente der einzelnen Zeilen der Matrix hinzu.</span><span class="sxs-lookup"><span data-stu-id="6a49d-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="6a49d-110">Im vorherigen `Next` Beispiel schließt die erste Anweisung die innere `For` Schleife, und die letzte `Next` Anweisung schließt die äußere `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="6a49d-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="6a49d-111">Entsprechend werden die `End If` Anweisungen in `If` den-Anweisungen automatisch auf die nächste vorherige `If` -Anweisung angewendet.</span><span class="sxs-lookup"><span data-stu-id="6a49d-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="6a49d-112">Nested `Do` Loops funktionieren in ähnlicher Weise, wobei die innerste `Loop` -Anweisung mit der innersten `Do` -Anweisung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="6a49d-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a49d-113">Wenn Sie für viele Steuerungsstrukturen auf ein Schlüsselwort klicken, werden alle Schlüsselwörter in der Struktur hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="6a49d-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="6a49d-114">Wenn Sie beispielsweise auf eine `If` `If...Then...Else` Konstruktion klicken, werden `ElseIf`alle Instanzen von `If`, `Then`,, `Else`und `End If` in der Konstruktion hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="6a49d-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="6a49d-115">Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu wechseln, drücken Sie STRG + UMSCHALT + nach-unten oder STRG + UMSCHALT + nach-oben-Taste.</span><span class="sxs-lookup"><span data-stu-id="6a49d-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="6a49d-116">Schachteln verschiedener Arten von Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="6a49d-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="6a49d-117">Sie können eine Art von Steuerelement Struktur in einer anderen Art Schachteln.</span><span class="sxs-lookup"><span data-stu-id="6a49d-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="6a49d-118">Im folgenden Beispiel wird ein `With` -Block innerhalb `For Each` einer-Schleife und `If` geschachtelte `With` Blöcke innerhalb des-Blocks verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a49d-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="6a49d-119">Überlappende Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="6a49d-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="6a49d-120">Sie können die Steuerelement Strukturen nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="6a49d-120">You cannot overlap control structures.</span></span> <span data-ttu-id="6a49d-121">Dies bedeutet, dass jede geschachtelte Struktur vollständig in der nächsten innersten Struktur enthalten sein muss.</span><span class="sxs-lookup"><span data-stu-id="6a49d-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="6a49d-122">Beispielsweise ist die folgende Anordnung ungültig, da die `For` -Schleife beendet wird, `With` bevor der innere-Block beendet wird.</span><span class="sxs-lookup"><span data-stu-id="6a49d-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![Das Diagramm zeigt ein Beispiel für eine ungültige Schachtelung.](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 <span data-ttu-id="6a49d-124">Der Visual Basic-Compiler erkennt solche überlappenden Steuerungsstrukturen und signalisiert einen Kompilierzeitfehler.</span><span class="sxs-lookup"><span data-stu-id="6a49d-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a49d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a49d-125">See also</span></span>

- [<span data-ttu-id="6a49d-126">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="6a49d-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="6a49d-127">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="6a49d-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="6a49d-128">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="6a49d-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="6a49d-129">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="6a49d-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
