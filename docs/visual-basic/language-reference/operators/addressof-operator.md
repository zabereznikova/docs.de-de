---
title: AddressOf-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: b68d93009d2d297f8b8867fb8e79b26173a45095
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56964668"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="1de9c-102">AddressOf-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1de9c-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="1de9c-103">Erstellt eine Instanz eines Delegaten, die auf bestimmte Prozedur verweist.</span><span class="sxs-lookup"><span data-stu-id="1de9c-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1de9c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1de9c-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="1de9c-105">Teile</span><span class="sxs-lookup"><span data-stu-id="1de9c-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="1de9c-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1de9c-106">Required.</span></span> <span data-ttu-id="1de9c-107">Gibt an, wie durch den Delegaten für die neu erstellte Prozedur verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1de9c-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1de9c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1de9c-108">Remarks</span></span>  
 <span data-ttu-id="1de9c-109">Die `AddressOf` Operator erstellt eine zu delegierende Funktion, die auf die angegebene Funktion zeigt `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="1de9c-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="1de9c-110">Wenn ist die angegebene Prozedur an, dass eine Instanzmethode klicken Sie dann den Funktionsdelegaten auf die Instanz und die Methode verweist.</span><span class="sxs-lookup"><span data-stu-id="1de9c-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="1de9c-111">Klicken Sie dann beim Aufrufen der Funktionsdelegaten wird die angegebene Methode der angegebenen Instanz aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1de9c-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="1de9c-112">Die `AddressOf` Operator kann verwendet werden, wie der Operand eines Delegatkonstruktors oder in einem Kontext, in dem der Typ des Delegaten vom Compiler bestimmt werden kann, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1de9c-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1de9c-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1de9c-113">Example</span></span>  
 <span data-ttu-id="1de9c-114">Dieses Beispiel verwendet die `AddressOf` Operator zum Festlegen eines Delegaten behandeln die `Click` -Ereignis einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="1de9c-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="1de9c-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1de9c-115">Example</span></span>  
 <span data-ttu-id="1de9c-116">Im folgenden Beispiel wird die `AddressOf` Operator, um die Startfunktion für einen Thread bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1de9c-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="1de9c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1de9c-117">See also</span></span>
- [<span data-ttu-id="1de9c-118">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1de9c-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="1de9c-119">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1de9c-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="1de9c-120">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1de9c-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="1de9c-121">Delegaten</span><span class="sxs-lookup"><span data-stu-id="1de9c-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
