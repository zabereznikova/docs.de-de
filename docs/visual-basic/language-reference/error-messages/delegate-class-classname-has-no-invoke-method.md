---
title: Die Delegatklasse "<classname>" hat keine Invoke-Methode. Ein Ausdruck dieses Typs kann daher nicht das Ziel eines Methodenaufrufs sein.
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 27be97ba2930791bcb9012c824bc418a0089b037
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409711"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="161f3-102">Die Delegatklasse "\<classname>" hat keine Invoke-Methode. Ein Ausdruck dieses Typs kann daher nicht das Ziel eines Methodenaufrufs sein.</span><span class="sxs-lookup"><span data-stu-id="161f3-102">Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="161f3-103">Ein Aufruf von `Invoke` über einen Delegaten ist fehlgeschlagen, da `Invoke` nicht in der Delegatklasse implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="161f3-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="161f3-104">**Fehler-ID:** BC30220</span><span class="sxs-lookup"><span data-stu-id="161f3-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="161f3-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="161f3-105">To correct this error</span></span>  
  
1. <span data-ttu-id="161f3-106">Stellen Sie sicher, dass eine Instanz der Delegatklasse mit einer `Dim` -Anweisung erstellt wurde und dass der Delegatinstanz mit dem-Operator eine Prozedur zugewiesen wurde `AddressOf` .</span><span class="sxs-lookup"><span data-stu-id="161f3-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2. <span data-ttu-id="161f3-107">Suchen Sie den Code, der die Delegatklasse implementiert, und stellen Sie sicher, dass Sie die `Invoke` Prozedur implementiert.</span><span class="sxs-lookup"><span data-stu-id="161f3-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="161f3-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="161f3-108">See also</span></span>

- [<span data-ttu-id="161f3-109">Delegaten</span><span class="sxs-lookup"><span data-stu-id="161f3-109">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="161f3-110">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="161f3-110">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="161f3-111">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="161f3-111">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="161f3-112">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="161f3-112">Dim Statement</span></span>](../statements/dim-statement.md)
