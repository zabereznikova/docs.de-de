---
title: '#Region-Anweisung (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: db8063cf06ad0735bb4d9290c60548f7ff9af217
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611942"
---
# <a name="region-directive"></a><span data-ttu-id="20a6c-102">#Region-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20a6c-102">#Region Directive</span></span>
<span data-ttu-id="20a6c-103">Reduziert Codeabschnitte in Visual Basic-Dateien und blendet sie aus.</span><span class="sxs-lookup"><span data-stu-id="20a6c-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20a6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20a6c-104">Syntax</span></span>  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="20a6c-105">Teile</span><span class="sxs-lookup"><span data-stu-id="20a6c-105">Parts</span></span>  
  
|<span data-ttu-id="20a6c-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="20a6c-106">Term</span></span>|<span data-ttu-id="20a6c-107">Definition</span><span class="sxs-lookup"><span data-stu-id="20a6c-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="20a6c-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="20a6c-108">Required.</span></span> <span data-ttu-id="20a6c-109">Eine Zeichenfolge, die als Bereichtitel fungiert, wenn sie reduziert ist.</span><span class="sxs-lookup"><span data-stu-id="20a6c-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="20a6c-110">Bereiche werden standardmäßig reduziert.</span><span class="sxs-lookup"><span data-stu-id="20a6c-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="20a6c-111">Beendet den `#Region`-Block.</span><span class="sxs-lookup"><span data-stu-id="20a6c-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20a6c-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20a6c-112">Remarks</span></span>  
 <span data-ttu-id="20a6c-113">Mit der `#Region`-Direktive können Sie einen Codeblock festlegen, der bei Verwendung der Gliederungsfunktion des Code-Editors von Visual Studio erweitert oder reduziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="20a6c-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="20a6c-114">Sie können platzieren, oder *schachteln*, innerhalb von anderen Bereichen, die ähnliche Bereiche zusammen gruppiert.</span><span class="sxs-lookup"><span data-stu-id="20a6c-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20a6c-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="20a6c-115">Example</span></span>  
 <span data-ttu-id="20a6c-116">Dieses Beispiel verwendet die `#Region`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="20a6c-116">This example uses the `#Region` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="20a6c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20a6c-117">See also</span></span>
- [<span data-ttu-id="20a6c-118">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="20a6c-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="20a6c-119">Gliedern</span><span class="sxs-lookup"><span data-stu-id="20a6c-119">Outlining</span></span>](/visualstudio/ide/outlining)
- [<span data-ttu-id="20a6c-120">Vorgehensweise: Reduzieren und Ausblenden von Codeabschnitten</span><span class="sxs-lookup"><span data-stu-id="20a6c-120">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
