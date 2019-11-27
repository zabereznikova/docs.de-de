---
title: Bedingte Kompilierung
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 19a2c70941a9a72574f7e624743def74b80c4e39
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347461"
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="52bbf-102">Bedingte Kompilierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="52bbf-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="52bbf-103">Bei der *bedingten Kompilierung*werden bestimmte Code Blöcke in einem Programm selektiv kompiliert, während andere ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="52bbf-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="52bbf-104">Beispielsweise können Sie Debuganweisungen schreiben, die die Geschwindigkeit verschiedener Ansätze mit derselben Programmieraufgabe vergleichen, oder Sie möchten eine Anwendung für mehrere Sprachen lokalisieren.</span><span class="sxs-lookup"><span data-stu-id="52bbf-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="52bbf-105">Bedingte Kompilierungs Anweisungen sind so konzipiert, dass Sie zur Kompilierzeit und nicht zur Laufzeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="52bbf-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="52bbf-106">Code Blöcke, die mit der `#If...Then...#Else`-Direktive bedingt kompiliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="52bbf-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="52bbf-107">Wenn Sie z. b. Französisch-und deutschsprachige Versionen derselben Anwendung aus demselben Quellcode erstellen möchten, Betten Sie plattformspezifische Code Segmente in `#If...Then` Anweisungen ein, indem Sie die vordefinierten Konstanten `FrenchVersion` und `GermanVersion`.</span><span class="sxs-lookup"><span data-stu-id="52bbf-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="52bbf-108">Im folgenden Beispiel wird veranschaulicht, wie:</span><span class="sxs-lookup"><span data-stu-id="52bbf-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 <span data-ttu-id="52bbf-109">Wenn Sie den Wert der `FrenchVersion` bedingte Kompilierungs Konstante zum Zeitpunkt der Kompilierung auf `True` festlegen, wird der bedingte Code für die französische Version kompiliert.</span><span class="sxs-lookup"><span data-stu-id="52bbf-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="52bbf-110">Wenn Sie den Wert der `GermanVersion` Konstante auf `True`festlegen, verwendet der Compiler die deutsche Version.</span><span class="sxs-lookup"><span data-stu-id="52bbf-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="52bbf-111">Wenn keines der beiden `True`festgelegt ist, wird der Code im letzten `Else`-Block ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="52bbf-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52bbf-112">Die automatische Vervollständigung funktioniert nicht, wenn Code bearbeitet und bedingte Kompilierungs Direktiven verwendet werden, wenn der Code nicht Teil der aktuellen Verzweigung ist.</span><span class="sxs-lookup"><span data-stu-id="52bbf-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="52bbf-113">Deklarieren bedingter Kompilierungs Konstanten</span><span class="sxs-lookup"><span data-stu-id="52bbf-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="52bbf-114">Sie können auf eine von drei Arten bedingte Kompilierungs Konstanten festlegen:</span><span class="sxs-lookup"><span data-stu-id="52bbf-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
- <span data-ttu-id="52bbf-115">Im **Projekt-Designer**</span><span class="sxs-lookup"><span data-stu-id="52bbf-115">In the **Project Designer**</span></span>  
  
- <span data-ttu-id="52bbf-116">Bei Verwendung des Befehlszeilen Compilers an der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="52bbf-116">At the command line when using the command-line compiler</span></span>  
  
- <span data-ttu-id="52bbf-117">In Ihrem Code</span><span class="sxs-lookup"><span data-stu-id="52bbf-117">In your code</span></span>  
  
 <span data-ttu-id="52bbf-118">Die Konstanten für die bedingte Kompilierung haben einen speziellen Bereich und können nicht über Standard Code aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="52bbf-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="52bbf-119">Der Gültigkeitsbereich einer Konstanten für die bedingte Kompilierung hängt davon ab, wie er festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="52bbf-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="52bbf-120">In der folgenden Tabelle wird der Gültigkeitsbereich der Konstanten aufgelistet, die mit den drei oben erwähnten Methoden deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="52bbf-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="52bbf-121">Festlegen der Konstante</span><span class="sxs-lookup"><span data-stu-id="52bbf-121">How constant is set</span></span>|<span data-ttu-id="52bbf-122">Gültigkeitsbereich der Konstante</span><span class="sxs-lookup"><span data-stu-id="52bbf-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="52bbf-123">**Projekt-Designer**</span><span class="sxs-lookup"><span data-stu-id="52bbf-123">**Project Designer**</span></span>|<span data-ttu-id="52bbf-124">Öffentlich für alle Dateien im Projekt</span><span class="sxs-lookup"><span data-stu-id="52bbf-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="52bbf-125">Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="52bbf-125">Command line</span></span>|<span data-ttu-id="52bbf-126">Öffentlich für alle Dateien, die an den Befehlszeilen Compiler übermittelt werden</span><span class="sxs-lookup"><span data-stu-id="52bbf-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="52bbf-127">`#Const`-Anweisung im Code</span><span class="sxs-lookup"><span data-stu-id="52bbf-127">`#Const` statement in code</span></span>|<span data-ttu-id="52bbf-128">Privat für die Datei, in der Sie deklariert ist</span><span class="sxs-lookup"><span data-stu-id="52bbf-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="52bbf-129">So legen Sie Konstanten im Projekt-Designer fest</span><span class="sxs-lookup"><span data-stu-id="52bbf-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="52bbf-130">-Legen Sie vor dem Erstellen der ausführbaren Datei Konstanten im **Projekt-Designer** fest, indem Sie die Schritte unter Verwalten von [Projekt-und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)befolgen.</span><span class="sxs-lookup"><span data-stu-id="52bbf-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="52bbf-131">So legen Sie Konstanten in der Befehlszeile fest</span><span class="sxs-lookup"><span data-stu-id="52bbf-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="52bbf-132">-Verwenden Sie den Schalter **-d** , um die Konstanten für die bedingte Kompilierung einzugeben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="52bbf-132">-   Use the **-d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="52bbf-133">Zwischen dem Schalter " **-d** " und der ersten Konstante ist kein Leerzeichen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="52bbf-133">No space is required between the **-d** switch and the first constant.</span></span> <span data-ttu-id="52bbf-134">Weitere Informationen finden Sie unter [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span><span class="sxs-lookup"><span data-stu-id="52bbf-134">For more information, see [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="52bbf-135">Befehlszeilen Deklarationen überschreiben Deklarationen, die im **Projekt-Designer**eingegeben wurden, löschen Sie aber nicht.</span><span class="sxs-lookup"><span data-stu-id="52bbf-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="52bbf-136">Die im **Projekt-Designer** festgelegten Argumente bleiben für nachfolgende Kompilierungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="52bbf-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="52bbf-137">Beim Schreiben von Konstanten im Code selbst gibt es keine strengen Regeln für die Platzierung, da der Gültigkeitsbereich das gesamte Modul ist, in dem Sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="52bbf-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="52bbf-138">So legen Sie Konstanten im Code fest</span><span class="sxs-lookup"><span data-stu-id="52bbf-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="52bbf-139">-Platzieren Sie die Konstanten im Deklarations Block des Moduls, in dem Sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52bbf-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="52bbf-140">Dadurch wird der Code organisiert und leichter lesbar.</span><span class="sxs-lookup"><span data-stu-id="52bbf-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="52bbf-141">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="52bbf-141">Related Topics</span></span>  
  
|<span data-ttu-id="52bbf-142">Titel</span><span class="sxs-lookup"><span data-stu-id="52bbf-142">Title</span></span>|<span data-ttu-id="52bbf-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52bbf-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="52bbf-144">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="52bbf-144">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|<span data-ttu-id="52bbf-145">Bietet Vorschläge, wie Sie Ihren Code auf einfache Weise lesen und warten können.</span><span class="sxs-lookup"><span data-stu-id="52bbf-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="52bbf-146">Verweis</span><span class="sxs-lookup"><span data-stu-id="52bbf-146">Reference</span></span>  
 [<span data-ttu-id="52bbf-147">#Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="52bbf-147">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="52bbf-148">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="52bbf-148">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="52bbf-149">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52bbf-149">-define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
