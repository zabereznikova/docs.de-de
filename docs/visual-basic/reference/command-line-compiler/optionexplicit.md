---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 5c0946b94bfe02d797d1a484088869375703eb6a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005307"
---
# <a name="-optionexplicit"></a><span data-ttu-id="d2dc8-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="d2dc8-102">-optionexplicit</span></span>
<span data-ttu-id="d2dc8-103">Bewirkt, dass der Compiler Fehler meldet, wenn keine Variablen deklariert sind, bevor Sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d2dc8-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2dc8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2dc8-104">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d2dc8-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d2dc8-105">Arguments</span></span>  
 <span data-ttu-id="d2dc8-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d2dc8-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="d2dc8-107">Optional.</span><span class="sxs-lookup"><span data-stu-id="d2dc8-107">Optional.</span></span> <span data-ttu-id="d2dc8-108">Geben Sie `-optionexplicit+` an, um eine explizite Deklaration von Variablen anzufordern.</span><span class="sxs-lookup"><span data-stu-id="d2dc8-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="d2dc8-109">Die Option "`-optionexplicit+`" ist die Standardeinstellung und entspricht `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="d2dc8-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="d2dc8-110">Die Option `-optionexplicit-` aktiviert die implizite Deklaration von Variablen.</span><span class="sxs-lookup"><span data-stu-id="d2dc8-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2dc8-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2dc8-111">Remarks</span></span>  
 <span data-ttu-id="d2dc8-112">Wenn die Quell Code Datei eine [explizite Option-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md)enthält, überschreibt die-Anweisung die Befehlszeilen-Compilereinstellung `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="d2dc8-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="d2dc8-113">So legen Sie-optionexpliziten in der Visual Studio-IDE fest</span><span class="sxs-lookup"><span data-stu-id="d2dc8-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="d2dc8-114">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="d2dc8-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d2dc8-115">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d2dc8-115">On the **Project** menu, click **Properties**.</span></span>   
  
2. <span data-ttu-id="d2dc8-116">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="d2dc8-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="d2dc8-117">Ändern Sie den Wert im Feld **Option explizit** .</span><span class="sxs-lookup"><span data-stu-id="d2dc8-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2dc8-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d2dc8-118">Example</span></span>  
 <span data-ttu-id="d2dc8-119">Der folgende Code wird kompiliert, wenn `-optionexplicit-` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d2dc8-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="d2dc8-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2dc8-120">See also</span></span>

- [<span data-ttu-id="d2dc8-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="d2dc8-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d2dc8-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="d2dc8-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="d2dc8-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="d2dc8-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="d2dc8-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="d2dc8-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="d2dc8-125">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="d2dc8-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="d2dc8-126">Option Explicit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d2dc8-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="d2dc8-127">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="d2dc8-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
