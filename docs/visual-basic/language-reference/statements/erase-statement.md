---
title: Erase-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 7dec2a859f664ee8dcbb305082ec33aeacbaccb4
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583385"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="00aec-102">Erase-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00aec-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="00aec-103">Wird zum Freigeben von Array Variablen und zum Freigeben des für ihre Elemente verwendeten Speichers verwendet.</span><span class="sxs-lookup"><span data-stu-id="00aec-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00aec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00aec-104">Syntax</span></span>  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="00aec-105">Teile</span><span class="sxs-lookup"><span data-stu-id="00aec-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="00aec-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00aec-106">Required.</span></span> <span data-ttu-id="00aec-107">Liste der zu löschenden Array Variablen.</span><span class="sxs-lookup"><span data-stu-id="00aec-107">List of array variables to be erased.</span></span> <span data-ttu-id="00aec-108">Mehrere Variablen werden durch Kommas voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="00aec-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00aec-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00aec-109">Remarks</span></span>  
 <span data-ttu-id="00aec-110">Die `Erase`-Anweisung kann nur auf Prozedur Ebene angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="00aec-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="00aec-111">Dies bedeutet, dass Sie Arrays innerhalb einer Prozedur freigeben können, jedoch nicht auf Klassen-oder Modulebene.</span><span class="sxs-lookup"><span data-stu-id="00aec-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="00aec-112">Die `Erase`-Anweisung entspricht der Zuweisung von `Nothing` zu jeder Array Variablen.</span><span class="sxs-lookup"><span data-stu-id="00aec-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00aec-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00aec-113">Example</span></span>  
 <span data-ttu-id="00aec-114">Im folgenden Beispiel werden die `Erase`-Anweisung verwendet, um zwei Arrays zu löschen und Ihren Arbeitsspeicher (1000 bzw. 100 Speicherelemente) freizugeben.</span><span class="sxs-lookup"><span data-stu-id="00aec-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="00aec-115">Die `ReDim`-Anweisung weist dann dem dreidimensionalen Array eine neue Array Instanz zu.</span><span class="sxs-lookup"><span data-stu-id="00aec-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="00aec-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00aec-116">See also</span></span>

- [<span data-ttu-id="00aec-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="00aec-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="00aec-118">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="00aec-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
