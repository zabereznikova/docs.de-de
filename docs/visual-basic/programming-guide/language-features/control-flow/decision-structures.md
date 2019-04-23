---
title: Entscheidungsstrukturen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: 4a76b2565c343e69ac3c11441035a7682a8f08ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318935"
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="f556a-102">Entscheidungsstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f556a-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="f556a-103">Visual Basic können Sie die Bedingungen zu testen, und führen Sie verschiedene Vorgänge abhängig von den Ergebnissen dieses Tests.</span><span class="sxs-lookup"><span data-stu-id="f556a-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="f556a-104">Sie können testen, auf eine Bedingung wird "true" oder "false" für verschiedene Werte für einen Ausdruck oder für verschiedene Ausnahmen generiert, wenn Sie eine Reihe von Anweisungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="f556a-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="f556a-105">Die folgende Abbildung zeigt eine Entscheidungsstruktur, die eine Bedingung "true" wird überprüft, und verschiedene Aktionen abhängig davon, ob es "true" oder "false".</span><span class="sxs-lookup"><span data-stu-id="f556a-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 ![Ein Flussdiagramm einer If... Klicken Sie dann... Else-Konstruktion.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="f556a-107">If... Klicken Sie dann... Else-Konstruktion</span><span class="sxs-lookup"><span data-stu-id="f556a-107">If...Then...Else Construction</span></span>  
 <span data-ttu-id="f556a-108">`If...Then...Else` Konstruktionen können Sie für eine oder mehrere Bedingungen zu testen, und führen Sie eine oder mehrere Anweisungen je nach jede Bedingung.</span><span class="sxs-lookup"><span data-stu-id="f556a-108">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="f556a-109">Sie können testen Bedingungen und Aktionen auf folgende Weise:</span><span class="sxs-lookup"><span data-stu-id="f556a-109">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="f556a-110">Führen Sie eine oder mehrere Anweisungen aus, wenn eine Bedingung `True`</span><span class="sxs-lookup"><span data-stu-id="f556a-110">Run one or more statements if a condition is `True`</span></span>  
  
-   <span data-ttu-id="f556a-111">Führen Sie eine oder mehrere Anweisungen aus, wenn eine Bedingung `False`</span><span class="sxs-lookup"><span data-stu-id="f556a-111">Run one or more statements if a condition is `False`</span></span>  
  
-   <span data-ttu-id="f556a-112">Führen Sie einige Anweisungen, wenn eine Bedingung `True` und anderen ist dies `False`</span><span class="sxs-lookup"><span data-stu-id="f556a-112">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
-   <span data-ttu-id="f556a-113">Eine weitere Bedingung zu testen, wenn eine vorherige Bedingung `False`</span><span class="sxs-lookup"><span data-stu-id="f556a-113">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="f556a-114">Die Steuerelement-Struktur, die alle diese Möglichkeiten bietet, ist die [Wenn... Klicken Sie dann... Else-Anweisung](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f556a-114">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="f556a-115">Sie können eine einzeilige-Version verwenden, wenn Sie nur einen Test und eine Anweisung ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="f556a-115">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="f556a-116">Wenn Sie einen komplexen Satz von Bedingungen und Aktionen verfügen, können Sie die Version der Zeile.</span><span class="sxs-lookup"><span data-stu-id="f556a-116">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="f556a-117">Auswählen... Case-Konstruktion</span><span class="sxs-lookup"><span data-stu-id="f556a-117">Select...Case Construction</span></span>  
 <span data-ttu-id="f556a-118">Die `Select...Case` Konstruktion können Sie einen Ausdruck ein Mal ausgewertet, und führen Sie verschiedene Gruppen von Anweisungen basierend auf verschiedenen möglichen Werte.</span><span class="sxs-lookup"><span data-stu-id="f556a-118">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="f556a-119">Weitere Informationen finden Sie unter [auswählen... Case-Anweisung](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f556a-119">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="f556a-120">Versuchen Sie es... Catch... Finally-Konstruktion</span><span class="sxs-lookup"><span data-stu-id="f556a-120">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="f556a-121">`Try...Catch...Finally` Konstruktionen können Sie eine Reihe von Anweisungen in einer Umgebung ausführen, die die Kontrolle behält, wenn eine der Anweisungen eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="f556a-121">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="f556a-122">Sie können verschiedene Aktionen für unterschiedliche Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="f556a-122">You can take different actions for different exceptions.</span></span> <span data-ttu-id="f556a-123">Optional können Sie angeben, einen Codeblock, der ausgeführt wird, bevor Sie verlassen, dass die gesamte `Try...Catch...Finally` erstellt, unabhängig davon, was geschieht.</span><span class="sxs-lookup"><span data-stu-id="f556a-123">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="f556a-124">Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f556a-124">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f556a-125">Für viele Steuerungsstrukturen Wenn Sie ein Schlüsselwort, klicken Sie auf werden alle Schlüsselwörter in der Struktur hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="f556a-125">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="f556a-126">Z. B. beim Klicken auf `If` in einer `If...Then...Else` Konstruktion, die alle Instanzen von `If`, `Then`, `ElseIf`, `Else`, und `End If` bei der Erstellung werden hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="f556a-126">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="f556a-127">Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu verschieben, drücken Sie STRG + UMSCHALT + nach-unten oder STRG + UMSCHALT + nach-oben-Taste.</span><span class="sxs-lookup"><span data-stu-id="f556a-127">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f556a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f556a-128">See also</span></span>

- [<span data-ttu-id="f556a-129">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="f556a-129">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="f556a-130">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="f556a-130">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="f556a-131">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="f556a-131">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="f556a-132">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="f556a-132">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="f556a-133">If-Operator</span><span class="sxs-lookup"><span data-stu-id="f556a-133">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
