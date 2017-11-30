---
title: Geschachtelte Steuerungsstrukturen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22adf4086cd494202a540b2ec16310072329b6ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="09898-102">Geschachtelte Steuerungsstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09898-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="09898-103">Sie fügen die Steueranweisungen in andere Steueranweisungen, z. B. ein `If...Then...Else` -Block in einem `For...Next` Schleife.</span><span class="sxs-lookup"><span data-stu-id="09898-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="09898-104">Eine steuerungsanweisung, die innerhalb einer anderen Steueranweisung platziert gilt als *geschachtelte*.</span><span class="sxs-lookup"><span data-stu-id="09898-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="09898-105">Schachteln von Ebenen</span><span class="sxs-lookup"><span data-stu-id="09898-105">Nesting Levels</span></span>  
 <span data-ttu-id="09898-106">Steuerungsstrukturen in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] können geschachtelt sein, um wie viele Ebenen wie gewünscht.</span><span class="sxs-lookup"><span data-stu-id="09898-106">Control structures in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] can be nested to as many levels as you want.</span></span> <span data-ttu-id="09898-107">Es ist üblich, geschachtelte Strukturen durch Festlegen von Einzügen für den Text jeder einzelnen besser lesbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="09898-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="09898-108">Die integrierte Entwicklungsumgebung (IDE)-Umgebung-Editor geschieht automatisch.</span><span class="sxs-lookup"><span data-stu-id="09898-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="09898-109">Im folgenden Beispiel wird die Prozedur `sumRows` addiert die positiven Elemente der einzelnen Zeilen der Matrix.</span><span class="sxs-lookup"><span data-stu-id="09898-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="09898-110">Im vorherigen Beispiel das erste `Next` Anweisung schließt die innere `For` Schleife und der letzte `Next` Anweisung schließt die äußere `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="09898-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="09898-111">Ebenso in geschachtelten `If` -Anweisungen, die `End If` Anweisungen gelten automatisch auf die nächste vor `If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="09898-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="09898-112">Geschachtelte `Do` -Schleifen funktionieren ähnlich, mit der innersten `Loop` Anweisung entsprechen die innerste `Do` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="09898-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09898-113">Für viele Steuerungsstrukturen werden, wenn Sie ein Schlüsselwort, klicken Sie auf alle Schlüsselwörter in der Struktur hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="09898-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="09898-114">Z. B. beim Klicken auf `If` in einer `If...Then...Else` Konstruktion, die alle Instanzen von `If`, `Then`, `ElseIf`, `Else`, und `End If` bei der Erstellung werden hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="09898-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="09898-115">Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu verschieben, drücken Sie STRG + UMSCHALT + nach-oben-Taste oder STRG + UMSCHALT + nach-oben-Taste.</span><span class="sxs-lookup"><span data-stu-id="09898-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="09898-116">Verschiedene Arten von Steuerungsstrukturen schachteln</span><span class="sxs-lookup"><span data-stu-id="09898-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="09898-117">Sie können eine Art von Steuerelement-Struktur in eine andere Art schachteln.</span><span class="sxs-lookup"><span data-stu-id="09898-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="09898-118">Im folgenden Beispiel wird eine `With` -Block ein `For Each` -Schleife und geschachtelte `If` blockiert innerhalb der `With` Block.</span><span class="sxs-lookup"><span data-stu-id="09898-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="09898-119">Überlappende Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="09898-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="09898-120">Steuerungsstrukturen sich nicht überschneiden.</span><span class="sxs-lookup"><span data-stu-id="09898-120">You cannot overlap control structures.</span></span> <span data-ttu-id="09898-121">Dies bedeutet, dass alle geschachtelten Strukturen vollständig innerhalb der nächsten innersten Struktur enthalten sein muss.</span><span class="sxs-lookup"><span data-stu-id="09898-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="09898-122">Die folgende Anordnung ist beispielsweise ungültig da die `For` -Schleife wird beendet, bevor Sie die innere `With` Block beendet wird.</span><span class="sxs-lookup"><span data-stu-id="09898-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 <span data-ttu-id="09898-123">![Grafisches Diagramm einer ungültigen Schachtelung](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span><span class="sxs-lookup"><span data-stu-id="09898-123">![Graphic diagram of invalid nesting](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span></span>  
<span data-ttu-id="09898-124">Ungültige Schachtelung von für und mit Strukturen</span><span class="sxs-lookup"><span data-stu-id="09898-124">Invalid nesting of For and With structures</span></span>  
  
 <span data-ttu-id="09898-125">Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Compiler erkennt solche überlappenden Steuerungsstrukturen und signalisiert einen Fehler während der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="09898-125">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09898-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09898-126">See Also</span></span>  
 [<span data-ttu-id="09898-127">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="09898-127">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="09898-128">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="09898-128">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="09898-129">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="09898-129">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="09898-130">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="09898-130">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
