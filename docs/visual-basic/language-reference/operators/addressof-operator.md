---
title: AddressOf-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 52560a2d9071373fd28f7aad2e485da08324656d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="1b4e8-102">AddressOf-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b4e8-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="1b4e8-103">Erstellt eine Delegatinstanz einer Prozedur, die bestimmte Prozedur verweist.</span><span class="sxs-lookup"><span data-stu-id="1b4e8-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b4e8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b4e8-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="1b4e8-105">Teile</span><span class="sxs-lookup"><span data-stu-id="1b4e8-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="1b4e8-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b4e8-106">Required.</span></span> <span data-ttu-id="1b4e8-107">Gibt an, wie durch den Delegaten neu erstellte Prozedur verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1b4e8-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b4e8-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b4e8-108">Remarks</span></span>  
 <span data-ttu-id="1b4e8-109">Die `AddressOf` Operator erstellt ein Funktionsdelegat, der auf die angegebene Funktion zeigt `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="1b4e8-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="1b4e8-110">Wenn ist die angegebene Prozedur an, dass die Instanz und die Methode eine Instanzmethode der Funktionsdelegat bezieht.</span><span class="sxs-lookup"><span data-stu-id="1b4e8-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="1b4e8-111">Klicken Sie dann wird den Funktionsdelegat aufgerufen wird, die angegebene Methode der angegebenen Instanz aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1b4e8-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="1b4e8-112">Die `AddressOf` -Operator kann verwendet werden, wie der Operand eines Delegatkonstruktors oder in einem Kontext, in dem der Typ des Delegaten vom Compiler bestimmt werden kann, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b4e8-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b4e8-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b4e8-113">Example</span></span>  
 <span data-ttu-id="1b4e8-114">Dieses Beispiel verwendet die `AddressOf` Operator zum Festlegen eines Delegaten behandeln die `Click` Ereignis einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="1b4e8-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="1b4e8-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b4e8-115">Example</span></span>  
 <span data-ttu-id="1b4e8-116">Im folgenden Beispiel wird die `AddressOf` Operator, um die Autostart-Funktion für einen Thread zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="1b4e8-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1b4e8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b4e8-117">See Also</span></span>  
 [<span data-ttu-id="1b4e8-118">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1b4e8-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="1b4e8-119">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1b4e8-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="1b4e8-120">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1b4e8-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="1b4e8-121">Delegaten</span><span class="sxs-lookup"><span data-stu-id="1b4e8-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
