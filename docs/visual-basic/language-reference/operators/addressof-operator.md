---
title: AddressOf-Operator (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e29b7ae2a6f6040cfc8c6e0cd0c9eb055a6694e9
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="16777-102">AddressOf-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16777-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="16777-103">Erstellt eine Instanz eines Delegaten, die die Prozedur verweist.</span><span class="sxs-lookup"><span data-stu-id="16777-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16777-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="16777-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="16777-105">Teile</span><span class="sxs-lookup"><span data-stu-id="16777-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="16777-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="16777-106">Required.</span></span> <span data-ttu-id="16777-107">Gibt an, wie durch die neu erstellte Delegaten verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="16777-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16777-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16777-108">Remarks</span></span>  
 <span data-ttu-id="16777-109">Die `AddressOf` Operator erstellt einen Funktionsdelegaten, der auf die angegebene Funktion zeigt `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="16777-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="16777-110">Wenn ist die angegebene Prozedur eine Instanzenmethode der Funktionsdelegat sowohl auf die Instanz als auch auf die Methode verweist.</span><span class="sxs-lookup"><span data-stu-id="16777-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="16777-111">Klicken Sie dann wird der Funktionsdelegat aufgerufen wird, die angegebene Methode der angegebenen Instanz aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="16777-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="16777-112">Die `AddressOf` -Operator kann als Operand eines Delegatkonstruktors verwendet werden, oder es kann verwendet werden, in einem Kontext, in dem der Typ des Delegaten vom Compiler bestimmt werden kann.</span><span class="sxs-lookup"><span data-stu-id="16777-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16777-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16777-113">Example</span></span>  
 <span data-ttu-id="16777-114">Dieses Beispiel verwendet die `AddressOf` Operator zum Festlegen eines Delegaten behandeln die `Click` Ereignis einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="16777-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 <span data-ttu-id="16777-115">[!code-vb[VbVbalrDelegates&#8;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="16777-115">[!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="16777-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16777-116">Example</span></span>  
 <span data-ttu-id="16777-117">Im folgenden Beispiel wird die `AddressOf` Operator, um die Startfunktion für einen Thread bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="16777-117">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 <span data-ttu-id="16777-118">[!code-vb[VbVbalrDelegates&#9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="16777-118">[!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16777-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16777-119">See Also</span></span>  
 <span data-ttu-id="16777-120">[Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="16777-120">[Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) </span></span>  
<span data-ttu-id="16777-121"> [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="16777-121"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="16777-122"> [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="16777-122"> [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="16777-123"> [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span><span class="sxs-lookup"><span data-stu-id="16777-123"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span></span>

