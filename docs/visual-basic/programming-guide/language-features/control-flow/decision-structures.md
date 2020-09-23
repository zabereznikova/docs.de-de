---
title: Entscheidungsstrukturen
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: 79c4949cd4d5b07d1b1d666b21467bf8db41ab3d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095615"
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="73006-102">Entscheidungsstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73006-102">Decision Structures (Visual Basic)</span></span>

<span data-ttu-id="73006-103">Mit Visual Basic können Sie Bedingungen testen und abhängig von den Ergebnissen dieses Tests verschiedene Vorgänge durchführen.</span><span class="sxs-lookup"><span data-stu-id="73006-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="73006-104">Sie können prüfen, dass eine Bedingung true oder false ist, für verschiedene Werte eines Ausdrucks oder für verschiedene Ausnahmen, die beim Ausführen einer Reihe von Anweisungen generiert werden.</span><span class="sxs-lookup"><span data-stu-id="73006-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="73006-105">In der folgenden Abbildung wird eine Entscheidungsstruktur dargestellt, die überprüft, ob eine Bedingung wahr ist, und abhängig davon, ob Sie true oder false ist, verschiedene Aktionen unternimmt.</span><span class="sxs-lookup"><span data-stu-id="73006-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 ![Ein Flussdiagramm einer if... Dann... Else-Konstruktion.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="73006-107">Wenn... Dann... Else-Konstruktion</span><span class="sxs-lookup"><span data-stu-id="73006-107">If...Then...Else Construction</span></span>  

 <span data-ttu-id="73006-108">`If...Then...Else` mit-Konstruktionen können Sie eine oder mehrere Bedingungen testen und abhängig von den einzelnen Bedingungen eine oder mehrere-Anweisungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="73006-108">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="73006-109">Es gibt folgende Möglichkeiten, um Bedingungen zu testen und Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="73006-109">You can test conditions and take actions in the following ways:</span></span>  
  
- <span data-ttu-id="73006-110">Führen Sie eine oder mehrere Anweisungen aus, wenn eine Bedingung ist. `True`</span><span class="sxs-lookup"><span data-stu-id="73006-110">Run one or more statements if a condition is `True`</span></span>  
  
- <span data-ttu-id="73006-111">Führen Sie eine oder mehrere Anweisungen aus, wenn eine Bedingung ist. `False`</span><span class="sxs-lookup"><span data-stu-id="73006-111">Run one or more statements if a condition is `False`</span></span>  
  
- <span data-ttu-id="73006-112">Führen Sie einige Anweisungen aus, wenn eine Bedingung ist, `True` und andere, wenn Sie `False`</span><span class="sxs-lookup"><span data-stu-id="73006-112">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
- <span data-ttu-id="73006-113">Testen einer zusätzlichen Bedingung, wenn eine vorherige Bedingung ist `False`</span><span class="sxs-lookup"><span data-stu-id="73006-113">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="73006-114">Die Steuerelement Struktur, die alle diese Möglichkeiten bietet, ist der [If... Dann... Else-Anweisung](../../../language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="73006-114">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="73006-115">Sie können eine einzeilige Version verwenden, wenn Sie nur einen Test und eine Anweisung ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="73006-115">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="73006-116">Wenn Sie einen komplexeren Satz von Bedingungen und Aktionen haben, können Sie die mehrzeilige Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="73006-116">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="73006-117">Wählen Sie... Fall Konstruktion</span><span class="sxs-lookup"><span data-stu-id="73006-117">Select...Case Construction</span></span>  

 <span data-ttu-id="73006-118">Die `Select...Case` Konstruktion ermöglicht Ihnen das einmalige Auswerten eines Ausdrucks und das Ausführen verschiedener Sätze von Anweisungen basierend auf anderen möglichen Werten.</span><span class="sxs-lookup"><span data-stu-id="73006-118">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="73006-119">Weitere Informationen finden Sie unter [SELECT... Case-Anweisung](../../../language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="73006-119">For more information, see [Select...Case Statement](../../../language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="73006-120">Try... Catch... Schließlich erstellen</span><span class="sxs-lookup"><span data-stu-id="73006-120">Try...Catch...Finally Construction</span></span>  

 <span data-ttu-id="73006-121">`Try...Catch...Finally` mit-Konstruktionen können Sie eine Reihe von-Anweisungen in einer Umgebung ausführen, die die Steuerung beibehält, wenn eine der Anweisungen eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="73006-121">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="73006-122">Sie können verschiedene Aktionen für verschiedene Ausnahmen durchführen.</span><span class="sxs-lookup"><span data-stu-id="73006-122">You can take different actions for different exceptions.</span></span> <span data-ttu-id="73006-123">Sie können optional einen Codeblock angeben, der ausgeführt wird, bevor Sie die gesamte `Try...Catch...Finally` Konstruktion beenden, unabhängig davon, was passiert.</span><span class="sxs-lookup"><span data-stu-id="73006-123">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="73006-124">Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="73006-124">For more information, see [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73006-125">Wenn Sie für viele Steuerungsstrukturen auf ein Schlüsselwort klicken, werden alle Schlüsselwörter in der Struktur hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="73006-125">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="73006-126">Wenn Sie beispielsweise auf `If` eine Konstruktion klicken `If...Then...Else` , werden alle Instanzen von `If` , `Then` , `ElseIf` , `Else` und `End If` in der Konstruktion hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="73006-126">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="73006-127">Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu wechseln, drücken Sie STRG + UMSCHALT + nach-unten oder STRG + UMSCHALT + nach-oben-Taste.</span><span class="sxs-lookup"><span data-stu-id="73006-127">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73006-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73006-128">See also</span></span>

- [<span data-ttu-id="73006-129">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="73006-129">Control Flow</span></span>](index.md)
- [<span data-ttu-id="73006-130">Schleifenstrukturen</span><span class="sxs-lookup"><span data-stu-id="73006-130">Loop Structures</span></span>](loop-structures.md)
- [<span data-ttu-id="73006-131">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="73006-131">Other Control Structures</span></span>](other-control-structures.md)
- [<span data-ttu-id="73006-132">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="73006-132">Nested Control Structures</span></span>](nested-control-structures.md)
- [<span data-ttu-id="73006-133">If-Operator</span><span class="sxs-lookup"><span data-stu-id="73006-133">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
