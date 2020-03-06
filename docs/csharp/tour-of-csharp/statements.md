---
title: C#-Anweisungen – Überblick über C#
description: Sie erstellen die Aktionen eines C#-Programms mit Anweisungen.
ms.date: 02/27/2020
ms.assetid: 5409c379-5622-4fae-88b5-1654276ea8d4
ms.openlocfilehash: ced13b1bfd17977acb98bf33c0a477161cf08a93
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159103"
---
# <a name="statements"></a><span data-ttu-id="89862-103">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="89862-103">Statements</span></span>

<span data-ttu-id="89862-104">Die Aktionen eines Programms werden mit *Anweisungen* ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="89862-104">The actions of a program are expressed using *statements*.</span></span> <span data-ttu-id="89862-105">C# unterstützt verschiedene Arten von Anweisungen, von denen ein Teil als eingebettete Anweisungen definiert ist.</span><span class="sxs-lookup"><span data-stu-id="89862-105">C# supports several different kinds of statements, a number of which are defined in terms of embedded statements.</span></span>

<span data-ttu-id="89862-106">Ein *Block* ermöglicht, mehrere Anweisungen in Kontexten zu schreiben, in denen eine einzelne Anweisung zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="89862-106">A *block* permits multiple statements to be written in contexts where a single statement is allowed.</span></span> <span data-ttu-id="89862-107">Ein Block besteht aus einer Liste von Anweisungen, die zwischen den Trennzeichen `{` und `}` geschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="89862-107">A block consists of a list of statements written between the delimiters `{` and `}`.</span></span>

<span data-ttu-id="89862-108">*Deklarationsanweisungen* werden verwendet, um lokale Variablen und Konstanten deklarieren.</span><span class="sxs-lookup"><span data-stu-id="89862-108">*Declaration statements* are used to declare local variables and constants.</span></span>

<span data-ttu-id="89862-109">*Ausdrucksanweisungen* werden zum Auswerten von Ausdrücken verwendet.</span><span class="sxs-lookup"><span data-stu-id="89862-109">*Expression statements* are used to evaluate expressions.</span></span> <span data-ttu-id="89862-110">Ausdrücke, die als Anweisungen verwendet werden können, enthalten Methodenaufrufe, Objektzuordnungen mit dem `new`-Operator, Zuweisungen mit `=` und den Verbundzuweisungsoperatoren, Inkrementier- und Dekrementiervorgänge unter Verwendung des `++`- und `--`-Operators und `await`-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="89862-110">Expressions that can be used as statements include method invocations, object allocations using the `new` operator, assignments using `=` and the compound assignment operators, increment and decrement operations using the `++` and `--` operators and `await` expressions.</span></span>

<span data-ttu-id="89862-111">*Auswahlanweisungen* werden verwendet, um eine Anzahl von möglichen Anweisungen für die Ausführung anhand des Werts eines Ausdrucks auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="89862-111">*Selection statements* are used to select one of a number of possible statements for execution based on the value of some expression.</span></span> <span data-ttu-id="89862-112">Diese Gruppe enthält die Anweisungen `if` und `switch`.</span><span class="sxs-lookup"><span data-stu-id="89862-112">This group contains the `if` and `switch` statements.</span></span>

<span data-ttu-id="89862-113">*Iterationsanweisungen* werden verwendet, um eine eingebettete Anweisung wiederholt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="89862-113">*Iteration statements* are used to execute repeatedly an embedded statement.</span></span> <span data-ttu-id="89862-114">Diese Gruppe enthält die Anweisungen `while`, `do`, `for` und `foreach`.</span><span class="sxs-lookup"><span data-stu-id="89862-114">This group contains the `while`, `do`, `for`, and `foreach` statements.</span></span>

<span data-ttu-id="89862-115">*Sprunganweisungen* werden verwendet, um die Steuerung zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="89862-115">*Jump statements* are used to transfer control.</span></span> <span data-ttu-id="89862-116">Diese Gruppe enthält die Anweisungen `break`, `continue`, `goto`, `throw`, `return` und `yield`.</span><span class="sxs-lookup"><span data-stu-id="89862-116">This group contains the `break`, `continue`, `goto`, `throw`, `return`, and `yield` statements.</span></span>

<span data-ttu-id="89862-117">Mit der `try`... `catch`-Anweisung werden Ausnahmen abgefangen, die während der Ausführung eines Blocks auftreten, und mit der `try`... `finally`-Anweisung wird Finalisierungscode angegeben, der immer ausgeführt wird, unabhängig davon, ob eine Ausnahme aufgetreten ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="89862-117">The `try`...`catch` statement is used to catch exceptions that occur during execution of a block, and the `try`...`finally` statement is used to specify finalization code that is always executed, whether an exception occurred or not.</span></span>

<span data-ttu-id="89862-118">Mit den Anweisungen `checked` und `unchecked` wird der Überlaufüberprüfungs-Kontext für arithmetische Operationen für Ganzzahltypen und Konvertierungen gesteuert.</span><span class="sxs-lookup"><span data-stu-id="89862-118">The `checked` and `unchecked` statements are used to control the overflow-checking context for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="89862-119">Die `lock`-Anweisung wird verwendet, um die Sperre für gegenseitigen Ausschluss für ein bestimmtes Objekt abzurufen, eine Anweisung auszuführen und die Sperre aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="89862-119">The `lock` statement is used to obtain the mutual-exclusion lock for a given object, execute a statement, and then release the lock.</span></span>

<span data-ttu-id="89862-120">Die `using`-Anweisung wird verwendet, um eine Ressource abzurufen, eine Anweisung auszuführen und dann diese Ressource zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="89862-120">The `using` statement is used to obtain a resource, execute a statement, and then dispose of that resource.</span></span>

<span data-ttu-id="89862-121">Im Folgenden werden die Arten von Anweisungen aufgelistet, die verwendet werden können, und für jede ein Beispiel aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="89862-121">The following lists the kinds of statements that can be used, and provides an example for each.</span></span>

* <span data-ttu-id="89862-122">Deklaration lokaler Variablen:</span><span class="sxs-lookup"><span data-stu-id="89862-122">Local variable declaration:</span></span>

 [!code-csharp[Declarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L9-L15)]

* <span data-ttu-id="89862-123">Deklaration lokaler Konstanten:</span><span class="sxs-lookup"><span data-stu-id="89862-123">Local constant declaration:</span></span>

 [!code-csharp[ConstantDeclarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L17-L22)]

* <span data-ttu-id="89862-124">Ausdrucksanweisung:</span><span class="sxs-lookup"><span data-stu-id="89862-124">Expression statement:</span></span>

 [!code-csharp[Expressions](../../../samples/snippets/csharp/tour/statements/Program.cs#L24-L31)]

* <span data-ttu-id="89862-125">`if`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="89862-125">`if` statement:</span></span>

 [!code-csharp[IfStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L33-L43)]

* <span data-ttu-id="89862-126">`switch`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="89862-126">`switch` statement:</span></span>

 [!code-csharp[SwitchStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L45-L60)]

* <span data-ttu-id="89862-127">`while`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="89862-127">`while` statement:</span></span>

 [!code-csharp[WhileStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L62-L70)]

* <span data-ttu-id="89862-128">`do`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="89862-128">`do` statement:</span></span>

 [!code-csharp[DoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L72-L81)]

* <span data-ttu-id="89862-129">`for`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="89862-129">`for` statement:</span></span>

 [!code-csharp[ForStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L83-L89)]

* <span data-ttu-id="89862-130">`foreach`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="89862-130">`foreach` statement:</span></span>

 [!code-csharp[ForEachStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L91-L97)]

* <span data-ttu-id="89862-131">`break`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="89862-131">`break` statement:</span></span>

 [!code-csharp[BreakStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L99-L108)]

* <span data-ttu-id="89862-132">`continue`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="89862-132">`continue` statement:</span></span>

 [!code-csharp[ContinueStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L110-L118)]

* <span data-ttu-id="89862-133">`goto`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="89862-133">`goto` statement:</span></span>

 [!code-csharp[GotoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L120-L129)]

* <span data-ttu-id="89862-134">`return`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="89862-134">`return` statement:</span></span>

 [!code-csharp[ReturnStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L131-L139)]

* <span data-ttu-id="89862-135">`yield`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="89862-135">`yield` statement:</span></span>

 [!code-csharp[YieldStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L141-L155)]

* <span data-ttu-id="89862-136">`throw`-Anweisungen und `try`-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="89862-136">`throw` statements and `try` statements:</span></span>

 [!code-csharp[TryThrow](../../../samples/snippets/csharp/tour/statements/Program.cs#L157-L183)]

* <span data-ttu-id="89862-137">`checked`- und `unchecked`-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="89862-137">`checked` and `unchecked` statements:</span></span>

 [!code-csharp[CheckedUncheckedStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L185-L196)]

* <span data-ttu-id="89862-138">`lock`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="89862-138">`lock` statement:</span></span>

 [!code-csharp[LockStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L257-L273)]

* <span data-ttu-id="89862-139">`using`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="89862-139">`using` statement:</span></span>

 [!code-csharp[UsingStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L198-L206)]

>[!div class="step-by-step"]
><span data-ttu-id="89862-140">[Zurück](expressions.md)
>[Weiter](classes-and-objects.md)</span><span class="sxs-lookup"><span data-stu-id="89862-140">[Previous](expressions.md)
[Next](classes-and-objects.md)</span></span>
