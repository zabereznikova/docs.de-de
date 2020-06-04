---
title: AddressOf-Operator
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 3e7db8e7329ce8d21b6e07863e6f1673a6389608
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372063"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="0a09f-102">AddressOf-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a09f-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="0a09f-103">Erstellt eine Delegatinstanz, die auf die jeweilige Prozedur verweist.</span><span class="sxs-lookup"><span data-stu-id="0a09f-103">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a09f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a09f-104">Syntax</span></span>  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="0a09f-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="0a09f-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="0a09f-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0a09f-106">Required.</span></span> <span data-ttu-id="0a09f-107">Gibt die Prozedur an, auf die durch den neu erstellten Delegaten verwiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0a09f-107">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a09f-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0a09f-108">Remarks</span></span>  
 <span data-ttu-id="0a09f-109">Der- `AddressOf` Operator erstellt einen Delegaten, der auf die durch angegebene untergeordnete or-Funktion verweist `procedurename` .</span><span class="sxs-lookup"><span data-stu-id="0a09f-109">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="0a09f-110">Wenn die angegebene Prozedur eine Instanzmethode ist, verweist der Delegat sowohl auf die-Instanz als auch auf die-Methode.</span><span class="sxs-lookup"><span data-stu-id="0a09f-110">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="0a09f-111">Wenn der Delegat aufgerufen wird, wird die angegebene Methode der angegebenen-Instanz aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0a09f-111">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="0a09f-112">Der `AddressOf` Operator kann als Operand eines Delegatkonstruktors oder in einem Kontext verwendet werden, in dem der Typ des Delegaten vom Compiler bestimmt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0a09f-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a09f-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a09f-113">Example</span></span>  
 <span data-ttu-id="0a09f-114">In diesem Beispiel wird der- `AddressOf` Operator verwendet, um einen Delegaten zur Behandlung des- `Click` Ereignisses einer Schaltfläche festzulegen.</span><span class="sxs-lookup"><span data-stu-id="0a09f-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="0a09f-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a09f-115">Example</span></span>  
 <span data-ttu-id="0a09f-116">Im folgenden Beispiel wird der- `AddressOf` Operator verwendet, um die Startup-Funktion für einen Thread festzulegen.</span><span class="sxs-lookup"><span data-stu-id="0a09f-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="0a09f-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a09f-117">See also</span></span>

- [<span data-ttu-id="0a09f-118">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="0a09f-118">Declare Statement</span></span>](../statements/declare-statement.md)
- [<span data-ttu-id="0a09f-119">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0a09f-119">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="0a09f-120">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0a09f-120">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="0a09f-121">Delegaten</span><span class="sxs-lookup"><span data-stu-id="0a09f-121">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
