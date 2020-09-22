---
title: Erase-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 33d88b5ce71ceab8d4b4b59d356c53a804c360be
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873287"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="69196-102">Erase-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69196-102">Erase Statement (Visual Basic)</span></span>

<span data-ttu-id="69196-103">Wird zum Freigeben von Array Variablen und zum Freigeben des für ihre Elemente verwendeten Speichers verwendet.</span><span class="sxs-lookup"><span data-stu-id="69196-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69196-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="69196-104">Syntax</span></span>  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="69196-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="69196-105">Parts</span></span>  

 `arraylist`  
 <span data-ttu-id="69196-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="69196-106">Required.</span></span> <span data-ttu-id="69196-107">Liste der zu löschenden Array Variablen.</span><span class="sxs-lookup"><span data-stu-id="69196-107">List of array variables to be erased.</span></span> <span data-ttu-id="69196-108">Mehrere Variablen werden durch Kommas voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="69196-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69196-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="69196-109">Remarks</span></span>  

 <span data-ttu-id="69196-110">Die- `Erase` Anweisung kann nur auf Prozedur Ebene angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="69196-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="69196-111">Dies bedeutet, dass Sie Arrays innerhalb einer Prozedur freigeben können, jedoch nicht auf Klassen-oder Modulebene.</span><span class="sxs-lookup"><span data-stu-id="69196-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="69196-112">Die- `Erase` Anweisung entspricht der Zuweisung `Nothing` zu jeder Array Variablen.</span><span class="sxs-lookup"><span data-stu-id="69196-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69196-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="69196-113">Example</span></span>  

 <span data-ttu-id="69196-114">Im folgenden Beispiel wird die `Erase` -Anweisung verwendet, um zwei Arrays zu löschen und Ihren Arbeitsspeicher (1000 bzw. 100 Speicherelemente) freizugeben.</span><span class="sxs-lookup"><span data-stu-id="69196-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="69196-115">Die- `ReDim` Anweisung weist dann dem dreidimensionalen Array eine neue Array Instanz zu.</span><span class="sxs-lookup"><span data-stu-id="69196-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="69196-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69196-116">See also</span></span>

- [<span data-ttu-id="69196-117">Schweigen</span><span class="sxs-lookup"><span data-stu-id="69196-117">Nothing</span></span>](../nothing.md)
- [<span data-ttu-id="69196-118">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="69196-118">ReDim Statement</span></span>](redim-statement.md)
