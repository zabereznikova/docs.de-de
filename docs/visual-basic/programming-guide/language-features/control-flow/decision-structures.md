---
title: Decision-Strukturen (Visual Basic) | Microsoft-Dokumentation
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
- statements [Visual Basic], control flow
- If statement, decision structures
- If statement, If...Then...Else
- control flow, decision structures
- decision structures
- conditional statements, decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
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
ms.openlocfilehash: dcbfb4bc3318d5f79870d04e606fab8bfa2dafb9
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="c47d0-102">Entscheidungsstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c47d0-102">Decision Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="c47d0-103">können Sie testbedingungen und andere Vorgänge abhängig von den Ergebnissen dieses Tests ausführen.</span><span class="sxs-lookup"><span data-stu-id="c47d0-103"> lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="c47d0-104">Sie können testen, für eine Bedingung zu true oder false für verschiedene Werte für einen Ausdruck oder für verschiedene Ausnahmen generiert, wenn Sie eine Reihe von Anweisungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="c47d0-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="c47d0-105">Die folgende Abbildung zeigt eine Entscheidungsstruktur, die testet eine Bedingung erfüllt sein und verschiedene Aktionen abhängig davon, ob er true oder false.</span><span class="sxs-lookup"><span data-stu-id="c47d0-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 <span data-ttu-id="c47d0-106">![Flussdiagramm einer If... Dann... Else-Konstruktion](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span><span class="sxs-lookup"><span data-stu-id="c47d0-106">![Flow chart of an If...Then...Else construction](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span></span>  
<span data-ttu-id="c47d0-107">Unterschiedliche Aktionen auszuführen, wenn eine Bedingung True ist, und wenn sie falsch ist.</span><span class="sxs-lookup"><span data-stu-id="c47d0-107">Taking different actions when a condition is true and when it is false</span></span>  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="c47d0-108">If... Dann... Else-Konstruktion</span><span class="sxs-lookup"><span data-stu-id="c47d0-108">If...Then...Else Construction</span></span>  
 <span data-ttu-id="c47d0-109">`If...Then...Else`Konstruktionen können Sie für mindestens eine Bedingung zu testen, und führen Sie eine oder mehrere Anweisungen jede Bedingung.</span><span class="sxs-lookup"><span data-stu-id="c47d0-109">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="c47d0-110">Sie können testbedingungen und Aktionen auf folgende Weise:</span><span class="sxs-lookup"><span data-stu-id="c47d0-110">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="c47d0-111">Führen Sie eine oder mehrere Anweisungen, wenn eine Bedingung`True`</span><span class="sxs-lookup"><span data-stu-id="c47d0-111">Run one or more statements if a condition is `True`</span></span>  
  
-   <span data-ttu-id="c47d0-112">Führen Sie eine oder mehrere Anweisungen, wenn eine Bedingung`False`</span><span class="sxs-lookup"><span data-stu-id="c47d0-112">Run one or more statements if a condition is `False`</span></span>  
  
-   <span data-ttu-id="c47d0-113">Führen Sie einige Anweisungen, wenn eine Bedingung `True` und anderen ist dies`False`</span><span class="sxs-lookup"><span data-stu-id="c47d0-113">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
-   <span data-ttu-id="c47d0-114">Testen einer zusätzlichen Bedingung, wenn eine zuvor angegebene Bedingung ist`False`</span><span class="sxs-lookup"><span data-stu-id="c47d0-114">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="c47d0-115">Die Kontrollstruktur, die all diese Maßnahmen ermöglicht, wird die [Wenn... Dann... Else-Anweisung](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c47d0-115">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="c47d0-116">Sie können eine einzeiligen Version verwenden, haben nur einen Test und eine Anweisung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c47d0-116">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="c47d0-117">Wenn Sie einen komplexen Satz aus Bedingung und Aktion haben, können Sie die Version für mehrere Zeilen.</span><span class="sxs-lookup"><span data-stu-id="c47d0-117">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="c47d0-118">Wählen Sie... Case-Konstruktion</span><span class="sxs-lookup"><span data-stu-id="c47d0-118">Select...Case Construction</span></span>  
 <span data-ttu-id="c47d0-119">Die `Select...Case` Konstruktion können Sie Auswerten eines Ausdrucks einmal, und führen Sie verschiedene Gruppen von Anweisungen basierend auf verschiedenen möglichen Werte.</span><span class="sxs-lookup"><span data-stu-id="c47d0-119">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="c47d0-120">Weitere Informationen finden Sie unter [wählen... Case-Anweisung](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c47d0-120">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="c47d0-121">Versuchen Sie es... Catch... Finally-Konstruktion</span><span class="sxs-lookup"><span data-stu-id="c47d0-121">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="c47d0-122">`Try...Catch...Finally`Konstruktionen können Sie eine Gruppe von Anweisungen in einer Umgebung ausführen, die Kontrolle behält, wenn eine Anweisung eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="c47d0-122">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="c47d0-123">Sie können verschiedene Aktionen für verschiedene Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="c47d0-123">You can take different actions for different exceptions.</span></span> <span data-ttu-id="c47d0-124">Optional können Sie angeben, einen Codeblock, der ausgeführt wird, bevor Sie verlassen, dass die gesamte `Try...Catch...Finally` Konstruktion, unabhängig davon, was auftritt.</span><span class="sxs-lookup"><span data-stu-id="c47d0-124">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="c47d0-125">Weitere Informationen finden Sie unter [versuchen... Catch... Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c47d0-125">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c47d0-126">Für viele Steuerungsstrukturen werden beim Klicken auf ein Schlüsselwort alle Schlüsselwörter in der Struktur hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="c47d0-126">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="c47d0-127">Z. B. beim Klicken auf `If` in einer `If...Then...Else` Konstruktion, alle Instanzen von `If`, `Then`, `ElseIf`, `Else`, und `End If` bei der Erstellung werden hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="c47d0-127">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="c47d0-128">Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu wechseln, drücken Sie STRG + UMSCHALT + nach-unten oder STRG + UMSCHALT + nach-oben-Taste.</span><span class="sxs-lookup"><span data-stu-id="c47d0-128">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c47d0-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c47d0-129">See Also</span></span>  
 <span data-ttu-id="c47d0-130">[Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="c47d0-130">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="c47d0-131"> [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="c47d0-131"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="c47d0-132"> [Weitere Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="c47d0-132"> [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span></span>  
<span data-ttu-id="c47d0-133"> [Geschachtelte Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="c47d0-133"> [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span></span>  
<span data-ttu-id="c47d0-134"> [If-Operator](../../../../visual-basic/language-reference/operators/if-operator.md)</span><span class="sxs-lookup"><span data-stu-id="c47d0-134"> [If Operator](../../../../visual-basic/language-reference/operators/if-operator.md)</span></span>
