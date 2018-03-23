---
title: -optionstrict
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2ff7d13fcb3e224ee76cdb42f3974a4eddb042f5
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-optionstrict"></a><span data-ttu-id="d7e5f-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="d7e5f-102">-optionstrict</span></span>
<span data-ttu-id="d7e5f-103">Erzwingt strenge Typsemantik um implizite typkonvertierungen zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7e5f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7e5f-104">Syntax</span></span>  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d7e5f-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d7e5f-105">Arguments</span></span>  
 <span data-ttu-id="d7e5f-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d7e5f-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="d7e5f-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-107">Optional.</span></span> <span data-ttu-id="d7e5f-108">Die `-optionstrict+` Option beschränkt die implizite typkonvertierung.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="d7e5f-109">Der Standardwert für diese Option ist `-optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="d7e5f-110">Die `-optionstrict+` Option entspricht dem `-optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="d7e5f-111">Sie können sowohl für freie Typsemantik verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="d7e5f-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-112">Required.</span></span> <span data-ttu-id="d7e5f-113">Warnhinweis anzeigen Sie, wenn die strenge Sprachsemantik nicht beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7e5f-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7e5f-114">Remarks</span></span>  
 <span data-ttu-id="d7e5f-115">Wenn `-optionstrict+` ist aktiviert, können nur erweiternde Konvertierungen implizit vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="d7e5f-116">Implizite einschränkende typkonvertierungen, z. B. das Zuweisen einer `Decimal` Geben Sie mit einem Integer-Typ-Objekt, das als Fehler gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="d7e5f-117">Verwenden Sie zum Generieren von Warnungen für implizite einschränkende typkonvertierungen `-optionstrict:custom`.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="d7e5f-118">Verwendung `-nowarn:numberlist` , um bestimmte Warnungen ignorieren und `-warnaserror:numberlist` auf bestimmte Warnungen als Fehler behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="d7e5f-119">-Optionstrict in der Visual Studio-IDE festlegen</span><span class="sxs-lookup"><span data-stu-id="d7e5f-119">To set -optionstrict in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="d7e5f-120">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d7e5f-121">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften.**</span><span class="sxs-lookup"><span data-stu-id="d7e5f-121">On the **Project** menu, click **Properties.**</span></span>   
  
2.  <span data-ttu-id="d7e5f-122">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-122">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="d7e5f-123">Ändern Sie den Wert in der **Option Strict** Feld.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-123">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="d7e5f-124">So legen Sie - Optionstrict programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="d7e5f-124">To set -optionstrict programmatically</span></span>  
  
-   <span data-ttu-id="d7e5f-125">Finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d7e5f-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7e5f-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7e5f-126">Example</span></span>  
 <span data-ttu-id="d7e5f-127">Der folgende code kompiliert `Test.vb` strikte Typsemantik zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7e5f-127">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7e5f-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7e5f-128">See Also</span></span>  
 [<span data-ttu-id="d7e5f-129">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="d7e5f-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d7e5f-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="d7e5f-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="d7e5f-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="d7e5f-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="d7e5f-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="d7e5f-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="d7e5f-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="d7e5f-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)  
 [<span data-ttu-id="d7e5f-134">-Warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7e5f-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)  
 [<span data-ttu-id="d7e5f-135">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="d7e5f-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="d7e5f-136">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d7e5f-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="d7e5f-137">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="d7e5f-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
