---
title: Bedingte Kompilierung in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 4698435cb2ab15d16d8a8a898a01a9ffbc4f69c2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64639807"
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="67ee6-102">Bedingte Kompilierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67ee6-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="67ee6-103">In *für die bedingte Kompilierung*, selektiv bestimmte Codeblöcke in einem Programm kompiliert werden, während andere ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="67ee6-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="67ee6-104">Sie möchten z. B. Schreiben Debuggen-Anweisungen, die von der Geschwindigkeit der Ansätze mit den gleichen Programmiertask, oder Sie vergleichen kann eine Anwendung für mehrere Sprachen lokalisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="67ee6-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="67ee6-105">Anweisungen für die bedingte Kompilierung dienen, die während der Zeitpunkt der Kompilierung zur Laufzeit nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="67ee6-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="67ee6-106">Sie kennzeichnen Codeblöcke mit bedingt kompiliert werden die `#If...Then...#Else` Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="67ee6-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="67ee6-107">Z. B. Französisch und Deutsch-Sprache erstellen Versionen der gleichen Anwendung aus dem Quellcode, die Sie einbetten, plattformspezifischen Codesegmente in `#If...Then` Anweisungen, die mithilfe der definierten Konstanten `FrenchVersion` und `GermanVersion`.</span><span class="sxs-lookup"><span data-stu-id="67ee6-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="67ee6-108">Im folgende Beispiel wird veranschaulicht, wie:</span><span class="sxs-lookup"><span data-stu-id="67ee6-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 <span data-ttu-id="67ee6-109">Wenn Sie festlegen, dass den Wert des der `FrenchVersion` Konstante für bedingte Kompilierung auf `True` zum Zeitpunkt der Kompilierung der bedingte Code für die französische Version kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="67ee6-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="67ee6-110">Wenn Sie festlegen, dass den Wert des der `GermanVersion` zu Konstante `True`, verwendet der Compiler die deutsche Version.</span><span class="sxs-lookup"><span data-stu-id="67ee6-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="67ee6-111">Wenn keine, um festgelegt ist `True`, den Code in den letzten `Else` -Block ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="67ee6-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67ee6-112">Automatische Vervollständigung wird nicht die Funktion beim Bearbeiten von code und mit bedingten Kompilierungsdirektiven, wenn der Code nicht Teil von current Branch ist.</span><span class="sxs-lookup"><span data-stu-id="67ee6-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="67ee6-113">Deklarieren von Konstanten für bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="67ee6-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="67ee6-114">Sie können die Konstanten für bedingte Kompilierung in eine von drei Arten festlegen:</span><span class="sxs-lookup"><span data-stu-id="67ee6-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
- <span data-ttu-id="67ee6-115">In der **Projekt-Designer**</span><span class="sxs-lookup"><span data-stu-id="67ee6-115">In the **Project Designer**</span></span>  
  
- <span data-ttu-id="67ee6-116">In der Befehlszeile, wenn Sie den Befehlszeilencompiler verwenden</span><span class="sxs-lookup"><span data-stu-id="67ee6-116">At the command line when using the command-line compiler</span></span>  
  
- <span data-ttu-id="67ee6-117">In Ihrem code</span><span class="sxs-lookup"><span data-stu-id="67ee6-117">In your code</span></span>  
  
 <span data-ttu-id="67ee6-118">Bedingte Kompilierungskonstanten haben einen speziellen Bereich und können nicht aus dem Standardcode zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="67ee6-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="67ee6-119">Der Bereich einer Konstante für bedingte Kompilierung ist abhängig von der sie eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="67ee6-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="67ee6-120">Die folgende Tabelle enthält den Bereich der Konstanten, die mit jeder der drei oben genannten Methoden deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="67ee6-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="67ee6-121">Festlegung der Konstante</span><span class="sxs-lookup"><span data-stu-id="67ee6-121">How constant is set</span></span>|<span data-ttu-id="67ee6-122">Bereich der Konstante</span><span class="sxs-lookup"><span data-stu-id="67ee6-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="67ee6-123">**Projekt-Designer**</span><span class="sxs-lookup"><span data-stu-id="67ee6-123">**Project Designer**</span></span>|<span data-ttu-id="67ee6-124">Öffentlich für alle Dateien im Projekt</span><span class="sxs-lookup"><span data-stu-id="67ee6-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="67ee6-125">Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="67ee6-125">Command line</span></span>|<span data-ttu-id="67ee6-126">Öffentlich für alle Dateien, die an den Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="67ee6-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="67ee6-127">`#Const` -Anweisung in code</span><span class="sxs-lookup"><span data-stu-id="67ee6-127">`#Const` statement in code</span></span>|<span data-ttu-id="67ee6-128">Privat für die Datei, die in der sie deklariert ist</span><span class="sxs-lookup"><span data-stu-id="67ee6-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="67ee6-129">Zum Festlegen von Konstanten in den Projekt-Designer</span><span class="sxs-lookup"><span data-stu-id="67ee6-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="67ee6-130">– Bevor Sie die ausführbare Datei erstellen, legen Sie Konstanten der **Projekt-Designer** anhand der Schritte im [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties).</span><span class="sxs-lookup"><span data-stu-id="67ee6-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="67ee6-131">Konstanten in der Befehlszeile festlegen.</span><span class="sxs-lookup"><span data-stu-id="67ee6-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="67ee6-132">– Verwenden Sie die **/d** Switch Konstanten für bedingte Kompilierung, wie im folgenden Beispiel eingeben:</span><span class="sxs-lookup"><span data-stu-id="67ee6-132">-   Use the **/d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="67ee6-133">Kein Speicherplatz ist erforderlich, zwischen den **/d** Switch und das erste Konstante.</span><span class="sxs-lookup"><span data-stu-id="67ee6-133">No space is required between the **/d** switch and the first constant.</span></span> <span data-ttu-id="67ee6-134">Weitere Informationen finden Sie unter [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span><span class="sxs-lookup"><span data-stu-id="67ee6-134">For more information, see [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="67ee6-135">Befehlszeile-Deklarationen Überschreiben von Deklarationen, die in eingegebenen der **Projekt-Designer**, aber nicht gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="67ee6-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="67ee6-136">Legen Sie die Argumente in **Projekt-Designer** bleiben für nachfolgende Kompilierungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="67ee6-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="67ee6-137">Beim Konstanten im Code selbst schreiben möchten, stehen keine strengen Regeln bezüglich ihrer Platzierung, da deren Bereich das gesamte Modul ist in dem sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="67ee6-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="67ee6-138">Um Konstanten im Code festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="67ee6-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="67ee6-139">-Fügen Sie die Konstanten in der Deklarationsblock des Moduls, in dem sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="67ee6-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="67ee6-140">Dadurch bleibt Ihr Code organisiert und leichter zu lesen.</span><span class="sxs-lookup"><span data-stu-id="67ee6-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="67ee6-141">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="67ee6-141">Related Topics</span></span>  
  
|<span data-ttu-id="67ee6-142">Titel</span><span class="sxs-lookup"><span data-stu-id="67ee6-142">Title</span></span>|<span data-ttu-id="67ee6-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67ee6-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="67ee6-144">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="67ee6-144">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|<span data-ttu-id="67ee6-145">Enthält Vorschläge für Ihren Code leicht zu lesen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="67ee6-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="67ee6-146">Referenz</span><span class="sxs-lookup"><span data-stu-id="67ee6-146">Reference</span></span>  
 [<span data-ttu-id="67ee6-147">#Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="67ee6-147">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="67ee6-148">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="67ee6-148">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="67ee6-149">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67ee6-149">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
