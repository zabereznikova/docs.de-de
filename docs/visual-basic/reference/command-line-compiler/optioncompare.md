---
title: /optioncompare
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6f602e0b0b23345bf1f5aae843bd44bd2642bc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="optioncompare"></a><span data-ttu-id="e00ac-102">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="e00ac-102">/optioncompare</span></span>
<span data-ttu-id="e00ac-103">Gibt an, wie Zeichenfolgenvergleiche durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e00ac-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e00ac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e00ac-104">Syntax</span></span>  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="e00ac-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e00ac-105">Remarks</span></span>  
 <span data-ttu-id="e00ac-106">Können Sie angeben, `/optioncompare` in einer von zwei Formen: `/optioncompare:binary` binären Zeichenfolgenvergleichen verwendet und `/optioncompare:text` Textzeichenfolgenvergleiche verwendet.</span><span class="sxs-lookup"><span data-stu-id="e00ac-106">You can specify `/optioncompare` in one of two forms: `/optioncompare:binary` to use binary string comparisons, and `/optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="e00ac-107">Standardmäßig verwendet der Compiler `/optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="e00ac-107">By default, the compiler uses `/optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="e00ac-108">In Microsoft Windows bestimmt die Codepage, die verwendet wird, die binäre Sortierreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="e00ac-108">In Microsoft Windows, the code page being used determines the binary sort order.</span></span> <span data-ttu-id="e00ac-109">Eine typische binäre Sortierreihenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e00ac-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="e00ac-110">Textbasierte Zeichenfolgenvergleiche basieren auf einer schreibungsunabhängigen Textsortierreihenfolge, die durch das Gebietsschema des Systems bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e00ac-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="e00ac-111">Eine typische Textsortierreihenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e00ac-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="e00ac-112">/ Optioncompare in der Visual Studio-IDE festlegen</span><span class="sxs-lookup"><span data-stu-id="e00ac-112">To set /optioncompare in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="e00ac-113">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="e00ac-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e00ac-114">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e00ac-114">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="e00ac-115">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="e00ac-115">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="e00ac-116">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="e00ac-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="e00ac-117">Ändern Sie den Wert in der **Option Compare** Feld.</span><span class="sxs-lookup"><span data-stu-id="e00ac-117">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set-optioncompare-programmatically"></a><span data-ttu-id="e00ac-118">So legen Sie/optioncompare programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="e00ac-118">To set /optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="e00ac-119">Finden Sie unter [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e00ac-119">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e00ac-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e00ac-120">Example</span></span>  
 <span data-ttu-id="e00ac-121">Der folgende code kompiliert `ProjFile.vb` und binärer Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="e00ac-121">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e00ac-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e00ac-122">See Also</span></span>  
 [<span data-ttu-id="e00ac-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="e00ac-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e00ac-124">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="e00ac-124">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="e00ac-125">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="e00ac-125">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="e00ac-126">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="e00ac-126">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="e00ac-127">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="e00ac-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="e00ac-128">Option Compare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e00ac-128">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="e00ac-129">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="e00ac-129">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
