---
title: '#Region-Anweisung'
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
ms.openlocfilehash: 4cf9b103486378d001b588aa285f590980b51bb8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343794"
---
# <a name="region-directive"></a><span data-ttu-id="b6293-102">#Region-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b6293-102">#Region Directive</span></span>

<span data-ttu-id="b6293-103">Reduziert Codeabschnitte in Visual Basic-Dateien und blendet sie aus.</span><span class="sxs-lookup"><span data-stu-id="b6293-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6293-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6293-104">Syntax</span></span>  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="b6293-105">Teile</span><span class="sxs-lookup"><span data-stu-id="b6293-105">Parts</span></span>  
  
|<span data-ttu-id="b6293-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="b6293-106">Term</span></span>|<span data-ttu-id="b6293-107">Definition</span><span class="sxs-lookup"><span data-stu-id="b6293-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="b6293-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b6293-108">Required.</span></span> <span data-ttu-id="b6293-109">Eine Zeichenfolge, die als Bereichtitel fungiert, wenn sie reduziert ist.</span><span class="sxs-lookup"><span data-stu-id="b6293-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="b6293-110">Bereiche werden standardmäßig reduziert.</span><span class="sxs-lookup"><span data-stu-id="b6293-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="b6293-111">Beendet den `#Region`-Block.</span><span class="sxs-lookup"><span data-stu-id="b6293-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6293-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6293-112">Remarks</span></span>  

 <span data-ttu-id="b6293-113">Mit der `#Region`-Anweisung können Sie einen Codeblock festlegen, der bei Verwendung der Gliederungsfunktion des Code-Editors von Visual Studio erweitert oder reduziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b6293-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="b6293-114">You can place, or *nest*, regions within other regions to group similar regions together.</span><span class="sxs-lookup"><span data-stu-id="b6293-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6293-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b6293-115">Example</span></span>  

 <span data-ttu-id="b6293-116">Dieses Beispiel verwendet die `#Region`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="b6293-116">This example uses the `#Region` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b6293-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6293-117">See also</span></span>

- [<span data-ttu-id="b6293-118">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="b6293-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="b6293-119">Gliedern</span><span class="sxs-lookup"><span data-stu-id="b6293-119">Outlining</span></span>](/visualstudio/ide/outlining)
- [<span data-ttu-id="b6293-120">Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten</span><span class="sxs-lookup"><span data-stu-id="b6293-120">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
