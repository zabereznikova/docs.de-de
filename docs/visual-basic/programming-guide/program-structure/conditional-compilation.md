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
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="cbf0a-102">Bedingte Kompilierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cbf0a-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="cbf0a-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="cbf0a-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="cbf0a-105">Conditional compilation statements are designed to run during compile time, not at run time.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="cbf0a-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="cbf0a-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="cbf0a-108">The following example demonstrates how:</span><span class="sxs-lookup"><span data-stu-id="cbf0a-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 <span data-ttu-id="cbf0a-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="cbf0a-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="cbf0a-111">If neither is set to `True`, the code in the last `Else` block runs.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cbf0a-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="cbf0a-113">Declaring Conditional Compilation Constants</span><span class="sxs-lookup"><span data-stu-id="cbf0a-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="cbf0a-114">You can set conditional compilation constants in one of three ways:</span><span class="sxs-lookup"><span data-stu-id="cbf0a-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
- <span data-ttu-id="cbf0a-115">In the **Project Designer**</span><span class="sxs-lookup"><span data-stu-id="cbf0a-115">In the **Project Designer**</span></span>  
  
- <span data-ttu-id="cbf0a-116">At the command line when using the command-line compiler</span><span class="sxs-lookup"><span data-stu-id="cbf0a-116">At the command line when using the command-line compiler</span></span>  
  
- <span data-ttu-id="cbf0a-117">In your code</span><span class="sxs-lookup"><span data-stu-id="cbf0a-117">In your code</span></span>  
  
 <span data-ttu-id="cbf0a-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="cbf0a-119">The scope of a conditional compilation constant is dependent on the way it is set.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="cbf0a-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="cbf0a-121">How constant is set</span><span class="sxs-lookup"><span data-stu-id="cbf0a-121">How constant is set</span></span>|<span data-ttu-id="cbf0a-122">Scope of constant</span><span class="sxs-lookup"><span data-stu-id="cbf0a-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="cbf0a-123">**Project Designer**</span><span class="sxs-lookup"><span data-stu-id="cbf0a-123">**Project Designer**</span></span>|<span data-ttu-id="cbf0a-124">Public to all files in the project</span><span class="sxs-lookup"><span data-stu-id="cbf0a-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="cbf0a-125">Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="cbf0a-125">Command line</span></span>|<span data-ttu-id="cbf0a-126">Public to all files passed to the command-line compiler</span><span class="sxs-lookup"><span data-stu-id="cbf0a-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="cbf0a-127">`#Const` statement in code</span><span class="sxs-lookup"><span data-stu-id="cbf0a-127">`#Const` statement in code</span></span>|<span data-ttu-id="cbf0a-128">Private to the file in which it is declared</span><span class="sxs-lookup"><span data-stu-id="cbf0a-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="cbf0a-129">To set constants in the Project Designer</span><span class="sxs-lookup"><span data-stu-id="cbf0a-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="cbf0a-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span><span class="sxs-lookup"><span data-stu-id="cbf0a-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="cbf0a-131">To set constants at the command line</span><span class="sxs-lookup"><span data-stu-id="cbf0a-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="cbf0a-132">-   Use the **-d** switch to enter conditional compilation constants, as in the following example:</span><span class="sxs-lookup"><span data-stu-id="cbf0a-132">-   Use the **-d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="cbf0a-133">No space is required between the **-d** switch and the first constant.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-133">No space is required between the **-d** switch and the first constant.</span></span> <span data-ttu-id="cbf0a-134">For more information, see [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span><span class="sxs-lookup"><span data-stu-id="cbf0a-134">For more information, see [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="cbf0a-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="cbf0a-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="cbf0a-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="cbf0a-138">To set constants in your code</span><span class="sxs-lookup"><span data-stu-id="cbf0a-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="cbf0a-139">-   Place the constants in the declaration block of the module in which they are used.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="cbf0a-140">This helps keep your code organized and easier to read.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="cbf0a-141">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cbf0a-141">Related Topics</span></span>  
  
|<span data-ttu-id="cbf0a-142">Titel</span><span class="sxs-lookup"><span data-stu-id="cbf0a-142">Title</span></span>|<span data-ttu-id="cbf0a-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cbf0a-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="cbf0a-144">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="cbf0a-144">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|<span data-ttu-id="cbf0a-145">Provides suggestions for making your code easy to read and maintain.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="cbf0a-146">Referenz</span><span class="sxs-lookup"><span data-stu-id="cbf0a-146">Reference</span></span>  
 [<span data-ttu-id="cbf0a-147">#Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cbf0a-147">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="cbf0a-148">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="cbf0a-148">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="cbf0a-149">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbf0a-149">-define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
