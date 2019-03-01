---
title: Erase-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 5828e28b84ec62c7ed674757090806d73c61caea
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966735"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="dda0a-102">Erase-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dda0a-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="dda0a-103">Zum Freigeben von Arrayvariablen und Freigeben des Speicherplatzes, der für ihre Elemente verwendet.</span><span class="sxs-lookup"><span data-stu-id="dda0a-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dda0a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dda0a-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="dda0a-105">Teile</span><span class="sxs-lookup"><span data-stu-id="dda0a-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="dda0a-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dda0a-106">Required.</span></span> <span data-ttu-id="dda0a-107">Liste der Arrayvariablen gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="dda0a-107">List of array variables to be erased.</span></span> <span data-ttu-id="dda0a-108">Mehrere Variablen werden durch Kommas voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="dda0a-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dda0a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dda0a-109">Remarks</span></span>  
 <span data-ttu-id="dda0a-110">Die `Erase` Anweisung kann nur auf Prozedurebene angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dda0a-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="dda0a-111">Dies bedeutet, dass Sie Arrays innerhalb einer Prozedur, aber nicht auf Klassen-oder Modulebene freigeben können.</span><span class="sxs-lookup"><span data-stu-id="dda0a-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="dda0a-112">Die `Erase` -Anweisung ist identisch mit der Zuweisung `Nothing` jedes Array-Variable.</span><span class="sxs-lookup"><span data-stu-id="dda0a-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dda0a-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dda0a-113">Example</span></span>  
 <span data-ttu-id="dda0a-114">Im folgenden Beispiel wird die `Erase` Anweisung, um zwei Arrays gelöscht und deren Speicher freigeben (1000 und 100 Speicherelemente, bzw.).</span><span class="sxs-lookup"><span data-stu-id="dda0a-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="dda0a-115">Die `ReDim` Anweisung dann weist eine neue Arrayinstanz, auf das dreidimensionale Array.</span><span class="sxs-lookup"><span data-stu-id="dda0a-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="dda0a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dda0a-116">See also</span></span>
- [<span data-ttu-id="dda0a-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="dda0a-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="dda0a-118">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dda0a-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
