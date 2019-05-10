---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: 22423877325806e6e6abe535ad98530eb924780e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625905"
---
# <a name="-optionstrict"></a><span data-ttu-id="8fe29-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="8fe29-102">-optionstrict</span></span>
<span data-ttu-id="8fe29-103">Erzwingt strenge Typsemantik, um implizite typkonvertierungen zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="8fe29-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fe29-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8fe29-104">Syntax</span></span>  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8fe29-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="8fe29-105">Arguments</span></span>  
 <span data-ttu-id="8fe29-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="8fe29-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="8fe29-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="8fe29-107">Optional.</span></span> <span data-ttu-id="8fe29-108">Die `-optionstrict+` Option beschränkt die implizite typkonvertierung.</span><span class="sxs-lookup"><span data-stu-id="8fe29-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="8fe29-109">Der Standardwert für diese Option ist `-optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="8fe29-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="8fe29-110">Die `-optionstrict+` eignet identisch `-optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="8fe29-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="8fe29-111">Sie können sowohl für die freie Typsemantik verwenden.</span><span class="sxs-lookup"><span data-stu-id="8fe29-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="8fe29-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8fe29-112">Required.</span></span> <span data-ttu-id="8fe29-113">Warnen Sie, wenn die strenge Sprachsemantik nicht beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="8fe29-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fe29-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8fe29-114">Remarks</span></span>  
 <span data-ttu-id="8fe29-115">Wenn `-optionstrict+` gültig ist, können nur erweiternde Konvertierungen implizit vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="8fe29-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="8fe29-116">Implizite einschränkende typkonvertierungen, wie das Zuweisen einer `Decimal` Geben Sie mit einem Integer-Typ-Objekt, das als Fehler gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="8fe29-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="8fe29-117">Verwenden Sie zum Generieren von Warnungen für implizite einschränkende typkonvertierungen `-optionstrict:custom`.</span><span class="sxs-lookup"><span data-stu-id="8fe29-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="8fe29-118">Verwendung `-nowarn:numberlist` , um bestimmte Warnungen ignorieren und `-warnaserror:numberlist` bestimmte Warnungen als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="8fe29-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="8fe29-119">-Optionstrict in Visual Studio-IDE festlegen</span><span class="sxs-lookup"><span data-stu-id="8fe29-119">To set -optionstrict in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="8fe29-120">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="8fe29-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="8fe29-121">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften.**</span><span class="sxs-lookup"><span data-stu-id="8fe29-121">On the **Project** menu, click **Properties.**</span></span>   
  
2. <span data-ttu-id="8fe29-122">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="8fe29-122">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="8fe29-123">Ändern Sie den Wert in der **Option Strict** Feld.</span><span class="sxs-lookup"><span data-stu-id="8fe29-123">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="8fe29-124">-Optionstrict programmgesteuert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8fe29-124">To set -optionstrict programmatically</span></span>  
  
- <span data-ttu-id="8fe29-125">Finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8fe29-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fe29-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8fe29-126">Example</span></span>  
 <span data-ttu-id="8fe29-127">Der folgende code kompiliert `Test.vb` strikte Typsemantik zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8fe29-127">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8fe29-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fe29-128">See also</span></span>

- [<span data-ttu-id="8fe29-129">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="8fe29-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8fe29-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="8fe29-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="8fe29-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="8fe29-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="8fe29-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="8fe29-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="8fe29-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="8fe29-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="8fe29-134">-Warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fe29-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="8fe29-135">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="8fe29-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="8fe29-136">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8fe29-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="8fe29-137">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="8fe29-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
