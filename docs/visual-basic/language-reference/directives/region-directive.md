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
ms.openlocfilehash: cd53a6079c1564a8c73a0a1a6273fc166d18d3e6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409937"
---
# <a name="region-directive"></a><span data-ttu-id="1ae6b-102">#Region-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1ae6b-102">#Region Directive</span></span>

<span data-ttu-id="1ae6b-103">Reduziert Codeabschnitte in Visual Basic-Dateien und blendet sie aus.</span><span class="sxs-lookup"><span data-stu-id="1ae6b-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ae6b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ae6b-104">Syntax</span></span>  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="1ae6b-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="1ae6b-105">Parts</span></span>  
  
|<span data-ttu-id="1ae6b-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="1ae6b-106">Term</span></span>|<span data-ttu-id="1ae6b-107">Definition</span><span class="sxs-lookup"><span data-stu-id="1ae6b-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="1ae6b-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1ae6b-108">Required.</span></span> <span data-ttu-id="1ae6b-109">Eine Zeichenfolge, die als Bereichtitel fungiert, wenn sie reduziert ist.</span><span class="sxs-lookup"><span data-stu-id="1ae6b-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="1ae6b-110">Bereiche werden standardmäßig reduziert.</span><span class="sxs-lookup"><span data-stu-id="1ae6b-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="1ae6b-111">Beendet den `#Region`-Block.</span><span class="sxs-lookup"><span data-stu-id="1ae6b-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ae6b-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1ae6b-112">Remarks</span></span>  

 <span data-ttu-id="1ae6b-113">Mit der `#Region`-Anweisung können Sie einen Codeblock festlegen, der bei Verwendung der Gliederungsfunktion des Code-Editors von Visual Studio erweitert oder reduziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1ae6b-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="1ae6b-114">Sie können Bereiche in anderen Regionen platzieren oder *verschachteln*, um ähnliche Bereiche zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="1ae6b-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ae6b-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ae6b-115">Example</span></span>  

 <span data-ttu-id="1ae6b-116">Dieses Beispiel verwendet die `#Region`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1ae6b-116">This example uses the `#Region` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="1ae6b-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ae6b-117">See also</span></span>

- [<span data-ttu-id="1ae6b-118">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="1ae6b-118">#If...Then...#Else Directives</span></span>](if-then-else-directives.md)
- [<span data-ttu-id="1ae6b-119">Gliedern</span><span class="sxs-lookup"><span data-stu-id="1ae6b-119">Outlining</span></span>](/visualstudio/ide/outlining)
- [<span data-ttu-id="1ae6b-120">Vorgehensweise: Reduzieren und Ausblenden von Codeabschnitten</span><span class="sxs-lookup"><span data-stu-id="1ae6b-120">How to: Collapse and Hide Sections of Code</span></span>](../../programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
