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
ms.openlocfilehash: 65cc3fb1b2fa9daa04013caa2b93a3949d0a15b9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098935"
---
# <a name="-optionexplicit"></a><span data-ttu-id="c7d72-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="c7d72-102">-optionexplicit</span></span>

<span data-ttu-id="c7d72-103">Führt dazu, dass der Compiler Fehler meldet, wenn Variablen nicht deklariert werden, bevor sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7d72-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7d72-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7d72-104">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c7d72-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="c7d72-105">Arguments</span></span>  

 <span data-ttu-id="c7d72-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c7d72-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="c7d72-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c7d72-107">Optional.</span></span> <span data-ttu-id="c7d72-108">Geben Sie `-optionexplicit+` an, um die explizite Variablendeklaration erforderlich zu machen.</span><span class="sxs-lookup"><span data-stu-id="c7d72-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="c7d72-109">Die `-optionexplicit+`-Option ist der Standardwert und ist identisch mit `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="c7d72-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="c7d72-110">Die `-optionexplicit-`-Option ermöglicht die implizite Deklaration von Variablen.</span><span class="sxs-lookup"><span data-stu-id="c7d72-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7d72-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7d72-111">Remarks</span></span>  

 <span data-ttu-id="c7d72-112">Wenn die Quellcodedatei eine [Option Explicit-Anweisung](../../language-reference/statements/option-explicit-statement.md) enthält, überschreibt die Anweisung die Einstellung des `-optionexplicit`-Befehlszeilencompilers.</span><span class="sxs-lookup"><span data-stu-id="c7d72-112">If the source code file contains an [Option Explicit statement](../../language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="c7d72-113">So legen Sie -optionexplicit in der integrierten Entwicklungsumgebung in Visual Studio fest</span><span class="sxs-lookup"><span data-stu-id="c7d72-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="c7d72-114">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="c7d72-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c7d72-115">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c7d72-115">On the **Project** menu, click **Properties**.</span></span>
  
2. <span data-ttu-id="c7d72-116">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="c7d72-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="c7d72-117">Ändern Sie den Wert im Feld **Option Explicit** entsprechend.</span><span class="sxs-lookup"><span data-stu-id="c7d72-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7d72-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7d72-118">Example</span></span>  

 <span data-ttu-id="c7d72-119">Der folgende Code wird kompiliert, wenn `-optionexplicit-` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7d72-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="c7d72-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7d72-120">See also</span></span>

- [<span data-ttu-id="c7d72-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="c7d72-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="c7d72-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="c7d72-122">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="c7d72-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="c7d72-123">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="c7d72-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="c7d72-124">-optioninfer</span></span>](optioninfer.md)
- [<span data-ttu-id="c7d72-125">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="c7d72-125">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="c7d72-126">Option Explicit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c7d72-126">Option Explicit Statement</span></span>](../../language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="c7d72-127">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="c7d72-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
