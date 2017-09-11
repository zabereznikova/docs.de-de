---
title: '#Region-Direktive | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Region
- vb.#Region
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: 14
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
ms.openlocfilehash: 86b8e9ce99a8c12e290f5efdc5a5c4da57f350d9
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="region-directive"></a>#<span data-ttu-id="f9998-102">Region-Direktive</span><span class="sxs-lookup"><span data-stu-id="f9998-102">Region Directive</span></span>
<span data-ttu-id="f9998-103">Reduziert Codeabschnitte in Visual Basic-Dateien und blendet sie aus.</span><span class="sxs-lookup"><span data-stu-id="f9998-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9998-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9998-104">Syntax</span></span>  
  
```  
  
      #Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="f9998-105">Teile</span><span class="sxs-lookup"><span data-stu-id="f9998-105">Parts</span></span>  
  
|<span data-ttu-id="f9998-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="f9998-106">Term</span></span>|<span data-ttu-id="f9998-107">Definition</span><span class="sxs-lookup"><span data-stu-id="f9998-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="f9998-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f9998-108">Required.</span></span> <span data-ttu-id="f9998-109">Eine Zeichenfolge, die als Bereichtitel fungiert, wenn sie reduziert ist.</span><span class="sxs-lookup"><span data-stu-id="f9998-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="f9998-110">Bereiche werden standardmäßig reduziert.</span><span class="sxs-lookup"><span data-stu-id="f9998-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="f9998-111">Beendet den `#Region`-Block.</span><span class="sxs-lookup"><span data-stu-id="f9998-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9998-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9998-112">Remarks</span></span>  
 <span data-ttu-id="f9998-113">Mit der `#Region`-Direktive können Sie einen Codeblock festlegen, der bei Verwendung der Gliederungsfunktion des Code-Editors von Visual Studio erweitert oder reduziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f9998-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="f9998-114">Sie können platzieren, oder *schachteln*, innerhalb von anderen Bereichen, um ähnliche Bereiche zusammen zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="f9998-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9998-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9998-115">Example</span></span>  
 <span data-ttu-id="f9998-116">Dieses Beispiel verwendet die `#Region`-Direktive.</span><span class="sxs-lookup"><span data-stu-id="f9998-116">This example uses the `#Region` directive.</span></span>  
  
 <span data-ttu-id="f9998-117">[!code-vb[VbVbalrConditionalComp&4;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f9998-117">[!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9998-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9998-118">See Also</span></span>  
 <span data-ttu-id="f9998-119">[#If... Then... #Else-Direktive](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span><span class="sxs-lookup"><span data-stu-id="f9998-119">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span></span>  
<span data-ttu-id="f9998-120"> [Gliederung](https://docs.microsoft.com/visualstudio/ide/outlining) </span><span class="sxs-lookup"><span data-stu-id="f9998-120"> [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining) </span></span>  
<span data-ttu-id="f9998-121"> [Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)</span><span class="sxs-lookup"><span data-stu-id="f9998-121"> [How to: Collapse and Hide Sections of Code](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)</span></span>
