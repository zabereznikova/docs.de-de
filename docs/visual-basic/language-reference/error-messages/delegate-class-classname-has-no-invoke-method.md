---
title: Delegatklasse &#39; &lt;Classname&gt; &#39; hat keine Invoke-Methode, sodass ein Ausdruck dieses Typs kann nicht das Ziel eines Methodenaufrufs
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: d5421ea05968a221bbbf8f52a575550d1bca3cb2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653157"
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="aadaa-102">Delegatklasse &#39; &lt;Classname&gt; &#39; hat keine Invoke-Methode, sodass ein Ausdruck dieses Typs kann nicht das Ziel eines Methodenaufrufs</span><span class="sxs-lookup"><span data-stu-id="aadaa-102">Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="aadaa-103">Ein Aufruf von `Invoke` über einen Delegaten ist fehlgeschlagen, da `Invoke` ist nicht auf die Delegate-Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="aadaa-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="aadaa-104">**Fehler-ID:** BC30220</span><span class="sxs-lookup"><span data-stu-id="aadaa-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="aadaa-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="aadaa-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="aadaa-106">Stellen Sie sicher, dass mit eine Instanz von der "Delegate"-Klasse erstellt wurde eine `Dim` -Anweisung und die Delegatinstanz mit eine Prozedur zugewiesen wurde die `AddressOf` Operator.</span><span class="sxs-lookup"><span data-stu-id="aadaa-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="aadaa-107">Suchen Sie den Code, der die Delegate-Klasse implementiert, und stellen Sie sicher, dass es implementiert die `Invoke` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="aadaa-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aadaa-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aadaa-108">See also</span></span>
- [<span data-ttu-id="aadaa-109">Delegaten</span><span class="sxs-lookup"><span data-stu-id="aadaa-109">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="aadaa-110">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aadaa-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="aadaa-111">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="aadaa-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="aadaa-112">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aadaa-112">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
