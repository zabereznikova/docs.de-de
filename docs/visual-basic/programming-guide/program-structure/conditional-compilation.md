---
title: Bedingte Kompilierung
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: c3eb1eb57b3d76e762ed53edb3b168ad96abec39
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403264"
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="29963-102">Bedingte Kompilierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="29963-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="29963-103">Bei der *bedingten Kompilierung*werden bestimmte Code Blöcke in einem Programm selektiv kompiliert, während andere ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="29963-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="29963-104">Beispielsweise können Sie Debuganweisungen schreiben, die die Geschwindigkeit verschiedener Ansätze mit derselben Programmieraufgabe vergleichen, oder Sie möchten eine Anwendung für mehrere Sprachen lokalisieren.</span><span class="sxs-lookup"><span data-stu-id="29963-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="29963-105">Bedingte Kompilierungs Anweisungen sind so konzipiert, dass Sie zur Kompilierzeit und nicht zur Laufzeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="29963-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="29963-106">Code Blöcke, die mit der-Direktive bedingt kompiliert werden sollen `#If...Then...#Else` .</span><span class="sxs-lookup"><span data-stu-id="29963-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="29963-107">Wenn Sie z. b. Französisch-und deutschsprachige Versionen derselben Anwendung aus demselben Quellcode erstellen möchten, Betten Sie plattformspezifische Code Segmente in `#If...Then` -Anweisungen ein, die die vordefinierten Konstanten `FrenchVersion` und verwenden `GermanVersion` .</span><span class="sxs-lookup"><span data-stu-id="29963-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="29963-108">Im folgenden Beispiel wird veranschaulicht, wie:</span><span class="sxs-lookup"><span data-stu-id="29963-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 <span data-ttu-id="29963-109">Wenn Sie den Wert der `FrenchVersion` bedingten Kompilierungs Konstante zur `True` Kompilierzeit auf festlegen, wird der bedingte Code für die französische Version kompiliert.</span><span class="sxs-lookup"><span data-stu-id="29963-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="29963-110">Wenn Sie den Wert der `GermanVersion` Konstante auf festlegen `True` , verwendet der Compiler die deutsche Version.</span><span class="sxs-lookup"><span data-stu-id="29963-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="29963-111">Wenn keines von auf festgelegt ist `True` , wird der Code im letzten- `Else` Block ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="29963-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29963-112">Die automatische Vervollständigung funktioniert nicht, wenn Code bearbeitet und bedingte Kompilierungs Direktiven verwendet werden, wenn der Code nicht Teil der aktuellen Verzweigung ist.</span><span class="sxs-lookup"><span data-stu-id="29963-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="29963-113">Deklarieren bedingter Kompilierungs Konstanten</span><span class="sxs-lookup"><span data-stu-id="29963-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="29963-114">Sie können auf eine von drei Arten bedingte Kompilierungs Konstanten festlegen:</span><span class="sxs-lookup"><span data-stu-id="29963-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
- <span data-ttu-id="29963-115">Im **Projekt-Designer**</span><span class="sxs-lookup"><span data-stu-id="29963-115">In the **Project Designer**</span></span>  
  
- <span data-ttu-id="29963-116">Bei Verwendung des Befehlszeilen Compilers an der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="29963-116">At the command line when using the command-line compiler</span></span>  
  
- <span data-ttu-id="29963-117">In Ihrem Code</span><span class="sxs-lookup"><span data-stu-id="29963-117">In your code</span></span>  
  
 <span data-ttu-id="29963-118">Die Konstanten für die bedingte Kompilierung haben einen speziellen Bereich und können nicht über Standard Code aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="29963-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="29963-119">Der Gültigkeitsbereich einer Konstanten für die bedingte Kompilierung hängt davon ab, wie er festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="29963-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="29963-120">In der folgenden Tabelle wird der Gültigkeitsbereich der Konstanten aufgelistet, die mit den drei oben erwähnten Methoden deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="29963-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="29963-121">Festlegen der Konstante</span><span class="sxs-lookup"><span data-stu-id="29963-121">How constant is set</span></span>|<span data-ttu-id="29963-122">Gültigkeitsbereich der Konstante</span><span class="sxs-lookup"><span data-stu-id="29963-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="29963-123">**Projekt-Designer**</span><span class="sxs-lookup"><span data-stu-id="29963-123">**Project Designer**</span></span>|<span data-ttu-id="29963-124">Öffentlich für alle Dateien im Projekt</span><span class="sxs-lookup"><span data-stu-id="29963-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="29963-125">Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="29963-125">Command line</span></span>|<span data-ttu-id="29963-126">Öffentlich für alle Dateien, die an den Befehlszeilen Compiler übermittelt werden</span><span class="sxs-lookup"><span data-stu-id="29963-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="29963-127">`#Const`Anweisung im Code</span><span class="sxs-lookup"><span data-stu-id="29963-127">`#Const` statement in code</span></span>|<span data-ttu-id="29963-128">Privat für die Datei, in der Sie deklariert ist</span><span class="sxs-lookup"><span data-stu-id="29963-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="29963-129">So legen Sie Konstanten im Projekt-Designer fest</span><span class="sxs-lookup"><span data-stu-id="29963-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="29963-130">-Legen Sie vor dem Erstellen der ausführbaren Datei Konstanten im **Projekt-Designer** fest, indem Sie die Schritte unter Verwalten von [Projekt-und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)befolgen.</span><span class="sxs-lookup"><span data-stu-id="29963-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="29963-131">So legen Sie Konstanten in der Befehlszeile fest</span><span class="sxs-lookup"><span data-stu-id="29963-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="29963-132">-Verwenden Sie den Schalter **-d** , um die Konstanten für die bedingte Kompilierung einzugeben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="29963-132">-   Use the **-d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="29963-133">Zwischen dem Schalter " **-d** " und der ersten Konstante ist kein Leerzeichen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="29963-133">No space is required between the **-d** switch and the first constant.</span></span> <span data-ttu-id="29963-134">Weitere Informationen finden Sie unter [-define (Visual Basic)](../../reference/command-line-compiler/define.md).</span><span class="sxs-lookup"><span data-stu-id="29963-134">For more information, see [-define (Visual Basic)](../../reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="29963-135">Befehlszeilen Deklarationen überschreiben Deklarationen, die im **Projekt-Designer**eingegeben wurden, löschen Sie aber nicht.</span><span class="sxs-lookup"><span data-stu-id="29963-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="29963-136">Die im **Projekt-Designer** festgelegten Argumente bleiben für nachfolgende Kompilierungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="29963-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="29963-137">Beim Schreiben von Konstanten im Code selbst gibt es keine strengen Regeln für die Platzierung, da der Gültigkeitsbereich das gesamte Modul ist, in dem Sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="29963-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="29963-138">So legen Sie Konstanten im Code fest</span><span class="sxs-lookup"><span data-stu-id="29963-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="29963-139">-Platzieren Sie die Konstanten im Deklarations Block des Moduls, in dem Sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="29963-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="29963-140">Dadurch wird der Code organisiert und leichter lesbar.</span><span class="sxs-lookup"><span data-stu-id="29963-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="29963-141">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="29963-141">Related Topics</span></span>  
  
|<span data-ttu-id="29963-142">Titel</span><span class="sxs-lookup"><span data-stu-id="29963-142">Title</span></span>|<span data-ttu-id="29963-143">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="29963-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="29963-144">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="29963-144">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)|<span data-ttu-id="29963-145">Bietet Vorschläge, wie Sie Ihren Code auf einfache Weise lesen und warten können.</span><span class="sxs-lookup"><span data-stu-id="29963-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="29963-146">Verweis</span><span class="sxs-lookup"><span data-stu-id="29963-146">Reference</span></span>  
 [<span data-ttu-id="29963-147">#Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="29963-147">#Const Directive</span></span>](../../language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="29963-148">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="29963-148">#If...Then...#Else Directives</span></span>](../../language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="29963-149">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29963-149">-define (Visual Basic)</span></span>](../../reference/command-line-compiler/define.md)
