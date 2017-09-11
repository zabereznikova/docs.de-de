---
title: / optioncompare | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioncompare
dev_langs:
- VB
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c9512427cda0b6a3bcb0c1fe338b47ff9f779d19
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="optioncompare"></a><span data-ttu-id="89c2a-102">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="89c2a-102">/optioncompare</span></span>
<span data-ttu-id="89c2a-103">Gibt an, wie Zeichenfolgenvergleiche durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="89c2a-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89c2a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89c2a-104">Syntax</span></span>  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="89c2a-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89c2a-105">Remarks</span></span>  
 <span data-ttu-id="89c2a-106">Können Sie angeben, `/optioncompare` in zwei Formen: `/optioncompare:binary` zur Verwendung von binären Zeichenfolgenvergleichen und `/optioncompare:text` zum Vergleichen von Zeichenfolgen verwenden.</span><span class="sxs-lookup"><span data-stu-id="89c2a-106">You can specify `/optioncompare` in one of two forms: `/optioncompare:binary` to use binary string comparisons, and `/optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="89c2a-107">Standardmäßig verwendet der Compiler `/optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="89c2a-107">By default, the compiler uses `/optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="89c2a-108">In Microsoft Windows bestimmt die verwendete Codepage die binäre Sortierreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="89c2a-108">In Microsoft Windows, the code page being used determines the binary sort order.</span></span> <span data-ttu-id="89c2a-109">Eine typische binäre Sortierreihenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="89c2a-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="89c2a-110">Textbasierte Zeichenfolgenvergleiche basieren auf einer Textsortierreihenfolge durch das Gebietsschema des Systems bestimmt.</span><span class="sxs-lookup"><span data-stu-id="89c2a-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="89c2a-111">Eine normale Textsortierreihenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="89c2a-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="89c2a-112">/ Optioncompare in der Visual Studio-IDE festlegen</span><span class="sxs-lookup"><span data-stu-id="89c2a-112">To set /optioncompare in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="89c2a-113">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="89c2a-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="89c2a-114">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="89c2a-114">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="89c2a-115">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="89c2a-115">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="89c2a-116">Klicken Sie auf die **Kompilieren** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="89c2a-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="89c2a-117">Ändern Sie den Wert in der **Option Compare** Feld.</span><span class="sxs-lookup"><span data-stu-id="89c2a-117">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set-optioncompare-programmatically"></a><span data-ttu-id="89c2a-118">So legen Sie/optioncompare programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="89c2a-118">To set /optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="89c2a-119">Finden Sie unter [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="89c2a-119">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89c2a-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89c2a-120">Example</span></span>  
 <span data-ttu-id="89c2a-121">Der folgende Code kompiliert`rojFile.vb` und binärer Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="89c2a-121">The following code compiles P`rojFile.vb` and uses binary string comparisons.</span></span>  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="89c2a-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89c2a-122">See Also</span></span>  
 <span data-ttu-id="89c2a-123">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="89c2a-123">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="89c2a-124"> [/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="89c2a-124"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="89c2a-125"> [/ optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="89c2a-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="89c2a-126"> [/ optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="89c2a-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="89c2a-127"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="89c2a-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="89c2a-128"> [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="89c2a-128"> [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span></span>  
<span data-ttu-id="89c2a-129"> [VB-Standard, Projekte, Dialogfeld „Optionen“](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="89c2a-129"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
