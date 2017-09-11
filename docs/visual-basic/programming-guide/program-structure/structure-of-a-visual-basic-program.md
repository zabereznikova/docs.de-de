---
title: Struktur eines Visual Basic-Programms | Microsoft-Dokumentation
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
- conditional compilation, Visual Basic
- program structure, Visual Basic
- procedures, structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
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
ms.openlocfilehash: 3e16ea51d0f766fcb5866cde89e5384a153ac050
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="structure-of-a-visual-basic-program"></a><span data-ttu-id="960d7-102">Struktur von Visual Basic-Programmen</span><span class="sxs-lookup"><span data-stu-id="960d7-102">Structure of a Visual Basic Program</span></span>
<span data-ttu-id="960d7-103">Ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Programm aus Standardbausteinen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="960d7-103">A [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program is built up from standard building blocks.</span></span> <span data-ttu-id="960d7-104">Ein *Lösung* umfasst eine oder mehrere Projekte.</span><span class="sxs-lookup"><span data-stu-id="960d7-104">A *solution* comprises one or more projects.</span></span> <span data-ttu-id="960d7-105">Ein *Projekt* wiederum kann eine oder mehrere Assemblys enthalten.</span><span class="sxs-lookup"><span data-stu-id="960d7-105">A *project* in turn can contain one or more assemblies.</span></span> <span data-ttu-id="960d7-106">Jede *Assembly* aus einer oder mehreren Quelldateien kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="960d7-106">Each *assembly* is compiled from one or more source files.</span></span> <span data-ttu-id="960d7-107">Ein *Quelldatei* enthält die Definition und Implementierung von Klassen, Strukturen, Module und Schnittstellen, die schließlich den gesamten Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="960d7-107">A *source file* provides the definition and implementation of classes, structures, modules, and interfaces, which ultimately contain all your code.</span></span>  
  
 <span data-ttu-id="960d7-108">Weitere Informationen über diese Bausteine einer [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programmieren, finden Sie unter [Projektmappen und Projekte](https://docs.microsoft.com/visualstudio/ide/solutions-and-projects-in-visual-studio) und [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).</span><span class="sxs-lookup"><span data-stu-id="960d7-108">For more information about these building blocks of a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program, see [Solutions and Projects](https://docs.microsoft.com/visualstudio/ide/solutions-and-projects-in-visual-studio) and [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
## <a name="file-level-programming-elements"></a><span data-ttu-id="960d7-109">Programmierelemente auf Dateiebene</span><span class="sxs-lookup"><span data-stu-id="960d7-109">File-Level Programming Elements</span></span>  
 <span data-ttu-id="960d7-110">Wenn Sie ein Projekt oder eine Datei starten und Code-Editor zu öffnen, sehen Sie Code bereits an Ort und in der richtigen Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="960d7-110">When you start a project or file and open the code editor, you see some code already in place and in the correct order.</span></span> <span data-ttu-id="960d7-111">Code, den Sie schreiben sollten Folgendes beachten:</span><span class="sxs-lookup"><span data-stu-id="960d7-111">Any code that you write should follow the following sequence:</span></span>  
  
1.  <span data-ttu-id="960d7-112">`Option`Anweisungen</span><span class="sxs-lookup"><span data-stu-id="960d7-112">`Option` statements</span></span>  
  
2.  <span data-ttu-id="960d7-113">`Imports`Anweisungen</span><span class="sxs-lookup"><span data-stu-id="960d7-113">`Imports` statements</span></span>  
  
3.  <span data-ttu-id="960d7-114">`Namespace`Anweisungen und Elemente auf Namespaceebene</span><span class="sxs-lookup"><span data-stu-id="960d7-114">`Namespace` statements and namespace-level elements</span></span>  
  
 <span data-ttu-id="960d7-115">Wenn Sie die Anweisungen in einer anderen Reihenfolge eingeben, können Kompilierungsfehler ergeben.</span><span class="sxs-lookup"><span data-stu-id="960d7-115">If you enter statements in a different order, compilation errors can result.</span></span>  
  
 <span data-ttu-id="960d7-116">Ein Programm kann auch Anweisungen für die bedingte Kompilierung enthalten.</span><span class="sxs-lookup"><span data-stu-id="960d7-116">A program can also contain conditional compilation statements.</span></span> <span data-ttu-id="960d7-117">Sie können diese in der Quelldatei zwischen der Anweisungen von der oben dargestellten Reihenfolge einzufügen.</span><span class="sxs-lookup"><span data-stu-id="960d7-117">You can intersperse these in the source file among the statements of the preceding sequence.</span></span>  
  
### <a name="option-statements"></a><span data-ttu-id="960d7-118">Optionsanweisungen</span><span class="sxs-lookup"><span data-stu-id="960d7-118">Option Statements</span></span>  
 <span data-ttu-id="960d7-119">`Option`Anweisungen richten Grundregeln für nachfolgende Code hilft Syntax-und Logikfehler zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="960d7-119">`Option` statements establish ground rules for subsequent code, helping prevent syntax and logic errors.</span></span> <span data-ttu-id="960d7-120">Die [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md) wird sichergestellt, dass alle Variablen deklariert und richtig ist geschrieben, die verringert wird.</span><span class="sxs-lookup"><span data-stu-id="960d7-120">The [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) ensures that all variables are declared and spelled correctly, which reduces debugging time.</span></span> <span data-ttu-id="960d7-121">Die [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md) trägt dazu bei, logischen Fehlern und Datenverlust zu minimieren, die beim Arbeiten mit Variablen unterschiedlichen Typs auftreten können.</span><span class="sxs-lookup"><span data-stu-id="960d7-121">The [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) helps to minimize logic errors and data loss that can occur when you work between variables of different data types.</span></span> <span data-ttu-id="960d7-122">Die [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md) gibt die Art des Zeichenfolgenvergleichs an, die basierend auf ihren `Binary` oder `Text` Werte.</span><span class="sxs-lookup"><span data-stu-id="960d7-122">The [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) specifies the way strings are compared to each other, based on either their `Binary` or `Text` values.</span></span>  
  
### <a name="imports-statements"></a><span data-ttu-id="960d7-123">Imports-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="960d7-123">Imports Statements</span></span>  
 <span data-ttu-id="960d7-124">Sie können einschließen einer [Imports-Anweisung (.NET Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) um außerhalb des Projekts definierte Namen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="960d7-124">You can include an [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to import names defined outside your project.</span></span> <span data-ttu-id="960d7-125">Eine `Imports` -Anweisung kann Code zum Verweisen auf Klassen und anderen Typen in den importierten Namespaces definiert werden, ohne sie qualifizieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="960d7-125">An `Imports` statement allows your code to refer to classes and other types defined within the imported namespace, without having to qualify them.</span></span> <span data-ttu-id="960d7-126">Sie können beliebig viele `Imports` Anweisungen nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="960d7-126">You can use as many `Imports` statements as appropriate.</span></span> <span data-ttu-id="960d7-127">Weitere Informationen finden Sie unter [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).</span><span class="sxs-lookup"><span data-stu-id="960d7-127">For more information, see [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).</span></span>  
  
### <a name="namespace-statements"></a><span data-ttu-id="960d7-128">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="960d7-128">Namespace Statements</span></span>  
 <span data-ttu-id="960d7-129">Namespaces können, die Sie verwalten und klassifizieren Programmierelemente Gruppierung und den Zugriff zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="960d7-129">Namespaces help you organize and classify your programming elements for ease of grouping and accessing.</span></span> <span data-ttu-id="960d7-130">Verwenden Sie die [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md) zum Klassifizieren von der folgenden Anweisungen in einem bestimmten Namespace.</span><span class="sxs-lookup"><span data-stu-id="960d7-130">You use the [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) to classify the following statements within a particular namespace.</span></span> <span data-ttu-id="960d7-131">Weitere Informationen finden Sie unter [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="960d7-131">For more information, see [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
### <a name="conditional-compilation-statements"></a><span data-ttu-id="960d7-132">Anweisungen für die bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="960d7-132">Conditional Compilation Statements</span></span>  
 <span data-ttu-id="960d7-133">Anweisungen für die bedingte Kompilierung können praktisch von überall in der Quelldatei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="960d7-133">Conditional compilation statements can appear almost anywhere in your source file.</span></span> <span data-ttu-id="960d7-134">Sie bewirken, dass Teile des Codes enthalten oder zur Kompilierzeit je nach Umständen ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="960d7-134">They cause parts of your code to be included or excluded at compile time depending on certain conditions.</span></span> <span data-ttu-id="960d7-135">Auch können diese zum Debuggen Ihrer Anwendung, da bedingter Code im Debugmodus nur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="960d7-135">You can also use them for debugging your application, because conditional code runs in debugging mode only.</span></span> <span data-ttu-id="960d7-136">Weitere Informationen finden Sie unter [bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="960d7-136">For more information, see [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).</span></span>  
  
## <a name="namespace-level-programming-elements"></a><span data-ttu-id="960d7-137">Namespace-Ebene Programmierelemente</span><span class="sxs-lookup"><span data-stu-id="960d7-137">Namespace-Level Programming Elements</span></span>  
 <span data-ttu-id="960d7-138">Klassen, Strukturen und Module enthalten den Code für die in der Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="960d7-138">Classes, structures, and modules contain all the code in your source file.</span></span> <span data-ttu-id="960d7-139">Sie sind *auf Namespaceebene* Elemente, die in einem Namespace oder auf der Ebene der Quelldatei angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="960d7-139">They are *namespace-level* elements, which can appear within a namespace or at the source file level.</span></span> <span data-ttu-id="960d7-140">Sie enthalten die Deklarationen aller anderen Programmierelemente.</span><span class="sxs-lookup"><span data-stu-id="960d7-140">They hold the declarations of all other programming elements.</span></span> <span data-ttu-id="960d7-141">Schnittstellen, die Elementsignaturen definieren, doch keine Implementierung bereitstellen, werden ebenfalls auf Modulebene.</span><span class="sxs-lookup"><span data-stu-id="960d7-141">Interfaces, which define element signatures but provide no implementation, also appear at module level.</span></span> <span data-ttu-id="960d7-142">Weitere Informationen zu den Elementen auf Modulebene finden Sie unter den folgenden:</span><span class="sxs-lookup"><span data-stu-id="960d7-142">For more information on the module-level elements, see the following:</span></span>  
  
-   [<span data-ttu-id="960d7-143">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="960d7-143">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [<span data-ttu-id="960d7-144">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="960d7-144">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [<span data-ttu-id="960d7-145">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="960d7-145">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [<span data-ttu-id="960d7-146">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="960d7-146">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 <span data-ttu-id="960d7-147">Datenelemente auf Namespaceebene sind Enumerationen und Delegaten.</span><span class="sxs-lookup"><span data-stu-id="960d7-147">Data elements at namespace level are enumerations and delegates.</span></span>  
  
## <a name="module-level-programming-elements"></a><span data-ttu-id="960d7-148">Programmierelemente auf Modulebene</span><span class="sxs-lookup"><span data-stu-id="960d7-148">Module-Level Programming Elements</span></span>  
 <span data-ttu-id="960d7-149">Prozeduren, Operatoren, Eigenschaften und Ereignisse sind die einzige Programmierelemente, die ausführbaren Code (Anweisungen, die Aktionen zur Laufzeit) enthalten können.</span><span class="sxs-lookup"><span data-stu-id="960d7-149">Procedures, operators, properties, and events are the only programming elements that can hold executable code (statements that perform actions at run time).</span></span> <span data-ttu-id="960d7-150">Sie sind der *auf Modulebene* Elemente Ihres Programms.</span><span class="sxs-lookup"><span data-stu-id="960d7-150">They are the *module-level* elements of your program.</span></span> <span data-ttu-id="960d7-151">Weitere Informationen zu Elementen auf Prozedurebene finden Sie unter den folgenden:</span><span class="sxs-lookup"><span data-stu-id="960d7-151">For more information on the procedure-level elements, see the following:</span></span>  
  
-   [<span data-ttu-id="960d7-152">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="960d7-152">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="960d7-153">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="960d7-153">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [<span data-ttu-id="960d7-154">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="960d7-154">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="960d7-155">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="960d7-155">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [<span data-ttu-id="960d7-156">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="960d7-156">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="960d7-157">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="960d7-157">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 <span data-ttu-id="960d7-158">Datenelemente auf Modulebene sind Variablen, Konstanten, Enumerationen und Delegaten.</span><span class="sxs-lookup"><span data-stu-id="960d7-158">Data elements at module level are variables, constants, enumerations, and delegates.</span></span>  
  
## <a name="procedure-level-programming-elements"></a><span data-ttu-id="960d7-159">Programmierelemente auf Prozedurebene</span><span class="sxs-lookup"><span data-stu-id="960d7-159">Procedure-Level Programming Elements</span></span>  
 <span data-ttu-id="960d7-160">Die meisten der Inhalte *auf Prozedurebene* Elemente sind ausführbare Anweisungen, die den Code zur Laufzeit des Programms zu bilden.</span><span class="sxs-lookup"><span data-stu-id="960d7-160">Most of the contents of *procedure-level* elements are executable statements, which constitute the run-time code of your program.</span></span> <span data-ttu-id="960d7-161">Der gesamte ausführbare Code muss in einer Prozedur (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span><span class="sxs-lookup"><span data-stu-id="960d7-161">All executable code must be in some procedure (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span></span> <span data-ttu-id="960d7-162">Weitere Informationen finden Sie unter [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="960d7-162">For more information, see [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
 <span data-ttu-id="960d7-163">Datenelemente auf Prozedurebene sind auf lokale Variablen und Konstanten beschränkt.</span><span class="sxs-lookup"><span data-stu-id="960d7-163">Data elements at procedure level are limited to local variables and constants.</span></span>  
  
## <a name="the-main-procedure"></a><span data-ttu-id="960d7-164">Die Main-Prozedur</span><span class="sxs-lookup"><span data-stu-id="960d7-164">The Main Procedure</span></span>  
 <span data-ttu-id="960d7-165">Die `Main` -Prozedur ist der erste Code ausgeführt wird, wenn die Anwendung geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="960d7-165">The `Main` procedure is the first code to run when your application has been loaded.</span></span> <span data-ttu-id="960d7-166">`Main`Dient als Ausgangspunkt und gesamtsteuerung für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="960d7-166">`Main` serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="960d7-167">Es gibt vier Arten von `Main`:</span><span class="sxs-lookup"><span data-stu-id="960d7-167">There are four varieties of `Main`:</span></span>  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 <span data-ttu-id="960d7-168">Die häufigste Variante dieser Prozedur ist `Sub Main()`.</span><span class="sxs-lookup"><span data-stu-id="960d7-168">The most common variety of this procedure is `Sub Main()`.</span></span> <span data-ttu-id="960d7-169">Weitere Informationen finden Sie unter [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="960d7-169">For more information, see [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="960d7-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="960d7-170">See Also</span></span>  
 <span data-ttu-id="960d7-171">[Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="960d7-171">[Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) </span></span>  
<span data-ttu-id="960d7-172"> [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="960d7-172"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span></span>  
<span data-ttu-id="960d7-173"> [Beschränkungen in Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)</span><span class="sxs-lookup"><span data-stu-id="960d7-173"> [Visual Basic Limitations](../../../visual-basic/programming-guide/program-structure/limitations.md)</span></span>
