---
title: Codekonventionen für C# – C#-Programmierhandbuch
description: Erfahren Sie mehr über die Codekonventionen in C#. Codekonventionen sorgen für ein einheitliches Erscheinungsbild des Codes und vereinfachen das Kopieren, Ändern und Verwalten des Codes.
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
ms.openlocfilehash: 772aebff0b8c7aebe7c7d5c7634cd2931f4570b1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301852"
---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="823ff-104">Codekonventionen für C# (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="823ff-104">C# Coding Conventions (C# Programming Guide)</span></span>

<span data-ttu-id="823ff-105">Codierungskonventionen dienen den folgenden Zwecken:</span><span class="sxs-lookup"><span data-stu-id="823ff-105">Coding conventions serve the following purposes:</span></span>  
  
- <span data-ttu-id="823ff-106">Sie kreieren ein konsistentes Erscheinungsbild des Codes, sodass Leser sich auf den Inhalt und nicht auf das Layout konzentrieren können.</span><span class="sxs-lookup"><span data-stu-id="823ff-106">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
- <span data-ttu-id="823ff-107">Sie ermöglichen es den Lesern, Code schneller zu verstehen, da Rückschlüsse basierend auf den bisherigen Erfahrungen gezogen werden können.</span><span class="sxs-lookup"><span data-stu-id="823ff-107">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
- <span data-ttu-id="823ff-108">Sie erleichtern das Kopieren, Ändern und Pflegen des Codes.</span><span class="sxs-lookup"><span data-stu-id="823ff-108">They facilitate copying, changing, and maintaining the code.</span></span>  
  
- <span data-ttu-id="823ff-109">Sie zeigen die Best Practices für C#.</span><span class="sxs-lookup"><span data-stu-id="823ff-109">They demonstrate C# best practices.</span></span>  

<span data-ttu-id="823ff-110">Die Leitlinien in diesem Artikel werden von Microsoft befolgt, um Beispiele und Dokumentation zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="823ff-110">The guidelines in this article are used by Microsoft to develop samples and documentation.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="823ff-111">Namenskonventionen</span><span class="sxs-lookup"><span data-stu-id="823ff-111">Naming Conventions</span></span>  
  
- <span data-ttu-id="823ff-112">Verwenden Sie Namespacequalifizierungen in kurzen Beispielen, die keine [using-Anweisungen](../../language-reference/keywords/using-directive.md) umfassen.</span><span class="sxs-lookup"><span data-stu-id="823ff-112">In short examples that do not include [using directives](../../language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="823ff-113">Wenn Sie wissen, dass ein Namespace standardmäßig in ein Projekt importiert wird, müssen Sie den Namen aus diesem Namespace nicht voll qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="823ff-113">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="823ff-114">Qualifizierte Namen können nach einem Punkt (.) unterbrochen werden, wenn sie für eine einzelne Zeile zu lang sind, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="823ff-114">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
- <span data-ttu-id="823ff-115">Sie müssen nicht die Namen der Objekte ändern, die mit den Designertools von Visual Studio erstellt wurden, um sie an andere Richtlinien anzupassen.</span><span class="sxs-lookup"><span data-stu-id="823ff-115">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="823ff-116">Layoutkonventionen</span><span class="sxs-lookup"><span data-stu-id="823ff-116">Layout Conventions</span></span>  

<span data-ttu-id="823ff-117">Ein gutes Layout verwendet Formatierungen, um die Struktur des Codes hervorzuheben und um den Code verständlicher zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="823ff-117">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="823ff-118">Microsoft-Beispiele entsprechen den folgenden Konventionen:</span><span class="sxs-lookup"><span data-stu-id="823ff-118">Microsoft examples and samples conform to the following conventions:</span></span>  
  
- <span data-ttu-id="823ff-119">Verwenden Sie die Code-Editor-Standardeinstellungen (Intelligenter Einzug, vierstelliger Einzug, als Leerzeichen gespeicherte Tabulatoren).</span><span class="sxs-lookup"><span data-stu-id="823ff-119">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="823ff-120">Weitere Informationen finden Sie unter [Optionen, Text-Editor, C#, Formatierung](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span><span class="sxs-lookup"><span data-stu-id="823ff-120">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
- <span data-ttu-id="823ff-121">Schreiben Sie pro Zeile nur eine Anweisung.</span><span class="sxs-lookup"><span data-stu-id="823ff-121">Write only one statement per line.</span></span>  
  
- <span data-ttu-id="823ff-122">Schreiben Sie pro Zeile nur eine Deklaration.</span><span class="sxs-lookup"><span data-stu-id="823ff-122">Write only one declaration per line.</span></span>  
  
- <span data-ttu-id="823ff-123">Wenn Fortsetzungszeilen nicht automatisch eingezogen werden, rücken Sie diese um einen Tabstopp (vier Leerzeichen) ein.</span><span class="sxs-lookup"><span data-stu-id="823ff-123">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
- <span data-ttu-id="823ff-124">Fügen Sie zwischen Methoden- und Eigenschaftsdefinitionen mindestens eine Leerzeile ein.</span><span class="sxs-lookup"><span data-stu-id="823ff-124">Add at least one blank line between method definitions and property definitions.</span></span>  
  
- <span data-ttu-id="823ff-125">Verwenden Sie Klammern, um Klauseln in einem Ausdruck zu kennzeichnen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="823ff-125">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a><span data-ttu-id="823ff-126">Konventionen für Kommentare</span><span class="sxs-lookup"><span data-stu-id="823ff-126">Commenting Conventions</span></span>  
  
- <span data-ttu-id="823ff-127">Fügen Sie den Kommentar in einer eigenen Zeile und nicht am Ende einer Codezeile ein.</span><span class="sxs-lookup"><span data-stu-id="823ff-127">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
- <span data-ttu-id="823ff-128">Beginnen Sie Kommentartext mit einem Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="823ff-128">Begin comment text with an uppercase letter.</span></span>  
  
- <span data-ttu-id="823ff-129">Beenden Sie den Kommentartext mit einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="823ff-129">End comment text with a period.</span></span>  
  
- <span data-ttu-id="823ff-130">Fügen Sie ein Leerzeichen zwischen dem Kommentartrennzeichen (//) und dem Kommentartext ein, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="823ff-130">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
- <span data-ttu-id="823ff-131">Erstellen Sie keine formatierten Blöcke mit Sternchen um Kommentare.</span><span class="sxs-lookup"><span data-stu-id="823ff-131">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="823ff-132">Sprachrichtlinien</span><span class="sxs-lookup"><span data-stu-id="823ff-132">Language Guidelines</span></span>  

<span data-ttu-id="823ff-133">In den folgenden Abschnitten werden die Vorgehensweisen beschrieben, denen das C#-Team folgt, um Codebeispiele zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="823ff-133">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="823ff-134">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="823ff-134">String Data Type</span></span>  
  
- <span data-ttu-id="823ff-135">Verwenden Sie die [Zeichenfolgeninterpolation](../../language-reference/tokens/interpolated.md), um wie im folgenden Code gezeigt kurze Zeichenfolgen zu verketten.</span><span class="sxs-lookup"><span data-stu-id="823ff-135">Use [string interpolation](../../language-reference/tokens/interpolated.md) to concatenate short strings, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
- <span data-ttu-id="823ff-136">Verwenden Sie ein <xref:System.Text.StringBuilder>-Objekt, um Zeichenfolgen in Schleifen anzufügen, besonders bei der Arbeit mit großen Textmengen.</span><span class="sxs-lookup"><span data-stu-id="823ff-136">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="823ff-137">Implizit typisierte lokale Variablen</span><span class="sxs-lookup"><span data-stu-id="823ff-137">Implicitly Typed Local Variables</span></span>  
  
- <span data-ttu-id="823ff-138">Verwenden Sie die [implizite Typisierung](../classes-and-structs/implicitly-typed-local-variables.md) für lokale Variablen, wenn der Typ der Variablen auf der rechten Seite der Zuweisung offensichtlich ist oder wenn der genaue Typ nicht von Bedeutung ist.</span><span class="sxs-lookup"><span data-stu-id="823ff-138">Use [implicit typing](../classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
- <span data-ttu-id="823ff-139">Verwenden Sie nicht [var](../../language-reference/keywords/var.md), wenn der Typ nicht von der rechten Seite der Zuweisung offensichtlich ist.</span><span class="sxs-lookup"><span data-stu-id="823ff-139">Do not use [var](../../language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
- <span data-ttu-id="823ff-140">Verlassen Sie sich nicht auf den Variablennamen, um den Typ der Variable anzugeben.</span><span class="sxs-lookup"><span data-stu-id="823ff-140">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="823ff-141">Er ist unter Umständen nicht korrekt.</span><span class="sxs-lookup"><span data-stu-id="823ff-141">It might not be correct.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
- <span data-ttu-id="823ff-142">Vermeiden Sie den Einsatz von `var` anstelle von [dynamic](../../language-reference/builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="823ff-142">Avoid the use of `var` in place of [dynamic](../../language-reference/builtin-types/reference-types.md).</span></span>  
  
- <span data-ttu-id="823ff-143">Verwenden Sie die implizite Typisierung, um den Typ der Schleifenvariablen in [for](../../language-reference/keywords/for.md)-Schleifen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="823ff-143">Use implicit typing to determine the type of the loop variable in [for](../../language-reference/keywords/for.md) loops.</span></span>  
  
     <span data-ttu-id="823ff-144">Im folgenden Beispiel wird die implizite Typisierung in einer `for`-Anweisung verwendet.</span><span class="sxs-lookup"><span data-stu-id="823ff-144">The following example uses implicit typing in a `for` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  

- <span data-ttu-id="823ff-145">Verwenden Sie nicht die implizite Typisierung, um den Typ der Schleifenvariablen in [foreach](../../language-reference/keywords/foreach-in.md)-Schleifen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="823ff-145">Do not use implicit typing to determine the type of the loop variable in [foreach](../../language-reference/keywords/foreach-in.md) loops.</span></span>

     <span data-ttu-id="823ff-146">Im folgenden Beispiel wird die explizite Typisierung in einer `foreach`-Anweisung verwendet.</span><span class="sxs-lookup"><span data-stu-id="823ff-146">The following example uses explicit typing in a `foreach` statement.</span></span>

     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]

     > [!NOTE]
     > <span data-ttu-id="823ff-147">Achten Sie darauf, nicht versehentlich den Typ eines Elements in der Iterable-Sammlung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="823ff-147">Be careful not to accidentally change a type of an element of the iterable collection.</span></span> <span data-ttu-id="823ff-148">Beispielsweise ist es einfach, in einer `foreach`-Anweisung von <xref:System.Linq.IQueryable?displayProperty=nameWithType> zu <xref:System.Collections.IEnumerable?displayProperty=nameWithType> zu wechseln, was die Ausführung einer Abfrage ändert.</span><span class="sxs-lookup"><span data-stu-id="823ff-148">For example, it is easy to switch from <xref:System.Linq.IQueryable?displayProperty=nameWithType> to <xref:System.Collections.IEnumerable?displayProperty=nameWithType> in a `foreach` statement, which changes the execution of a query.</span></span>

### <a name="unsigned-data-type"></a><span data-ttu-id="823ff-149">Datentyp ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="823ff-149">Unsigned Data Type</span></span>  
  
<span data-ttu-id="823ff-150">Verwenden Sie im Allgemeinen `int` anstelle von Typen ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="823ff-150">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="823ff-151">Die Verwendung von `int` ist in C# üblich; durch den Einsatz von `int` wird die Interaktion mit anderen Bibliotheken vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="823ff-151">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="823ff-152">Arrays</span><span class="sxs-lookup"><span data-stu-id="823ff-152">Arrays</span></span>  
  
<span data-ttu-id="823ff-153">Verwenden Sie die präzise Syntax, wenn Sie Arrays in der Deklarationszeile initialisieren.</span><span class="sxs-lookup"><span data-stu-id="823ff-153">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a><span data-ttu-id="823ff-154">Delegaten</span><span class="sxs-lookup"><span data-stu-id="823ff-154">Delegates</span></span>  
  
<span data-ttu-id="823ff-155">Verwenden Sie die präzise Syntax, um Instanzen eines Delegattyps zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="823ff-155">Use the concise syntax to create instances of a delegate type.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
[!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="823ff-156">try-catch- und using-Anweisungen in der Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="823ff-156">try-catch and using Statements in Exception Handling</span></span>  
  
- <span data-ttu-id="823ff-157">Verwenden Sie eine [try-catch](../../language-reference/keywords/try-catch.md)-Anweisung für die meisten Ausnahmebehandlungen.</span><span class="sxs-lookup"><span data-stu-id="823ff-157">Use a [try-catch](../../language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
- <span data-ttu-id="823ff-158">Vereinfachen Sie den Code mithilfe der C#-Anweisung [using](../../language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="823ff-158">Simplify your code by using the C# [using statement](../../language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="823ff-159">Verwenden Sie bei einer [try-finally](../../language-reference/keywords/try-finally.md)-Anweisung, in der der einzige Code im `finally`-Block ein Aufruf der <xref:System.IDisposable.Dispose%2A>-Methode ist, stattdessen eine `using`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="823ff-159">If you have a [try-finally](../../language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="823ff-160">&&- und &#124;&#124;-Operatoren</span><span class="sxs-lookup"><span data-stu-id="823ff-160">&& and &#124;&#124; Operators</span></span>  
  
<span data-ttu-id="823ff-161">Vermeiden Sie Ausnahmen und erhöhen Sie die Leistung durch Überspringen von unnötigen Vergleichen, indem Sie [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) anstelle von [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) und [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) anstelle von [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) bei Vergleichen verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="823ff-161">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) instead of [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) and [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) instead of [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) when you perform comparisons, as shown in the following example.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a><span data-ttu-id="823ff-162">New-Operator</span><span class="sxs-lookup"><span data-stu-id="823ff-162">New Operator</span></span>  
  
- <span data-ttu-id="823ff-163">Verwenden Sie die präzise Form der Objektinstanziierung mit impliziter Typisierung, wie in der folgenden Deklaration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="823ff-163">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     <span data-ttu-id="823ff-164">Die vorherige Zeile entspricht der folgenden Deklaration.</span><span class="sxs-lookup"><span data-stu-id="823ff-164">The previous line is equivalent to the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
- <span data-ttu-id="823ff-165">Verwenden Sie Objektinitialisierer, um die Objekterstellung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="823ff-165">Use object initializers to simplify object creation.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a><span data-ttu-id="823ff-166">Ereignisbehandlung</span><span class="sxs-lookup"><span data-stu-id="823ff-166">Event Handling</span></span>  
  
<span data-ttu-id="823ff-167">Wenn Sie einen Ereignishandler definieren, den Sie später nicht entfernen müssen, verwenden Sie einen Lambdaausdruck.</span><span class="sxs-lookup"><span data-stu-id="823ff-167">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
[!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a><span data-ttu-id="823ff-168">Statische Member</span><span class="sxs-lookup"><span data-stu-id="823ff-168">Static Members</span></span>  
  
<span data-ttu-id="823ff-169">Rufen Sie [statische](../../language-reference/keywords/static.md) Member über diesen Klassennamen auf: *ClassName.StaticMember*.</span><span class="sxs-lookup"><span data-stu-id="823ff-169">Call [static](../../language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="823ff-170">Durch diese Empfehlung ist der Code besser lesbar, da der statische Zugriff eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="823ff-170">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="823ff-171">Qualifizieren Sie keinen statischen Member, der in einer Basisklasse mit dem Namen einer abgeleiteten Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="823ff-171">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="823ff-172">Während dieser Code kompiliert wird, ist die Lesbarkeit des Codes irreführend, und der Code kann später beschädigt werden, wenn Sie der abgeleiteten Klasse einen statischen Member mit dem gleichen Namen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="823ff-172">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="823ff-173">LINQ-Abfragen</span><span class="sxs-lookup"><span data-stu-id="823ff-173">LINQ Queries</span></span>  
  
- <span data-ttu-id="823ff-174">Verwenden Sie aussagekräftige Namen für Abfragevariablen.</span><span class="sxs-lookup"><span data-stu-id="823ff-174">Use meaningful names for query variables.</span></span> <span data-ttu-id="823ff-175">Im folgenden Beispiel wird `seattleCustomers` für Kunden in Seattle verwendet.</span><span class="sxs-lookup"><span data-stu-id="823ff-175">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- <span data-ttu-id="823ff-176">Verwenden Sie Aliase, um mithilfe der Pascal-Schreibweise sicherzustellen, dass die korrekte Großschreibung von Eigenschaftennamen anonymer Typen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="823ff-176">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
- <span data-ttu-id="823ff-177">Benennen Sie Eigenschaften um, wenn die Eigenschaftennamen im Ergebnis nicht eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="823ff-177">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="823ff-178">Wenn die Abfrage beispielsweise einen Kundennamen und eine Händler-ID zurückgibt, anstatt sie als `Name` und `ID` im Ergebnis beizubehalten, benennen Sie sie um, um zu verdeutlichen, dass `Name` der Name eines Kunden und `ID` die ID eines Händlers ist.</span><span class="sxs-lookup"><span data-stu-id="823ff-178">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
- <span data-ttu-id="823ff-179">Verwenden Sie die implizierte Typisierung in der Deklaration von Abfragevariablen und Bereichsvariablen.</span><span class="sxs-lookup"><span data-stu-id="823ff-179">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- <span data-ttu-id="823ff-180">Richten Sie Abfrageklauseln unter der [from](../../language-reference/keywords/from-clause.md)-Klausel aus, wie in den vorherigen Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="823ff-180">Align query clauses under the [from](../../language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
- <span data-ttu-id="823ff-181">Verwenden Sie vor anderen Abfrageklauseln [where](../../language-reference/keywords/where-clause.md)-Klauseln, um sicherzustellen, dass nachfolgende Abfrageklauseln für den reduzierten, gefilterten Datensatz ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="823ff-181">Use [where](../../language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
- <span data-ttu-id="823ff-182">Verwenden Sie mehrere `from`-Klauseln anstelle einer [join](../../language-reference/keywords/join-clause.md)-Klausel, um auf die inneren Auflistungen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="823ff-182">Use multiple `from` clauses instead of a [join](../../language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="823ff-183">Eine Auflistung von `Student`-Objekten kann beispielsweise jeweils eine Auflistung von Testergebnissen enthalten.</span><span class="sxs-lookup"><span data-stu-id="823ff-183">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="823ff-184">Wenn die folgende Abfrage ausgeführt wird, wird jedes Ergebnis über 90 zusammen mit dem Nachnamen des Studenten zurückgegeben, der das Testergebnis erzielt hat.</span><span class="sxs-lookup"><span data-stu-id="823ff-184">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a><span data-ttu-id="823ff-185">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="823ff-185">Security</span></span>  

<span data-ttu-id="823ff-186">Befolgen Sie die Richtlinien in [Richtlinien für das Schreiben von sicherem Code](../../../standard/security/secure-coding-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="823ff-186">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="823ff-187">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="823ff-187">See also</span></span>

- [<span data-ttu-id="823ff-188">Visual Basic-Codierungskonventionen</span><span class="sxs-lookup"><span data-stu-id="823ff-188">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)
- [<span data-ttu-id="823ff-189">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="823ff-189">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
