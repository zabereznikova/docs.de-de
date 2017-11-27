---
title: /optionexplicit
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1cfdb94ebafa7d6a14253aeb59ab98b3a953fe4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="optionexplicit"></a><span data-ttu-id="312da-102">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="312da-102">/optionexplicit</span></span>
<span data-ttu-id="312da-103">Bewirkt, dass der Compiler gemeldet, wenn keine Variablen deklariert werden, bevor sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="312da-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="312da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="312da-104">Syntax</span></span>  
  
```  
/optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="312da-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="312da-105">Arguments</span></span>  
 <span data-ttu-id="312da-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="312da-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="312da-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="312da-107">Optional.</span></span> <span data-ttu-id="312da-108">Geben Sie `/optionexplicit+` explizite Deklaration von Variablen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="312da-108">Specify `/optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="312da-109">Die `/optionexplicit+` Option ist die Standardeinstellung und entspricht dem `/optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="312da-109">The `/optionexplicit+` option is the default and is the same as `/optionexplicit`.</span></span> <span data-ttu-id="312da-110">Die `/optionexplicit-` Option ermöglicht die implizite Deklaration von Variablen.</span><span class="sxs-lookup"><span data-stu-id="312da-110">The `/optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="312da-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="312da-111">Remarks</span></span>  
 <span data-ttu-id="312da-112">Wenn die Quellcodedatei enthält eine [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md), überschreibt die Anweisung die `/optionexplicit` Befehlszeilencompiler-Einstellung.</span><span class="sxs-lookup"><span data-stu-id="312da-112">If the source code file contains an [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `/optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set-optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="312da-113">/ Optionexplicit in der Visual Studio-IDE festlegen</span><span class="sxs-lookup"><span data-stu-id="312da-113">To set /optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="312da-114">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="312da-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="312da-115">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="312da-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="312da-116">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="312da-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="312da-117">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="312da-117">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="312da-118">Ändern Sie den Wert in der **Option Explicit** Feld.</span><span class="sxs-lookup"><span data-stu-id="312da-118">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="312da-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="312da-119">Example</span></span>  
 <span data-ttu-id="312da-120">Im folgende Code wird kompiliert, wenn `/optionexplicit-` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="312da-120">The following code compiles when `/optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="312da-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="312da-121">See Also</span></span>  
 [<span data-ttu-id="312da-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="312da-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="312da-123">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="312da-123">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="312da-124">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="312da-124">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="312da-125">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="312da-125">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="312da-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="312da-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="312da-127">Option Explicit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="312da-127">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="312da-128">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="312da-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
