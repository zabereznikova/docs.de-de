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
ms.openlocfilehash: 2ebadf5ded1a23fe46b8e16cf18ae265b5d3c255
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591652"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="fb9d1-102">AddressOf-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb9d1-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="fb9d1-103">Erstellt eine Delegatinstanz, die auf die jeweilige Prozedur verweist.</span><span class="sxs-lookup"><span data-stu-id="fb9d1-103">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb9d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb9d1-104">Syntax</span></span>  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="fb9d1-105">Teile</span><span class="sxs-lookup"><span data-stu-id="fb9d1-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="fb9d1-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fb9d1-106">Required.</span></span> <span data-ttu-id="fb9d1-107">Gibt die Prozedur an, auf die durch den neu erstellten Delegaten verwiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb9d1-107">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb9d1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb9d1-108">Remarks</span></span>  
 <span data-ttu-id="fb9d1-109">Der `AddressOf`-Operator erstellt einen Delegaten, der auf die untergeordnete or-Funktion verweist, die von `procedurename` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fb9d1-109">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="fb9d1-110">Wenn die angegebene Prozedur eine Instanzmethode ist, verweist der Delegat sowohl auf die-Instanz als auch auf die-Methode.</span><span class="sxs-lookup"><span data-stu-id="fb9d1-110">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="fb9d1-111">Wenn der Delegat aufgerufen wird, wird die angegebene Methode der angegebenen-Instanz aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fb9d1-111">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="fb9d1-112">Der `AddressOf`-Operator kann als Operand eines Delegatkonstruktors oder in einem Kontext verwendet werden, in dem der Typ des Delegaten vom Compiler bestimmt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb9d1-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb9d1-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb9d1-113">Example</span></span>  
 <span data-ttu-id="fb9d1-114">In diesem Beispiel wird der `AddressOf`-Operator verwendet, um einen Delegaten zu bestimmen, der das `Click`-Ereignis einer Schaltfläche behandelt.</span><span class="sxs-lookup"><span data-stu-id="fb9d1-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="fb9d1-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb9d1-115">Example</span></span>  
 <span data-ttu-id="fb9d1-116">Im folgenden Beispiel wird der `AddressOf`-Operator verwendet, um die Startup-Funktion für einen Thread festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fb9d1-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="fb9d1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb9d1-117">See also</span></span>

- [<span data-ttu-id="fb9d1-118">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fb9d1-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="fb9d1-119">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fb9d1-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="fb9d1-120">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fb9d1-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="fb9d1-121">Delegaten</span><span class="sxs-lookup"><span data-stu-id="fb9d1-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
