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
ms.openlocfilehash: 86564b7ce419ef6c6e56a6b677b71009830b5fc4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662308"
---
# <a name="-optioncompare"></a><span data-ttu-id="18ccd-102">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="18ccd-102">-optioncompare</span></span>
<span data-ttu-id="18ccd-103">Gibt an, wie Zeichenfolgenvergleiche durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="18ccd-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18ccd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="18ccd-104">Syntax</span></span>  
  
```  
-optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="18ccd-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="18ccd-105">Remarks</span></span>  
 <span data-ttu-id="18ccd-106">Sie können angeben, `-optioncompare` in einem von zwei Formen: `-optioncompare:binary` binäre Zeichenfolgenvergleiche verwendet und `-optioncompare:text` Textzeichenfolgenvergleiche verwendet.</span><span class="sxs-lookup"><span data-stu-id="18ccd-106">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="18ccd-107">Standardmäßig verwendet der Compiler `-optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="18ccd-107">By default, the compiler uses `-optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="18ccd-108">In Microsoft Windows bestimmt die aktuellen Codepage die binäre Sortierreihenfolge an.</span><span class="sxs-lookup"><span data-stu-id="18ccd-108">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="18ccd-109">Eine typische binäre Sortierreihenfolge lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="18ccd-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="18ccd-110">Vergleiche des String textbasierte basieren auf einer schreibungsunabhängigen Textsortierreihenfolge, die durch das Gebietsschema des Systems bestimmt.</span><span class="sxs-lookup"><span data-stu-id="18ccd-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="18ccd-111">Eine typische Textsortierreihenfolge lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="18ccd-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="18ccd-112">-Optioncompare in Visual Studio-IDE festlegen</span><span class="sxs-lookup"><span data-stu-id="18ccd-112">To set -optioncompare in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="18ccd-113">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="18ccd-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="18ccd-114">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="18ccd-114">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="18ccd-115">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="18ccd-115">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="18ccd-116">Ändern Sie den Wert in der **Option Compare** Feld.</span><span class="sxs-lookup"><span data-stu-id="18ccd-116">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="18ccd-117">-Optioncompare programmgesteuert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="18ccd-117">To set -optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="18ccd-118">Finden Sie unter [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="18ccd-118">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="18ccd-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="18ccd-119">Example</span></span>  
 <span data-ttu-id="18ccd-120">Der folgende code kompiliert `ProjFile.vb` und binäre Zeichenfolgenvergleiche verwendet.</span><span class="sxs-lookup"><span data-stu-id="18ccd-120">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>  
  
```console
vbc -optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="18ccd-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18ccd-121">See also</span></span>
- [<span data-ttu-id="18ccd-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="18ccd-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="18ccd-123">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="18ccd-123">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="18ccd-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="18ccd-124">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="18ccd-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="18ccd-125">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="18ccd-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="18ccd-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="18ccd-127">Option Compare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="18ccd-127">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="18ccd-128">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="18ccd-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
