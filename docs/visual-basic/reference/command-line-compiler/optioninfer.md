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
ms.openlocfilehash: 524660fca7c56fa490cc85169898bf2bf6d1a16e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400577"
---
# <a name="-optioninfer"></a><span data-ttu-id="0fdc7-102">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="0fdc7-102">-optioninfer</span></span>
<span data-ttu-id="0fdc7-103">Ermöglicht die Verwendung von lokalem Typrückschluss in Variablendeklarationen.</span><span class="sxs-lookup"><span data-stu-id="0fdc7-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fdc7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0fdc7-104">Syntax</span></span>  
  
```console  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0fdc7-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0fdc7-105">Arguments</span></span>  
  
|<span data-ttu-id="0fdc7-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="0fdc7-106">Term</span></span>|<span data-ttu-id="0fdc7-107">Definition</span><span class="sxs-lookup"><span data-stu-id="0fdc7-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="0fdc7-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="0fdc7-108">`+` &#124; `-`</span></span>|<span data-ttu-id="0fdc7-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0fdc7-109">Optional.</span></span> <span data-ttu-id="0fdc7-110">Geben Sie `-optioninfer+` an, um lokalen Typrückschluss zu aktivieren oder `-optioninfer-` zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="0fdc7-110">Specify `-optioninfer+` to enable local type inference, or `-optioninfer-` to block it.</span></span> <span data-ttu-id="0fdc7-111">Die `-optioninfer` -Option ohne angegebenen Wert entspricht dem `-optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="0fdc7-111">The `-optioninfer` option, with no value specified, is the same as `-optioninfer+`.</span></span> <span data-ttu-id="0fdc7-112">Der Standardwert, wenn die `-optioninfer` Switch nicht vorhanden ist, ist auch `-optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="0fdc7-112">The default value when the `-optioninfer` switch is not present is also `-optioninfer+`.</span></span> <span data-ttu-id="0fdc7-113">Der Standardwert ist in der Vbc.rsp-Antwortdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0fdc7-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="0fdc7-114">Sie können die `-noconfig` Option nutzen, um die internen Standardwerte des Compilers, anstelle der Werte in vbc.rsp, beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="0fdc7-114">You can use the `-noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="0fdc7-115">Der Compilerstandardwert für diese Option ist `-optioninfer-`.</span><span class="sxs-lookup"><span data-stu-id="0fdc7-115">The compiler default for this option is `-optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fdc7-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0fdc7-116">Remarks</span></span>  
 <span data-ttu-id="0fdc7-117">Wenn die Quellcodedatei eine [Option Infer-Anweisung](../../language-reference/statements/option-infer-statement.md) enthält, überschreibt die Anweisung die Einstellung des `-optioninfer`-Befehlszeilencompilers.</span><span class="sxs-lookup"><span data-stu-id="0fdc7-117">If the source code file contains an [Option Infer Statement](../../language-reference/statements/option-infer-statement.md), the statement overrides the `-optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="0fdc7-118">Festlegen von -optioninfer in der Visual Studio-IDE</span><span class="sxs-lookup"><span data-stu-id="0fdc7-118">To set -optioninfer in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="0fdc7-119">Wählen Sie im **Projektmappen-Explorer** ein Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="0fdc7-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="0fdc7-120">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0fdc7-120">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="0fdc7-121">Ändern Sie auf der Registerkarte **Kompilieren** den Wert im Feld **Option infer**.</span><span class="sxs-lookup"><span data-stu-id="0fdc7-121">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fdc7-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0fdc7-122">Example</span></span>  
 <span data-ttu-id="0fdc7-123">Der folgende Code kompiliert `test.vb` mit aktiviertem lokalen Typrückschluss.</span><span class="sxs-lookup"><span data-stu-id="0fdc7-123">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0fdc7-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fdc7-124">See also</span></span>

- [<span data-ttu-id="0fdc7-125">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="0fdc7-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="0fdc7-126">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="0fdc7-126">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="0fdc7-127">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="0fdc7-127">-optionexplicit</span></span>](optionexplicit.md)
- [<span data-ttu-id="0fdc7-128">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="0fdc7-128">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="0fdc7-129">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="0fdc7-129">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="0fdc7-130">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0fdc7-130">Option Infer Statement</span></span>](../../language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="0fdc7-131">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="0fdc7-131">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="0fdc7-132">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="0fdc7-132">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="0fdc7-133">Seite „Kompilieren“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fdc7-133">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="0fdc7-134">-noconfig</span><span class="sxs-lookup"><span data-stu-id="0fdc7-134">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="0fdc7-135">Erstellen von der Befehlszeile aus</span><span class="sxs-lookup"><span data-stu-id="0fdc7-135">Building from the Command Line</span></span>](building-from-the-command-line.md)
