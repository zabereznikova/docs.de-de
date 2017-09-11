---
title: '&quot;AddressOf&quot;-Operand muss der Name einer Methode (ohne Klammern) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
dev_langs:
- VB
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 10
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c4ee57896b70d8af1a7bc245bdb45521c2442fea
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="a2522-102">"AddressOf"-Operand muss der Name einer Methode (ohne Klammern) sein.</span><span class="sxs-lookup"><span data-stu-id="a2522-102">&#39;AddressOf&#39; operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="a2522-103">Der `AddressOf` -Operator erstellt eine Delegatinstanz einer Prozedur, die auf eine bestimmte Prozedur verweist.</span><span class="sxs-lookup"><span data-stu-id="a2522-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="a2522-104">Die Syntax lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="a2522-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="a2522-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="a2522-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="a2522-106">Runden Klammern folgende Argument `AddressOf`, wobei keine benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="a2522-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="a2522-107">**Fehler-ID:** BC30577</span><span class="sxs-lookup"><span data-stu-id="a2522-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a2522-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a2522-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="a2522-109">Entfernen Sie die Klammern um das Argument nach `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="a2522-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="a2522-110">Stellen Sie sicher, dass das Argument ein Methodenname ist.</span><span class="sxs-lookup"><span data-stu-id="a2522-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2522-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2522-111">See Also</span></span>  
 <span data-ttu-id="a2522-112">[AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a2522-112">[AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="a2522-113"> [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span><span class="sxs-lookup"><span data-stu-id="a2522-113"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span></span>
