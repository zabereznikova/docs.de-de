---
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1906710ef10634187782f9355146dfa7ccb7748
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-optioncompare"></a><span data-ttu-id="b534f-102">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="b534f-102">-optioncompare</span></span>
<span data-ttu-id="b534f-103">Gibt an, wie Zeichenfolgenvergleiche durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b534f-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b534f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b534f-104">Syntax</span></span>  
  
```  
-optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="b534f-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b534f-105">Remarks</span></span>  
 <span data-ttu-id="b534f-106">Können Sie angeben, `-optioncompare` in einer von zwei Formen: `-optioncompare:binary` binären Zeichenfolgenvergleichen verwendet und `-optioncompare:text` Textzeichenfolgenvergleiche verwendet.</span><span class="sxs-lookup"><span data-stu-id="b534f-106">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="b534f-107">Standardmäßig verwendet der Compiler `-optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="b534f-107">By default, the compiler uses `-optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="b534f-108">In Microsoft Windows bestimmt die aktuellen Codepage die binäre Sortierreihenfolge an.</span><span class="sxs-lookup"><span data-stu-id="b534f-108">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="b534f-109">Eine typische binäre Sortierreihenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b534f-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="b534f-110">Textbasierte Zeichenfolgenvergleiche basieren auf einer schreibungsunabhängigen Textsortierreihenfolge, die durch das Gebietsschema des Systems bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b534f-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="b534f-111">Eine typische Textsortierreihenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b534f-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="b534f-112">-Optioncompare in der Visual Studio-IDE festlegen</span><span class="sxs-lookup"><span data-stu-id="b534f-112">To set -optioncompare in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="b534f-113">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="b534f-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b534f-114">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b534f-114">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="b534f-115">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="b534f-115">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="b534f-116">Ändern Sie den Wert in der **Option Compare** Feld.</span><span class="sxs-lookup"><span data-stu-id="b534f-116">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="b534f-117">So legen Sie - Optioncompare programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="b534f-117">To set -optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="b534f-118">Finden Sie unter [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b534f-118">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b534f-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b534f-119">Example</span></span>  
 <span data-ttu-id="b534f-120">Der folgende code kompiliert `ProjFile.vb` und binärer Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="b534f-120">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>  
  
```console
vbc -optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b534f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b534f-121">See Also</span></span>  
 [<span data-ttu-id="b534f-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="b534f-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b534f-123">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="b534f-123">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="b534f-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="b534f-124">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="b534f-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="b534f-125">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="b534f-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="b534f-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="b534f-127">Option Compare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b534f-127">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="b534f-128">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="b534f-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
