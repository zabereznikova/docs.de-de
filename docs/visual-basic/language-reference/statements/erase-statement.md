---
title: Erase-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 317e2a7dc5facb08388f3a3e635734e4daed5eac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601792"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="b834b-102">Erase-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b834b-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="b834b-103">Zum Arrayvariablen freigeben und Aufheben der Zuordnung für ihre Elemente verwendeten Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="b834b-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b834b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b834b-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="b834b-105">Teile</span><span class="sxs-lookup"><span data-stu-id="b834b-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="b834b-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b834b-106">Required.</span></span> <span data-ttu-id="b834b-107">Liste der Arrayvariablen gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="b834b-107">List of array variables to be erased.</span></span> <span data-ttu-id="b834b-108">Mehrere Variablen werden durch Kommas voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="b834b-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b834b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b834b-109">Remarks</span></span>  
 <span data-ttu-id="b834b-110">Die `Erase` Anweisung kann nur auf Prozedurebene angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b834b-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="b834b-111">Dies bedeutet, dass Sie Arrays innerhalb einer Prozedur, aber nicht auf Klassen-oder Modulebene freigeben können.</span><span class="sxs-lookup"><span data-stu-id="b834b-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="b834b-112">Die `Erase` Anweisung ist äquivalent zum Zuweisen von `Nothing` jedes Array-Variable.</span><span class="sxs-lookup"><span data-stu-id="b834b-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b834b-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b834b-113">Example</span></span>  
 <span data-ttu-id="b834b-114">Im folgenden Beispiel wird die `Erase` Anweisung zum Löschen von zwei Arrays und Freigeben von Speicher (1000 und 100 Speicherelemente bzw.).</span><span class="sxs-lookup"><span data-stu-id="b834b-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="b834b-115">Die `ReDim` Anweisung dann weist eine neue Arrayinstanz auf das dreidimensionale Array.</span><span class="sxs-lookup"><span data-stu-id="b834b-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b834b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b834b-116">See Also</span></span>  
 [<span data-ttu-id="b834b-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="b834b-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)  
 [<span data-ttu-id="b834b-118">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b834b-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
