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
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8275a0628c8593d9e6c55ef27adcde2acec31547
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="a5e99-102">Geschachtelte Steuerungsstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5e99-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="a5e99-103">Sie fügen die Steueranweisungen in andere Steueranweisungen, z. B. ein `If...Then...Else` -Block in einer `For...Next` Schleife.</span><span class="sxs-lookup"><span data-stu-id="a5e99-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="a5e99-104">Eine Steuerelement-Anweisung innerhalb einer anderen Steueranweisung platziert gilt als *geschachtelten*.</span><span class="sxs-lookup"><span data-stu-id="a5e99-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="a5e99-105">Schachteln von Ebenen</span><span class="sxs-lookup"><span data-stu-id="a5e99-105">Nesting Levels</span></span>  
 <span data-ttu-id="a5e99-106">Steuerungsstrukturen in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] können geschachtelt werden, um so viele Ebenen wie gewünscht.</span><span class="sxs-lookup"><span data-stu-id="a5e99-106">Control structures in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can be nested to as many levels as you want.</span></span> <span data-ttu-id="a5e99-107">Es ist üblich, geschachtelte Strukturen durch den Text jeder einzelnen einrücken besser lesbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="a5e99-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="a5e99-108">Integrierte Entwicklung Umgebung (IDE) Editor wird automatisch.</span><span class="sxs-lookup"><span data-stu-id="a5e99-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="a5e99-109">Im folgenden Beispiel, das Verfahren `sumRows` addiert die positiven Elemente jeder Zeile der Matrix.</span><span class="sxs-lookup"><span data-stu-id="a5e99-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="a5e99-110">Im vorherigen Beispiel ist der erste `Next` Anweisung schließt die innere `For` -Schleife und die letzte `Next` Anweisung schließt die äußere `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="a5e99-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="a5e99-111">Ebenso in geschachtelten `If` -Anweisungen, die `End If` Aussagen gelten automatisch an den nächstgelegenen vorherigen `If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a5e99-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="a5e99-112">Geschachtelte `Do` -Schleifen funktionieren ähnlich, wobei die innerste `Loop` Anweisung entsprechen die innerste `Do` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a5e99-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5e99-113">Für viele Steuerungsstrukturen werden beim Klicken auf ein Schlüsselwort alle Schlüsselwörter in der Struktur hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="a5e99-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="a5e99-114">Z. B. beim Klicken auf `If` in einer `If...Then...Else` Konstruktion, alle Instanzen von `If`, `Then`, `ElseIf`, `Else`, und `End If` bei der Erstellung werden hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="a5e99-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="a5e99-115">Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu wechseln, drücken Sie STRG + UMSCHALT + nach-unten oder STRG + UMSCHALT + nach-oben-Taste.</span><span class="sxs-lookup"><span data-stu-id="a5e99-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="a5e99-116">Schachteln von verschiedenen Arten von Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="a5e99-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="a5e99-117">Sie können eine Art von Steuerungsstruktur innerhalb einer anderen Art schachteln.</span><span class="sxs-lookup"><span data-stu-id="a5e99-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="a5e99-118">Im folgenden Beispiel wird ein `With` -Block innerhalb einer `For Each` -Schleife und geschachtelte `If` blockiert innerhalb der `With` Block.</span><span class="sxs-lookup"><span data-stu-id="a5e99-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="a5e99-119">Überlappende Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="a5e99-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="a5e99-120">Steuerungsstrukturen sich nicht überschneiden.</span><span class="sxs-lookup"><span data-stu-id="a5e99-120">You cannot overlap control structures.</span></span> <span data-ttu-id="a5e99-121">Dies bedeutet, dass alle geschachtelten Strukturen vollständig innerhalb der nächsten inneren Struktur enthalten sein muss.</span><span class="sxs-lookup"><span data-stu-id="a5e99-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="a5e99-122">Die folgende Anordnung ist beispielsweise ungültig da die `For` -Schleife vor dem inneren `With` Block beendet wird.</span><span class="sxs-lookup"><span data-stu-id="a5e99-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 <span data-ttu-id="a5e99-123">![Grafisches Diagramm einer ungültigen Schachtelung](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span><span class="sxs-lookup"><span data-stu-id="a5e99-123">![Graphic diagram of invalid nesting](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span></span>  
<span data-ttu-id="a5e99-124">Ungültige Schachtelung von for- und Strukturen</span><span class="sxs-lookup"><span data-stu-id="a5e99-124">Invalid nesting of For and With structures</span></span>  
  
 <span data-ttu-id="a5e99-125">Die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler erkennt diese überlappenden Steuerungsstrukturen und signalisiert einen Fehler während der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="a5e99-125">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5e99-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5e99-126">See Also</span></span>  
 <span data-ttu-id="a5e99-127">[Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="a5e99-127">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="a5e99-128"> [Entscheidungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span><span class="sxs-lookup"><span data-stu-id="a5e99-128"> [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span></span>  
<span data-ttu-id="a5e99-129"> [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="a5e99-129"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="a5e99-130"> [Weitere Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)</span><span class="sxs-lookup"><span data-stu-id="a5e99-130"> [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)</span></span>
