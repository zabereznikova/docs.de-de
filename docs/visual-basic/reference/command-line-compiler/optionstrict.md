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
ms.openlocfilehash: 6d281fe07754f0471f8d6c0e31cf3ea890060504
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005347"
---
# <a name="-optionstrict"></a><span data-ttu-id="2ca39-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="2ca39-102">-optionstrict</span></span>
<span data-ttu-id="2ca39-103">Erzwingt eine strikte Typsemantik, um implizite Typkonvertierungen einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="2ca39-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ca39-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ca39-104">Syntax</span></span>  
  
```console  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2ca39-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="2ca39-105">Arguments</span></span>  
 <span data-ttu-id="2ca39-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2ca39-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="2ca39-107">Optional.</span><span class="sxs-lookup"><span data-stu-id="2ca39-107">Optional.</span></span> <span data-ttu-id="2ca39-108">Die Option "`-optionstrict+`" schränkt die implizite Typkonvertierung ein.</span><span class="sxs-lookup"><span data-stu-id="2ca39-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="2ca39-109">Der Standardwert für diese Option ist `-optionstrict-`.</span><span class="sxs-lookup"><span data-stu-id="2ca39-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="2ca39-110">Die Option "`-optionstrict+`" entspricht `-optionstrict`.</span><span class="sxs-lookup"><span data-stu-id="2ca39-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="2ca39-111">Sie können beide für die semantische Typsemantik verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ca39-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="2ca39-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2ca39-112">Required.</span></span> <span data-ttu-id="2ca39-113">Warnen, wenn die strenge sprach Semantik nicht beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="2ca39-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ca39-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ca39-114">Remarks</span></span>  
 <span data-ttu-id="2ca39-115">Wenn `-optionstrict+` wirksam ist, können nur erweiternde Typkonvertierungen implizit vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="2ca39-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="2ca39-116">Implizite einschränkende Typkonvertierungen, wie z. b. das Zuweisen eines `Decimal`-Typobjekts zu einem ganzzahligen Typobjekt, werden als Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2ca39-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="2ca39-117">Verwenden Sie `-optionstrict:custom`, um Warnungen für implizite einschränkende Typkonvertierungen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="2ca39-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="2ca39-118">Verwenden Sie `-nowarn:numberlist`, um bestimmte Warnungen zu ignorieren, und `-warnaserror:numberlist`, um bestimmte Warnungen als Fehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="2ca39-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="2ca39-119">So legen Sie-optionstrict in der Visual Studio-IDE fest</span><span class="sxs-lookup"><span data-stu-id="2ca39-119">To set -optionstrict in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="2ca39-120">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="2ca39-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2ca39-121">Klicken Sie im Menü **Projekt** auf **Eigenschaften.**</span><span class="sxs-lookup"><span data-stu-id="2ca39-121">On the **Project** menu, click **Properties.**</span></span>   
  
2. <span data-ttu-id="2ca39-122">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="2ca39-122">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="2ca39-123">Ändern Sie den Wert im Feld **Option Strict** .</span><span class="sxs-lookup"><span data-stu-id="2ca39-123">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="2ca39-124">So legen Sie-optionstrict Programm gesteuert fest</span><span class="sxs-lookup"><span data-stu-id="2ca39-124">To set -optionstrict programmatically</span></span>  
  
- <span data-ttu-id="2ca39-125">Siehe [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2ca39-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ca39-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ca39-126">Example</span></span>  
 <span data-ttu-id="2ca39-127">Der folgende Code kompiliert `Test.vb` mithilfe der strengen Typsemantik.</span><span class="sxs-lookup"><span data-stu-id="2ca39-127">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ca39-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ca39-128">See also</span></span>

- [<span data-ttu-id="2ca39-129">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="2ca39-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2ca39-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="2ca39-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="2ca39-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="2ca39-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="2ca39-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="2ca39-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="2ca39-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="2ca39-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="2ca39-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ca39-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="2ca39-135">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="2ca39-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="2ca39-136">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2ca39-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="2ca39-137">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="2ca39-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
