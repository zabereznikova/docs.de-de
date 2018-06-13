---
title: Der Name einer Bereichsvariablen kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: d6d082511d501b961b537317f0cb17bcd1c9370b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594620"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="b5158-102">Der Name einer Bereichsvariablen kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden</span><span class="sxs-lookup"><span data-stu-id="b5158-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="b5158-103">Ein Programmierelement, die eine oder mehrere Argumente akzeptiert, ist in einer LINQ-Abfrage enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5158-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="b5158-104">Der Compiler kann eine Bereichsvariable aus dieser Programmierelement abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="b5158-104">The compiler is unable to infer a range variable from that programming element.</span></span>  
  
 <span data-ttu-id="b5158-105">**Fehler-ID:** BC36599</span><span class="sxs-lookup"><span data-stu-id="b5158-105">**Error ID:** BC36599</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b5158-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b5158-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="b5158-107">Geben Sie einen expliziten Variablennamen für das Programmierelement an, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b5158-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5158-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5158-108">See Also</span></span>  
 [<span data-ttu-id="b5158-109">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b5158-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="b5158-110">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="b5158-110">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
