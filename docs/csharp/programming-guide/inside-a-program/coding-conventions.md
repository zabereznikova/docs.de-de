---
title: Codekonventionen für C# – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
ms.openlocfilehash: 42e1814af38fa442255f6da79fb4862ce3d0f361
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423203"
---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="71191-102">Codekonventionen für C# (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="71191-102">C# Coding Conventions (C# Programming Guide)</span></span>
 <span data-ttu-id="71191-103">Codierungskonventionen dienen den folgenden Zwecken:</span><span class="sxs-lookup"><span data-stu-id="71191-103">Coding conventions serve the following purposes:</span></span>  
  
- <span data-ttu-id="71191-104">Sie kreieren ein konsistentes Erscheinungsbild des Codes, sodass Leser sich auf den Inhalt und nicht auf das Layout konzentrieren können.</span><span class="sxs-lookup"><span data-stu-id="71191-104">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
- <span data-ttu-id="71191-105">Sie ermöglichen es den Lesern, Code schneller zu verstehen, da Rückschlüsse basierend auf den bisherigen Erfahrungen gezogen werden können.</span><span class="sxs-lookup"><span data-stu-id="71191-105">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
- <span data-ttu-id="71191-106">Sie erleichtern das Kopieren, Ändern und Pflegen des Codes.</span><span class="sxs-lookup"><span data-stu-id="71191-106">They facilitate copying, changing, and maintaining the code.</span></span>  
  
- <span data-ttu-id="71191-107">Sie zeigen die Best Practices für C#.</span><span class="sxs-lookup"><span data-stu-id="71191-107">They demonstrate C# best practices.</span></span>  

 <span data-ttu-id="71191-108">Die Richtlinien in diesem Thema werden von Microsoft verwendet, um Beispiele und die Dokumentation zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="71191-108">The guidelines in this topic are used by Microsoft to develop samples and documentation.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="71191-109">Namenskonventionen</span><span class="sxs-lookup"><span data-stu-id="71191-109">Naming Conventions</span></span>  
  
- <span data-ttu-id="71191-110">Verwenden Sie Namespacequalifizierungen in kurzen Beispielen, die keine [using-Anweisungen](../../language-reference/keywords/using-directive.md) umfassen.</span><span class="sxs-lookup"><span data-stu-id="71191-110">In short examples that do not include [using directives](../../language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="71191-111">Wenn Sie wissen, dass ein Namespace standardmäßig in ein Projekt importiert wird, müssen Sie den Namen aus diesem Namespace nicht voll qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="71191-111">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="71191-112">Qualifizierte Namen können nach einem Punkt (.) unterbrochen werden, wenn sie für eine einzelne Zeile zu lang sind, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="71191-112">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
- <span data-ttu-id="71191-113">Sie müssen nicht die Namen der Objekte ändern, die mit den Designertools von Visual Studio erstellt wurden, um sie an andere Richtlinien anzupassen.</span><span class="sxs-lookup"><span data-stu-id="71191-113">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="71191-114">Layoutkonventionen</span><span class="sxs-lookup"><span data-stu-id="71191-114">Layout Conventions</span></span>  
 <span data-ttu-id="71191-115">Ein gutes Layout verwendet Formatierungen, um die Struktur des Codes hervorzuheben und um den Code verständlicher zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="71191-115">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="71191-116">Microsoft-Beispiele entsprechen den folgenden Konventionen:</span><span class="sxs-lookup"><span data-stu-id="71191-116">Microsoft examples and samples conform to the following conventions:</span></span>  
  
- <span data-ttu-id="71191-117">Verwenden Sie die Code-Editor-Standardeinstellungen (Intelligenter Einzug, vierstelliger Einzug, als Leerzeichen gespeicherte Tabulatoren).</span><span class="sxs-lookup"><span data-stu-id="71191-117">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="71191-118">Weitere Informationen finden Sie unter [Optionen, Text-Editor, C#, Formatierung](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span><span class="sxs-lookup"><span data-stu-id="71191-118">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
- <span data-ttu-id="71191-119">Schreiben Sie pro Zeile nur eine Anweisung.</span><span class="sxs-lookup"><span data-stu-id="71191-119">Write only one statement per line.</span></span>  
  
- <span data-ttu-id="71191-120">Schreiben Sie pro Zeile nur eine Deklaration.</span><span class="sxs-lookup"><span data-stu-id="71191-120">Write only one declaration per line.</span></span>  
  
- <span data-ttu-id="71191-121">Wenn Fortsetzungszeilen nicht automatisch eingezogen werden, rücken Sie diese um einen Tabstopp (vier Leerzeichen) ein.</span><span class="sxs-lookup"><span data-stu-id="71191-121">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
- <span data-ttu-id="71191-122">Fügen Sie zwischen Methoden- und Eigenschaftsdefinitionen mindestens eine Leerzeile ein.</span><span class="sxs-lookup"><span data-stu-id="71191-122">Add at least one blank line between method definitions and property definitions.</span></span>  
  
- <span data-ttu-id="71191-123">Verwenden Sie Klammern, um Klauseln in einem Ausdruck zu kennzeichnen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="71191-123">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a><span data-ttu-id="71191-124">Konventionen für Kommentare</span><span class="sxs-lookup"><span data-stu-id="71191-124">Commenting Conventions</span></span>  
  
- <span data-ttu-id="71191-125">Fügen Sie den Kommentar in einer eigenen Zeile und nicht am Ende einer Codezeile ein.</span><span class="sxs-lookup"><span data-stu-id="71191-125">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
- <span data-ttu-id="71191-126">Beginnen Sie Kommentartext mit einem Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="71191-126">Begin comment text with an uppercase letter.</span></span>  
  
- <span data-ttu-id="71191-127">Beenden Sie den Kommentartext mit einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="71191-127">End comment text with a period.</span></span>  
  
- <span data-ttu-id="71191-128">Fügen Sie ein Leerzeichen zwischen dem Kommentartrennzeichen (//) und dem Kommentartext ein, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="71191-128">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
- <span data-ttu-id="71191-129">Erstellen Sie keine formatierten Blöcke mit Sternchen um Kommentare.</span><span class="sxs-lookup"><span data-stu-id="71191-129">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="71191-130">Sprachrichtlinien</span><span class="sxs-lookup"><span data-stu-id="71191-130">Language Guidelines</span></span>  
 <span data-ttu-id="71191-131">In den folgenden Abschnitten werden die Vorgehensweisen beschrieben, denen das C#-Team folgt, um Codebeispiele zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="71191-131">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="71191-132">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="71191-132">String Data Type</span></span>  
  
- <span data-ttu-id="71191-133">Verwenden Sie die [Zeichenfolgeninterpolation](../../language-reference/tokens/interpolated.md), um wie im folgenden Code gezeigt kurze Zeichenfolgen zu verketten.</span><span class="sxs-lookup"><span data-stu-id="71191-133">Use [string interpolation](../../language-reference/tokens/interpolated.md) to concatenate short strings, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
- <span data-ttu-id="71191-134">Verwenden Sie ein <xref:System.Text.StringBuilder>-Objekt, um Zeichenfolgen in Schleifen anzufügen, besonders bei der Arbeit mit großen Textmengen.</span><span class="sxs-lookup"><span data-stu-id="71191-134">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="71191-135">Implizit typisierte lokale Variablen</span><span class="sxs-lookup"><span data-stu-id="71191-135">Implicitly Typed Local Variables</span></span>  
  
- <span data-ttu-id="71191-136">Verwenden Sie die [implizite Typisierung](../classes-and-structs/implicitly-typed-local-variables.md) für lokale Variablen, wenn der Typ der Variablen auf der rechten Seite der Zuweisung offensichtlich ist oder wenn der genaue Typ nicht von Bedeutung ist.</span><span class="sxs-lookup"><span data-stu-id="71191-136">Use [implicit typing](../classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
- <span data-ttu-id="71191-137">Verwenden Sie nicht [var](../../language-reference/keywords/var.md), wenn der Typ nicht von der rechten Seite der Zuweisung offensichtlich ist.</span><span class="sxs-lookup"><span data-stu-id="71191-137">Do not use [var](../../language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
- <span data-ttu-id="71191-138">Verlassen Sie sich nicht auf den Variablennamen, um den Typ der Variable anzugeben.</span><span class="sxs-lookup"><span data-stu-id="71191-138">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="71191-139">Er ist unter Umständen nicht korrekt.</span><span class="sxs-lookup"><span data-stu-id="71191-139">It might not be correct.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
- <span data-ttu-id="71191-140">Vermeiden Sie den Einsatz von `var` anstelle von [dynamic](../../language-reference/builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="71191-140">Avoid the use of `var` in place of [dynamic](../../language-reference/builtin-types/reference-types.md).</span></span>  
  
- <span data-ttu-id="71191-141">Verwenden Sie die implizite Typisierung, um den Typ der Schleifenvariablen in [for](../../language-reference/keywords/for.md)- und [foreach](../../language-reference/keywords/foreach-in.md)-Schleifen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="71191-141">Use implicit typing to determine the type of the loop variable in [for](../../language-reference/keywords/for.md) and [foreach](../../language-reference/keywords/foreach-in.md) loops.</span></span>  
  
     <span data-ttu-id="71191-142">Im folgenden Beispiel wird die implizite Typisierung in einer `for`-Anweisung verwendet.</span><span class="sxs-lookup"><span data-stu-id="71191-142">The following example uses implicit typing in a `for` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
     <span data-ttu-id="71191-143">Im folgenden Beispiel wird die implizite Typisierung in einer `foreach`-Anweisung verwendet.</span><span class="sxs-lookup"><span data-stu-id="71191-143">The following example uses implicit typing in a `foreach` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="71191-144">Datentyp ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="71191-144">Unsigned Data Type</span></span>  
  
- <span data-ttu-id="71191-145">Verwenden Sie im Allgemeinen `int` anstelle von Typen ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="71191-145">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="71191-146">Die Verwendung von `int` ist in C# üblich; durch den Einsatz von `int` wird die Interaktion mit anderen Bibliotheken vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="71191-146">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="71191-147">Arrays</span><span class="sxs-lookup"><span data-stu-id="71191-147">Arrays</span></span>  
  
- <span data-ttu-id="71191-148">Verwenden Sie die präzise Syntax, wenn Sie Arrays in der Deklarationszeile initialisieren.</span><span class="sxs-lookup"><span data-stu-id="71191-148">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a><span data-ttu-id="71191-149">Delegaten</span><span class="sxs-lookup"><span data-stu-id="71191-149">Delegates</span></span>  
  
- <span data-ttu-id="71191-150">Verwenden Sie die präzise Syntax, um Instanzen eines Delegattyps zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="71191-150">Use the concise syntax to create instances of a delegate type.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
     [!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="71191-151">try-catch- und using-Anweisungen in der Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="71191-151">try-catch and using Statements in Exception Handling</span></span>  
  
- <span data-ttu-id="71191-152">Verwenden Sie eine [try-catch](../../language-reference/keywords/try-catch.md)-Anweisung für die meisten Ausnahmebehandlungen.</span><span class="sxs-lookup"><span data-stu-id="71191-152">Use a [try-catch](../../language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
- <span data-ttu-id="71191-153">Vereinfachen Sie den Code mithilfe der C#-Anweisung [using](../../language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="71191-153">Simplify your code by using the C# [using statement](../../language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="71191-154">Verwenden Sie bei einer [try-finally](../../language-reference/keywords/try-finally.md)-Anweisung, in der der einzige Code im `finally`-Block ein Aufruf der <xref:System.IDisposable.Dispose%2A>-Methode ist, stattdessen eine `using`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="71191-154">If you have a [try-finally](../../language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="71191-155">&&- und &#124;&#124;-Operatoren</span><span class="sxs-lookup"><span data-stu-id="71191-155">&& and &#124;&#124; Operators</span></span>  
  
- <span data-ttu-id="71191-156">Vermeiden Sie Ausnahmen und erhöhen Sie die Leistung durch Überspringen von unnötigen Vergleichen, indem Sie [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) anstelle von [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) und [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) anstelle von [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) bei Vergleichen verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="71191-156">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) instead of [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) and [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) instead of [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) when you perform comparisons, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a><span data-ttu-id="71191-157">New-Operator</span><span class="sxs-lookup"><span data-stu-id="71191-157">New Operator</span></span>  
  
- <span data-ttu-id="71191-158">Verwenden Sie die präzise Form der Objektinstanziierung mit impliziter Typisierung, wie in der folgenden Deklaration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="71191-158">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     <span data-ttu-id="71191-159">Die vorherige Zeile entspricht der folgenden Deklaration.</span><span class="sxs-lookup"><span data-stu-id="71191-159">The previous line is equivalent to the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
- <span data-ttu-id="71191-160">Verwenden Sie Objektinitialisierer, um die Objekterstellung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="71191-160">Use object initializers to simplify object creation.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a><span data-ttu-id="71191-161">Ereignisbehandlung</span><span class="sxs-lookup"><span data-stu-id="71191-161">Event Handling</span></span>  
  
- <span data-ttu-id="71191-162">Wenn Sie einen Ereignishandler definieren, den Sie später nicht entfernen müssen, verwenden Sie einen Lambdaausdruck.</span><span class="sxs-lookup"><span data-stu-id="71191-162">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
     [!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a><span data-ttu-id="71191-163">Statische Member</span><span class="sxs-lookup"><span data-stu-id="71191-163">Static Members</span></span>  
  
- <span data-ttu-id="71191-164">Rufen Sie [statische](../../language-reference/keywords/static.md) Member über diesen Klassennamen auf: *ClassName.StaticMember*.</span><span class="sxs-lookup"><span data-stu-id="71191-164">Call [static](../../language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="71191-165">Durch diese Empfehlung ist der Code besser lesbar, da der statische Zugriff eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="71191-165">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="71191-166">Qualifizieren Sie keinen statischen Member, der in einer Basisklasse mit dem Namen einer abgeleiteten Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="71191-166">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="71191-167">Während dieser Code kompiliert wird, ist die Lesbarkeit des Codes irreführend, und der Code kann später beschädigt werden, wenn Sie der abgeleiteten Klasse einen statischen Member mit dem gleichen Namen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="71191-167">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="71191-168">LINQ-Abfragen</span><span class="sxs-lookup"><span data-stu-id="71191-168">LINQ Queries</span></span>  
  
- <span data-ttu-id="71191-169">Verwenden Sie aussagekräftige Namen für Abfragevariablen.</span><span class="sxs-lookup"><span data-stu-id="71191-169">Use meaningful names for query variables.</span></span> <span data-ttu-id="71191-170">Im folgenden Beispiel wird `seattleCustomers` für Kunden in Seattle verwendet.</span><span class="sxs-lookup"><span data-stu-id="71191-170">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- <span data-ttu-id="71191-171">Verwenden Sie Aliase, um mithilfe der Pascal-Schreibweise sicherzustellen, dass die korrekte Großschreibung von Eigenschaftennamen anonymer Typen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="71191-171">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
- <span data-ttu-id="71191-172">Benennen Sie Eigenschaften um, wenn die Eigenschaftennamen im Ergebnis nicht eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="71191-172">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="71191-173">Wenn die Abfrage beispielsweise einen Kundennamen und eine Händler-ID zurückgibt, anstatt sie als `Name` und `ID` im Ergebnis beizubehalten, benennen Sie sie um, um zu verdeutlichen, dass `Name` der Name eines Kunden und `ID` die ID eines Händlers ist.</span><span class="sxs-lookup"><span data-stu-id="71191-173">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
- <span data-ttu-id="71191-174">Verwenden Sie die implizierte Typisierung in der Deklaration von Abfragevariablen und Bereichsvariablen.</span><span class="sxs-lookup"><span data-stu-id="71191-174">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- <span data-ttu-id="71191-175">Richten Sie Abfrageklauseln unter der [from](../../language-reference/keywords/from-clause.md)-Klausel aus, wie in den vorherigen Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="71191-175">Align query clauses under the [from](../../language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
- <span data-ttu-id="71191-176">Verwenden Sie vor anderen Abfrageklauseln [where](../../language-reference/keywords/where-clause.md)-Klauseln, um sicherzustellen, dass nachfolgende Abfrageklauseln für den reduzierten, gefilterten Datensatz ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="71191-176">Use [where](../../language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
- <span data-ttu-id="71191-177">Verwenden Sie mehrere `from`-Klauseln anstelle einer [join](../../language-reference/keywords/join-clause.md)-Klausel, um auf die inneren Auflistungen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="71191-177">Use multiple `from` clauses instead of a [join](../../language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="71191-178">Eine Auflistung von `Student`-Objekten kann beispielsweise jeweils eine Auflistung von Testergebnissen enthalten.</span><span class="sxs-lookup"><span data-stu-id="71191-178">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="71191-179">Wenn die folgende Abfrage ausgeführt wird, wird jedes Ergebnis über 90 zusammen mit dem Nachnamen des Studenten zurückgegeben, der das Testergebnis erzielt hat.</span><span class="sxs-lookup"><span data-stu-id="71191-179">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a><span data-ttu-id="71191-180">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="71191-180">Security</span></span>  
 <span data-ttu-id="71191-181">Befolgen Sie die Richtlinien in [Richtlinien für das Schreiben von sicherem Code](../../../standard/security/secure-coding-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="71191-181">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71191-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71191-182">See also</span></span>

- [<span data-ttu-id="71191-183">Visual Basic-Codierungskonventionen</span><span class="sxs-lookup"><span data-stu-id="71191-183">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)
- [<span data-ttu-id="71191-184">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="71191-184">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
