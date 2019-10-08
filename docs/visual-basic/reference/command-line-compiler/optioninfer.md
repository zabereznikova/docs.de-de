---
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: c6fc7e9dcfbce938ad75b0f357c2bfa9cd10703a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005324"
---
# <a name="-optioninfer"></a><span data-ttu-id="5fe95-102">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="5fe95-102">-optioninfer</span></span>
<span data-ttu-id="5fe95-103">Ermöglicht die Verwendung von lokalem Typrückschluss in Variablendeklarationen.</span><span class="sxs-lookup"><span data-stu-id="5fe95-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fe95-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5fe95-104">Syntax</span></span>  
  
```console  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5fe95-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="5fe95-105">Arguments</span></span>  
  
|<span data-ttu-id="5fe95-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="5fe95-106">Term</span></span>|<span data-ttu-id="5fe95-107">Definition</span><span class="sxs-lookup"><span data-stu-id="5fe95-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="5fe95-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="5fe95-108">`+` &#124; `-`</span></span>|<span data-ttu-id="5fe95-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="5fe95-109">Optional.</span></span> <span data-ttu-id="5fe95-110">Geben Sie `-optioninfer+` an, um lokalen Typrückschluss zu aktivieren oder `-optioninfer-` zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="5fe95-110">Specify `-optioninfer+` to enable local type inference, or `-optioninfer-` to block it.</span></span> <span data-ttu-id="5fe95-111">Die `-optioninfer` -Option ohne angegebenen Wert entspricht dem `-optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="5fe95-111">The `-optioninfer` option, with no value specified, is the same as `-optioninfer+`.</span></span> <span data-ttu-id="5fe95-112">Der Standardwert, wenn die `-optioninfer` Switch nicht vorhanden ist, ist auch `-optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="5fe95-112">The default value when the `-optioninfer` switch is not present is also `-optioninfer+`.</span></span> <span data-ttu-id="5fe95-113">Der Standardwert ist in der Vbc.rsp-Antwortdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5fe95-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="5fe95-114">Sie können die `-noconfig` Option nutzen, um die internen Standardwerte des Compilers, anstelle der Werte in vbc.rsp, beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="5fe95-114">You can use the `-noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="5fe95-115">Der Compilerstandardwert für diese Option ist `-optioninfer-`.</span><span class="sxs-lookup"><span data-stu-id="5fe95-115">The compiler default for this option is `-optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fe95-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5fe95-116">Remarks</span></span>  
 <span data-ttu-id="5fe95-117">Wenn die Quell Code Datei eine [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md)enthält, überschreibt die-Anweisung die Befehlszeilen-Compilereinstellung `-optioninfer`.</span><span class="sxs-lookup"><span data-stu-id="5fe95-117">If the source code file contains an [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md), the statement overrides the `-optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="5fe95-118">So legen Sie-optioninfer in der Visual Studio-IDE fest</span><span class="sxs-lookup"><span data-stu-id="5fe95-118">To set -optioninfer in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="5fe95-119">Wählen Sie ein Projekt in **Projektmappen-Explorer**aus.</span><span class="sxs-lookup"><span data-stu-id="5fe95-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="5fe95-120">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5fe95-120">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="5fe95-121">Ändern Sie auf der Registerkarte **Kompilieren** den Wert im Feld **Option ableiten** .</span><span class="sxs-lookup"><span data-stu-id="5fe95-121">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fe95-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5fe95-122">Example</span></span>  
 <span data-ttu-id="5fe95-123">Der folgende Code kompiliert `test.vb` mit aktiviertem lokalen Typrückschluss.</span><span class="sxs-lookup"><span data-stu-id="5fe95-123">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="5fe95-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fe95-124">See also</span></span>

- [<span data-ttu-id="5fe95-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="5fe95-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5fe95-126">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="5fe95-126">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="5fe95-127">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="5fe95-127">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="5fe95-128">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="5fe95-128">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="5fe95-129">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="5fe95-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="5fe95-130">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5fe95-130">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="5fe95-131">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="5fe95-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="5fe95-132">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="5fe95-132">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="5fe95-133">Seite „Kompilieren“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5fe95-133">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="5fe95-134">/noconfig</span><span class="sxs-lookup"><span data-stu-id="5fe95-134">/noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="5fe95-135">Erstellen von der Befehlszeile aus</span><span class="sxs-lookup"><span data-stu-id="5fe95-135">Building from the Command Line</span></span>](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
