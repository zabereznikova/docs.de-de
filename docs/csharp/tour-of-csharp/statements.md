---
title: "C#-Anweisungen – Überblick über C#"
description: Sie erstellen die Aktionen eines C#-Programms mit Anweisungen.
keywords: .NET, Csharp, Anweisungen, Syntax
author: BillWagner
ms.author: wiwagn
ms.date: 11/06/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 5409c379-5622-4fae-88b5-1654276ea8d4
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 99ec2489daf89926da9b8c4e148965412826a8a6
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="statements"></a><span data-ttu-id="63c5d-104">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="63c5d-104">Statements</span></span>

<span data-ttu-id="63c5d-105">Die Aktionen eines Programms werden mit *Anweisungen* ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="63c5d-105">The actions of a program are expressed using *statements*.</span></span> <span data-ttu-id="63c5d-106">C# unterstützt verschiedene Arten von Anweisungen, von denen ein Teil als eingebettete Anweisungen definiert ist.</span><span class="sxs-lookup"><span data-stu-id="63c5d-106">C# supports several different kinds of statements, a number of which are defined in terms of embedded statements.</span></span>

<span data-ttu-id="63c5d-107">Ein *Block* ermöglicht, mehrere Anweisungen in Kontexten zu schreiben, in denen eine einzelne Anweisung zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="63c5d-107">A *block* permits multiple statements to be written in contexts where a single statement is allowed.</span></span> <span data-ttu-id="63c5d-108">Ein Block besteht aus einer Liste von Anweisungen, die zwischen den Trennzeichen `{` und `}` geschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="63c5d-108">A block consists of a list of statements written between the delimiters `{` and `}`.</span></span>

<span data-ttu-id="63c5d-109">*Deklarationsanweisungen* werden verwendet, um lokale Variablen und Konstanten deklarieren.</span><span class="sxs-lookup"><span data-stu-id="63c5d-109">*Declaration statements* are used to declare local variables and constants.</span></span>

<span data-ttu-id="63c5d-110">*Ausdrucksanweisungen* werden zum Auswerten von Ausdrücken verwendet.</span><span class="sxs-lookup"><span data-stu-id="63c5d-110">*Expression statements* are used to evaluate expressions.</span></span> <span data-ttu-id="63c5d-111">Ausdrücke, die als Anweisungen verwendet werden können, enthalten Methodenaufrufe, Objektzuordnungen mit dem `new`-Operator, Zuweisungen mit `=` und den Verbundzuweisungsoperatoren, Inkrementier- und Dekrementiervorgänge unter Verwendung des `++`- und `--`-Operators und `await`-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="63c5d-111">Expressions that can be used as statements include method invocations, object allocations using the `new` operator, assignments using `=` and the compound assignment operators, increment and decrement operations using the `++` and `--` operators and `await` expressions.</span></span>

<span data-ttu-id="63c5d-112">*Auswahlanweisungen* werden verwendet, um eine Anzahl von möglichen Anweisungen für die Ausführung anhand des Werts eines Ausdrucks auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="63c5d-112">*Selection statements* are used to select one of a number of possible statements for execution based on the value of some expression.</span></span> <span data-ttu-id="63c5d-113">Zu dieser Gruppe gehören die `if`- und `switch`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="63c5d-113">In this group are the `if` and `switch` statements.</span></span>

<span data-ttu-id="63c5d-114">*Iterationsanweisungen* werden verwendet, um eine eingebettete Anweisung wiederholt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="63c5d-114">*Iteration statements* are used to execute repeatedly an embedded statement.</span></span> <span data-ttu-id="63c5d-115">Zu dieser Gruppe gehören die `while`-, `do`-, `for`- und `foreach`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="63c5d-115">In this group are the `while`, `do`, `for`, and `foreach` statements.</span></span>

<span data-ttu-id="63c5d-116">*Sprunganweisungen* werden verwendet, um die Steuerung zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="63c5d-116">*Jump statements* are used to transfer control.</span></span> <span data-ttu-id="63c5d-117">Zu dieser Gruppe gehören die `break`-, `continue`-, `goto`-, `throw`-, `return`- und `yield`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="63c5d-117">In this group are the `break`, `continue`, `goto`, `throw`, `return`, and `yield` statements.</span></span>

<span data-ttu-id="63c5d-118">Mit der `try`... `catch`-Anweisung werden Ausnahmen abgefangen, die während der Ausführung eines Blocks auftreten, und mit der `try`... `finally`-Anweisung wird Finalisierungscode angegeben, der immer ausgeführt wird, unabhängig davon, ob eine Ausnahme aufgetreten ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="63c5d-118">The `try`...`catch` statement is used to catch exceptions that occur during execution of a block, and the `try`...`finally` statement is used to specify finalization code that is always executed, whether an exception occurred or not.</span></span>

<span data-ttu-id="63c5d-119">Mit den Anweisungen `checked` und `unchecked` wird der Überlaufüberprüfungs-Kontext für arithmetische Operationen für Ganzzahltypen und Konvertierungen gesteuert.</span><span class="sxs-lookup"><span data-stu-id="63c5d-119">The `checked` and `unchecked` statements are used to control the overflow-checking context for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="63c5d-120">Die `lock`-Anweisung wird verwendet, um die Sperre für gegenseitigen Ausschluss für ein bestimmtes Objekt abzurufen, eine Anweisung auszuführen und die Sperre aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="63c5d-120">The `lock` statement is used to obtain the mutual-exclusion lock for a given object, execute a statement, and then release the lock.</span></span>

<span data-ttu-id="63c5d-121">Die `using`-Anweisung wird verwendet, um eine Ressource abzurufen, eine Anweisung auszuführen und dann diese Ressource zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="63c5d-121">The `using` statement is used to obtain a resource, execute a statement, and then dispose of that resource.</span></span>

<span data-ttu-id="63c5d-122">Im Folgenden werden die Arten von Anweisungen aufgelistet, die verwendet werden können, und für jede ein Beispiel aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="63c5d-122">The following lists the kinds of statements that can be used, and provides an example for each.</span></span>

* <span data-ttu-id="63c5d-123">Deklaration lokaler Variablen:</span><span class="sxs-lookup"><span data-stu-id="63c5d-123">Local variable declaration:</span></span>

 <span data-ttu-id="63c5d-124">[!code-csharp[Deklarationen](../../../samples/snippets/csharp/tour/statements/Program.cs#L9-L15)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-124">[!code-csharp[Declarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L9-L15)]</span></span>

* <span data-ttu-id="63c5d-125">Deklaration lokaler Konstanten:</span><span class="sxs-lookup"><span data-stu-id="63c5d-125">Local constant declaration:</span></span>

 <span data-ttu-id="63c5d-126">[!code-csharp[ConstantDeclarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L17-L22)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-126">[!code-csharp[ConstantDeclarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L17-L22)]</span></span>

* <span data-ttu-id="63c5d-127">Ausdrucksanweisung:</span><span class="sxs-lookup"><span data-stu-id="63c5d-127">Expression statement:</span></span>

 <span data-ttu-id="63c5d-128">[!code-csharp[Ausdrücke](../../../samples/snippets/csharp/tour/statements/Program.cs#L24-L31)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-128">[!code-csharp[Expressions](../../../samples/snippets/csharp/tour/statements/Program.cs#L24-L31)]</span></span>

* <span data-ttu-id="63c5d-129">`if`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="63c5d-129">`if` statement:</span></span>

 <span data-ttu-id="63c5d-130">[!code-csharp[IfStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L33-L43)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-130">[!code-csharp[IfStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L33-L43)]</span></span>

* <span data-ttu-id="63c5d-131">`switch`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="63c5d-131">`switch` statement:</span></span>

 <span data-ttu-id="63c5d-132">[!code-csharp[SwitchStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L45-L60)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-132">[!code-csharp[SwitchStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L45-L60)]</span></span>

* <span data-ttu-id="63c5d-133">`while`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="63c5d-133">`while` statement:</span></span>

 <span data-ttu-id="63c5d-134">[!code-csharp[WhileStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L62-L70)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-134">[!code-csharp[WhileStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L62-L70)]</span></span>

* <span data-ttu-id="63c5d-135">`do`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="63c5d-135">`do` statement:</span></span>

 <span data-ttu-id="63c5d-136">[!code-csharp[DoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L72-L81)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-136">[!code-csharp[DoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L72-L81)]</span></span>

* <span data-ttu-id="63c5d-137">`for`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="63c5d-137">`for` statement:</span></span>

 <span data-ttu-id="63c5d-138">[!code-csharp[ForStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L83-L89)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-138">[!code-csharp[ForStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L83-L89)]</span></span>

* <span data-ttu-id="63c5d-139">`foreach`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="63c5d-139">`foreach` statement:</span></span>

 <span data-ttu-id="63c5d-140">[!code-csharp[ForEachStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L91-L97)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-140">[!code-csharp[ForEachStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L91-L97)]</span></span>

* <span data-ttu-id="63c5d-141">`break`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="63c5d-141">`break` statement:</span></span>

 <span data-ttu-id="63c5d-142">[!code-csharp[BreakStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L99-L108)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-142">[!code-csharp[BreakStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L99-L108)]</span></span>

* <span data-ttu-id="63c5d-143">`continue`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="63c5d-143">`continue` statement:</span></span>

 <span data-ttu-id="63c5d-144">[!code-csharp[ContinueStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L110-L118)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-144">[!code-csharp[ContinueStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L110-L118)]</span></span>

* <span data-ttu-id="63c5d-145">`goto`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="63c5d-145">`goto` statement:</span></span>

 <span data-ttu-id="63c5d-146">[!code-csharp[GotoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L120-L129)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-146">[!code-csharp[GotoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L120-L129)]</span></span>

* <span data-ttu-id="63c5d-147">`return`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="63c5d-147">`return` statement:</span></span>

 <span data-ttu-id="63c5d-148">[!code-csharp[ReturnStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L131-L139)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-148">[!code-csharp[ReturnStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L131-L139)]</span></span>

* <span data-ttu-id="63c5d-149">`yield`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="63c5d-149">`yield` statement:</span></span>

 <span data-ttu-id="63c5d-150">[!code-csharp[YieldStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L141-L155)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-150">[!code-csharp[YieldStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L141-L155)]</span></span>

* <span data-ttu-id="63c5d-151">`throw`-Anweisungen und `try`-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="63c5d-151">`throw` statements and `try` statements:</span></span>

 <span data-ttu-id="63c5d-152">[!code-csharp[TryThrow](../../../samples/snippets/csharp/tour/statements/Program.cs#L157-L183)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-152">[!code-csharp[TryThrow](../../../samples/snippets/csharp/tour/statements/Program.cs#L157-L183)]</span></span>

* <span data-ttu-id="63c5d-153">`checked`- und `unchecked`-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="63c5d-153">`checked` and `unchecked` statements:</span></span>

 <span data-ttu-id="63c5d-154">[!code-csharp[CheckedUncheckedStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L185-L196)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-154">[!code-csharp[CheckedUncheckedStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L185-L196)]</span></span>

* <span data-ttu-id="63c5d-155">`lock`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="63c5d-155">`lock` statement:</span></span>

 <span data-ttu-id="63c5d-156">[!code-csharp[LockStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L257-L273)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-156">[!code-csharp[LockStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L257-L273)]</span></span>

* <span data-ttu-id="63c5d-157">`using`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="63c5d-157">`using` statement:</span></span>

 <span data-ttu-id="63c5d-158">[!code-csharp[UsingStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L198-L206)]</span><span class="sxs-lookup"><span data-stu-id="63c5d-158">[!code-csharp[UsingStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L198-L206)]</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="63c5d-159">[Zurück](expressions.md)
[Weiter](classes-and-objects.md)</span><span class="sxs-lookup"><span data-stu-id="63c5d-159">[Previous](expressions.md)
[Next](classes-and-objects.md)</span></span>

