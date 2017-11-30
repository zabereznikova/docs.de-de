---
title: "Codekonventionen für C# (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: "32"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 84ddc2b3cebb6bad95f5076889de11f12624b4de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="d6a92-102">Codekonventionen für C# (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d6a92-102">C# Coding Conventions (C# Programming Guide)</span></span>
<span data-ttu-id="d6a92-103">Die [C#-Sprachspezifikation](http://go.microsoft.com/fwlink/?LinkId=199552) definiert keinen Codierungsstandard.</span><span class="sxs-lookup"><span data-stu-id="d6a92-103">The [C# Language Specification](http://go.microsoft.com/fwlink/?LinkId=199552) does not define a coding standard.</span></span> <span data-ttu-id="d6a92-104">Die Richtlinien in diesem Thema werden jedoch von Microsoft verwendet, um Beispiele und die Dokumentation zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="d6a92-104">However, the guidelines in this topic are used by Microsoft to develop samples and documentation.</span></span>  
  
 <span data-ttu-id="d6a92-105">Codierungskonventionen dienen den folgenden Zwecken:</span><span class="sxs-lookup"><span data-stu-id="d6a92-105">Coding conventions serve the following purposes:</span></span>  
  
-   <span data-ttu-id="d6a92-106">Sie kreieren ein konsistentes Erscheinungsbild des Codes, sodass Leser sich auf den Inhalt und nicht auf das Layout konzentrieren können.</span><span class="sxs-lookup"><span data-stu-id="d6a92-106">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="d6a92-107">Sie ermöglichen es den Lesern, Code schneller zu verstehen, da Rückschlüsse basierend auf den bisherigen Erfahrungen gezogen werden können.</span><span class="sxs-lookup"><span data-stu-id="d6a92-107">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="d6a92-108">Sie erleichtern das Kopieren, Ändern und Pflegen des Codes.</span><span class="sxs-lookup"><span data-stu-id="d6a92-108">They facilitate copying, changing, and maintaining the code.</span></span>  
  
-   <span data-ttu-id="d6a92-109">Sie zeigen die Best Practices für C#.</span><span class="sxs-lookup"><span data-stu-id="d6a92-109">They demonstrate C# best practices.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="d6a92-110">Namenskonventionen</span><span class="sxs-lookup"><span data-stu-id="d6a92-110">Naming Conventions</span></span>  
  
-   <span data-ttu-id="d6a92-111">Verwenden Sie Namespacequalifizierungen in kurzen Beispielen, die keine [using-Anweisungen](../../../csharp/language-reference/keywords/using-directive.md) umfassen.</span><span class="sxs-lookup"><span data-stu-id="d6a92-111">In short examples that do not include [using directives](../../../csharp/language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="d6a92-112">Wenn Sie wissen, dass ein Namespace standardmäßig in ein Projekt importiert wird, müssen Sie den Namen aus diesem Namespace nicht voll qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="d6a92-112">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="d6a92-113">Qualifizierte Namen können nach einem Punkt (.) unterbrochen werden, wenn sie für eine einzelne Zeile zu lang sind, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6a92-113">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
-   <span data-ttu-id="d6a92-114">Sie müssen nicht die Namen der Objekte ändern, die mit den Designertools von Visual Studio erstellt wurden, um sie an andere Richtlinien anzupassen.</span><span class="sxs-lookup"><span data-stu-id="d6a92-114">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="d6a92-115">Layoutkonventionen</span><span class="sxs-lookup"><span data-stu-id="d6a92-115">Layout Conventions</span></span>  
 <span data-ttu-id="d6a92-116">Ein gutes Layout verwendet Formatierungen, um die Struktur des Codes hervorzuheben und um den Code verständlicher zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="d6a92-116">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="d6a92-117">Microsoft-Beispiele entsprechen den folgenden Konventionen:</span><span class="sxs-lookup"><span data-stu-id="d6a92-117">Microsoft examples and samples conform to the following conventions:</span></span>  
  
-   <span data-ttu-id="d6a92-118">Verwenden Sie die Code-Editor-Standardeinstellungen (Intelligenter Einzug, vierstelliger Einzug, als Leerzeichen gespeicherte Tabulatoren).</span><span class="sxs-lookup"><span data-stu-id="d6a92-118">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="d6a92-119">Weitere Informationen finden Sie unter [Optionen, Text-Editor, C#, Formatierung](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span><span class="sxs-lookup"><span data-stu-id="d6a92-119">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
-   <span data-ttu-id="d6a92-120">Schreiben Sie pro Zeile nur eine Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d6a92-120">Write only one statement per line.</span></span>  
  
-   <span data-ttu-id="d6a92-121">Schreiben Sie pro Zeile nur eine Deklaration.</span><span class="sxs-lookup"><span data-stu-id="d6a92-121">Write only one declaration per line.</span></span>  
  
-   <span data-ttu-id="d6a92-122">Wenn Fortsetzungszeilen nicht automatisch eingezogen werden, rücken Sie diese um einen Tabstopp (vier Leerzeichen) ein.</span><span class="sxs-lookup"><span data-stu-id="d6a92-122">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
-   <span data-ttu-id="d6a92-123">Fügen Sie zwischen Methoden- und Eigenschaftsdefinitionen mindestens eine Leerzeile ein.</span><span class="sxs-lookup"><span data-stu-id="d6a92-123">Add at least one blank line between method definitions and property definitions.</span></span>  
  
-   <span data-ttu-id="d6a92-124">Verwenden Sie Klammern, um Klauseln in einem Ausdruck zu kennzeichnen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6a92-124">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a><span data-ttu-id="d6a92-125">Konventionen für Kommentare</span><span class="sxs-lookup"><span data-stu-id="d6a92-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="d6a92-126">Fügen Sie den Kommentar in einer eigenen Zeile und nicht am Ende einer Codezeile ein.</span><span class="sxs-lookup"><span data-stu-id="d6a92-126">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="d6a92-127">Beginnen Sie Kommentartext mit einem Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="d6a92-127">Begin comment text with an uppercase letter.</span></span>  
  
-   <span data-ttu-id="d6a92-128">Beenden Sie den Kommentartext mit einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="d6a92-128">End comment text with a period.</span></span>  
  
-   <span data-ttu-id="d6a92-129">Fügen Sie ein Leerzeichen zwischen dem Kommentartrennzeichen (//) und dem Kommentartext ein, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6a92-129">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
-   <span data-ttu-id="d6a92-130">Erstellen Sie keine formatierten Blöcke mit Sternchen um Kommentare.</span><span class="sxs-lookup"><span data-stu-id="d6a92-130">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="d6a92-131">Sprachrichtlinien</span><span class="sxs-lookup"><span data-stu-id="d6a92-131">Language Guidelines</span></span>  
 <span data-ttu-id="d6a92-132">In den folgenden Abschnitten werden die Vorgehensweisen beschrieben, denen das C#-Team folgt, um Codebeispiele zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d6a92-132">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="d6a92-133">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="d6a92-133">String Data Type</span></span>  
  
-   <span data-ttu-id="d6a92-134">Verwenden Sie den `+`-Operator, um kurze Zeichenfolgen zu verketten, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6a92-134">Use the `+` operator to concatenate short strings, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
-   <span data-ttu-id="d6a92-135">Verwenden Sie ein <xref:System.Text.StringBuilder>-Objekt, um Zeichenfolgen in Schleifen anzufügen, besonders bei der Arbeit mit großen Textmengen.</span><span class="sxs-lookup"><span data-stu-id="d6a92-135">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="d6a92-136">Implizit typisierte lokale Variablen</span><span class="sxs-lookup"><span data-stu-id="d6a92-136">Implicitly Typed Local Variables</span></span>  
  
-   <span data-ttu-id="d6a92-137">Verwenden Sie die [implizite Typisierung](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) für lokale Variablen, wenn der Typ der Variablen auf der rechten Seite der Zuweisung offensichtlich ist oder wenn der genaue Typ nicht von Bedeutung ist.</span><span class="sxs-lookup"><span data-stu-id="d6a92-137">Use [implicit typing](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
-   <span data-ttu-id="d6a92-138">Verwenden Sie nicht [var](../../../csharp/language-reference/keywords/var.md), wenn der Typ nicht von der rechten Seite der Zuweisung offensichtlich ist.</span><span class="sxs-lookup"><span data-stu-id="d6a92-138">Do not use [var](../../../csharp/language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
-   <span data-ttu-id="d6a92-139">Verlassen Sie sich nicht auf den Variablennamen, um den Typ der Variable anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d6a92-139">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="d6a92-140">Er ist unter Umständen nicht korrekt.</span><span class="sxs-lookup"><span data-stu-id="d6a92-140">It might not be correct.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
-   <span data-ttu-id="d6a92-141">Vermeiden Sie den Einsatz von `var` anstelle von [dynamic](../../../csharp/language-reference/keywords/dynamic.md).</span><span class="sxs-lookup"><span data-stu-id="d6a92-141">Avoid the use of `var` in place of [dynamic](../../../csharp/language-reference/keywords/dynamic.md).</span></span>  
  
-   <span data-ttu-id="d6a92-142">Verwenden Sie die implizite Typisierung, um den Typ der Schleifenvariablen in [for](../../../csharp/language-reference/keywords/for.md)- und [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Schleifen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="d6a92-142">Use implicit typing to determine the type of the loop variable in [for](../../../csharp/language-reference/keywords/for.md) and [foreach](../../../csharp/language-reference/keywords/foreach-in.md) loops.</span></span>  
  
     <span data-ttu-id="d6a92-143">Im folgenden Beispiel wird die implizite Typisierung in einer `for`-Anweisung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6a92-143">The following example uses implicit typing in a `for` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#11](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#11)]  
  
     <span data-ttu-id="d6a92-144">Im folgenden Beispiel wird die implizite Typisierung in einer `foreach`-Anweisung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6a92-144">The following example uses implicit typing in a `foreach` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="d6a92-145">Datentyp ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="d6a92-145">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="d6a92-146">Verwenden Sie im Allgemeinen `int` anstelle von Typen ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="d6a92-146">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="d6a92-147">Die Verwendung von `int` ist in C# üblich; durch den Einsatz von `int` wird die Interaktion mit anderen Bibliotheken vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="d6a92-147">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="d6a92-148">Arrays</span><span class="sxs-lookup"><span data-stu-id="d6a92-148">Arrays</span></span>  
  
-   <span data-ttu-id="d6a92-149">Verwenden Sie die präzise Syntax, wenn Sie Arrays in der Deklarationszeile initialisieren.</span><span class="sxs-lookup"><span data-stu-id="d6a92-149">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a><span data-ttu-id="d6a92-150">Delegate</span><span class="sxs-lookup"><span data-stu-id="d6a92-150">Delegates</span></span>  
  
-   <span data-ttu-id="d6a92-151">Verwenden Sie die präzise Syntax, um Instanzen eines Delegattyps zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d6a92-151">Use the concise syntax to create instances of a delegate type.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
     [!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="d6a92-152">try-catch- und using-Anweisungen in der Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="d6a92-152">try-catch and using Statements in Exception Handling</span></span>  
  
-   <span data-ttu-id="d6a92-153">Verwenden Sie eine [try-catch](../../../csharp/language-reference/keywords/try-catch.md)-Anweisung für die meisten Ausnahmebehandlungen.</span><span class="sxs-lookup"><span data-stu-id="d6a92-153">Use a [try-catch](../../../csharp/language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
-   <span data-ttu-id="d6a92-154">Vereinfachen Sie den Code mithilfe der C#-Anweisung [using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d6a92-154">Simplify your code by using the C# [using statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="d6a92-155">Verwenden Sie bei einer [try-finally](../../../csharp/language-reference/keywords/try-finally.md)-Anweisung, in der der einzige Code im `finally`-Block ein Aufruf der <xref:System.IDisposable.Dispose%2A>-Methode ist, stattdessen eine `using`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d6a92-155">If you have a [try-finally](../../../csharp/language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="d6a92-156">&&- und &#124;&#124;-Operatoren</span><span class="sxs-lookup"><span data-stu-id="d6a92-156">&& and &#124;&#124; Operators</span></span>  
  
-   <span data-ttu-id="d6a92-157">Vermeiden Sie Ausnahmen und erhöhen Sie die Leistung durch Überspringen von unnötigen Vergleichen, indem Sie [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) anstelle von [&](../../../csharp/language-reference/operators/and-operator.md) und [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) anstelle von [&#124;](../../../csharp/language-reference/operators/or-operator.md) bei Vergleichen verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6a92-157">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) instead of [&](../../../csharp/language-reference/operators/and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) instead of [&#124;](../../../csharp/language-reference/operators/or-operator.md) when you perform comparisons, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a><span data-ttu-id="d6a92-158">New-Operator</span><span class="sxs-lookup"><span data-stu-id="d6a92-158">New Operator</span></span>  
  
-   <span data-ttu-id="d6a92-159">Verwenden Sie die präzise Form der Objektinstanziierung mit impliziter Typisierung, wie in der folgenden Deklaration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d6a92-159">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     <span data-ttu-id="d6a92-160">Die vorherige Zeile entspricht der folgenden Deklaration.</span><span class="sxs-lookup"><span data-stu-id="d6a92-160">The previous line is equivalent to the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
-   <span data-ttu-id="d6a92-161">Verwenden Sie Objektinitialisierer, um die Objekterstellung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="d6a92-161">Use object initializers to simplify object creation.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a><span data-ttu-id="d6a92-162">Ereignisbehandlung</span><span class="sxs-lookup"><span data-stu-id="d6a92-162">Event Handling</span></span>  
  
-   <span data-ttu-id="d6a92-163">Wenn Sie einen Ereignishandler definieren, den Sie später nicht entfernen müssen, verwenden Sie einen Lambda-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="d6a92-163">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
     [!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a><span data-ttu-id="d6a92-164">Statische Member</span><span class="sxs-lookup"><span data-stu-id="d6a92-164">Static Members</span></span>  
  
-   <span data-ttu-id="d6a92-165">Rufen Sie [statische](../../../csharp/language-reference/keywords/static.md) Member über den Klassennamen *ClassName.StaticMember* auf.</span><span class="sxs-lookup"><span data-stu-id="d6a92-165">Call [static](../../../csharp/language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="d6a92-166">Durch diese Empfehlung ist der Code besser lesbar, da der statische Zugriff eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="d6a92-166">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="d6a92-167">Qualifizieren Sie keinen statischen Member, der in einer Basisklasse mit dem Namen einer abgeleiteten Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d6a92-167">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="d6a92-168">Während dieser Code kompiliert wird, ist die Lesbarkeit des Codes irreführend, und der Code kann später beschädigt werden, wenn Sie der abgeleiteten Klasse einen statischen Member mit dem gleichen Namen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6a92-168">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="d6a92-169">LINQ-Abfragen</span><span class="sxs-lookup"><span data-stu-id="d6a92-169">LINQ Queries</span></span>  
  
-   <span data-ttu-id="d6a92-170">Verwenden Sie aussagekräftige Namen für Abfragevariablen.</span><span class="sxs-lookup"><span data-stu-id="d6a92-170">Use meaningful names for query variables.</span></span> <span data-ttu-id="d6a92-171">Im folgenden Beispiel wird `seattleCustomers` für Kunden in Seattle verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6a92-171">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
-   <span data-ttu-id="d6a92-172">Verwenden Sie Aliase, um mithilfe der Pascal-Schreibweise sicherzustellen, dass die korrekte Großschreibung von Eigenschaftennamen anonymer Typen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d6a92-172">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
-   <span data-ttu-id="d6a92-173">Benennen Sie Eigenschaften um, wenn die Eigenschaftennamen im Ergebnis nicht eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="d6a92-173">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="d6a92-174">Wenn die Abfrage beispielsweise einen Kundennamen und eine Händler-ID zurückgibt, anstatt sie als `Name` und `ID` im Ergebnis beizubehalten, benennen Sie sie um, um zu verdeutlichen, dass `Name` der Name eines Kunden und `ID` die ID eines Händlers ist.</span><span class="sxs-lookup"><span data-stu-id="d6a92-174">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
-   <span data-ttu-id="d6a92-175">Verwenden Sie die implizierte Typisierung in der Deklaration von Abfragevariablen und Bereichsvariablen.</span><span class="sxs-lookup"><span data-stu-id="d6a92-175">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
-   <span data-ttu-id="d6a92-176">Richten Sie Abfrageklauseln unter der [from](../../../csharp/language-reference/keywords/from-clause.md)-Klausel aus, wie in den vorherigen Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6a92-176">Align query clauses under the [from](../../../csharp/language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
-   <span data-ttu-id="d6a92-177">Verwenden Sie vor anderen Abfrageklauseln [where](../../../csharp/language-reference/keywords/where-clause.md)-Klauseln, um sicherzustellen, dass nachfolgende Abfrageklauseln für den reduzierten, gefilterten Datensatz ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d6a92-177">Use [where](../../../csharp/language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
-   <span data-ttu-id="d6a92-178">Verwenden Sie mehrere `from`-Klauseln anstelle einer [join](../../../csharp/language-reference/keywords/join-clause.md)-Klausel, um auf die inneren Auflistungen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d6a92-178">Use multiple `from` clauses instead of a [join](../../../csharp/language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="d6a92-179">Eine Auflistung von `Student`-Objekten kann beispielsweise jeweils eine Auflistung von Testergebnissen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d6a92-179">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="d6a92-180">Wenn die folgende Abfrage ausgeführt wird, wird jedes Ergebnis über 90 zusammen mit dem Nachnamen des Studenten zurückgegeben, der das Testergebnis erzielt hat.</span><span class="sxs-lookup"><span data-stu-id="d6a92-180">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a><span data-ttu-id="d6a92-181">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d6a92-181">Security</span></span>  
 <span data-ttu-id="d6a92-182">Befolgen Sie die Richtlinien in [Richtlinien für das Schreiben von sicherem Code](../../../standard/security/secure-coding-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="d6a92-182">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6a92-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6a92-183">See Also</span></span>  
 [<span data-ttu-id="d6a92-184">Visual Basic-Codierungskonventionen</span><span class="sxs-lookup"><span data-stu-id="d6a92-184">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 [<span data-ttu-id="d6a92-185">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="d6a92-185">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
