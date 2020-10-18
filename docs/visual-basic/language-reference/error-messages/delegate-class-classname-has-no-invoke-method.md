---
title: Die Delegatklasse "<classname>" hat keine Invoke-Methode. Ein Ausdruck dieses Typs kann daher nicht das Ziel eines Methodenaufrufs sein.
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 4e0fc61c7356008755134f670fa1fab0165cfd48
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162790"
---
# <a name="bc30220-delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="56491-102">BC30220: die Delegatklasse " \<classname> " hat keine Aufruf Methode. ein Ausdruck dieses Typs kann daher nicht das Ziel eines Methoden Aufrufs sein.</span><span class="sxs-lookup"><span data-stu-id="56491-102">BC30220: Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>

<span data-ttu-id="56491-103">Ein Aufruf von `Invoke` über einen Delegaten ist fehlgeschlagen, da `Invoke` nicht in der Delegatklasse implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="56491-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>

 <span data-ttu-id="56491-104">**Fehler-ID:** BC30220</span><span class="sxs-lookup"><span data-stu-id="56491-104">**Error ID:** BC30220</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="56491-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="56491-105">To correct this error</span></span>

1. <span data-ttu-id="56491-106">Stellen Sie sicher, dass eine Instanz der Delegatklasse mit einer `Dim` -Anweisung erstellt wurde und dass der Delegatinstanz mit dem-Operator eine Prozedur zugewiesen wurde `AddressOf` .</span><span class="sxs-lookup"><span data-stu-id="56491-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>

2. <span data-ttu-id="56491-107">Suchen Sie den Code, der die Delegatklasse implementiert, und stellen Sie sicher, dass Sie die `Invoke` Prozedur implementiert.</span><span class="sxs-lookup"><span data-stu-id="56491-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="56491-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56491-108">See also</span></span>

- [<span data-ttu-id="56491-109">Delegaten</span><span class="sxs-lookup"><span data-stu-id="56491-109">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="56491-110">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="56491-110">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="56491-111">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="56491-111">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="56491-112">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="56491-112">Dim Statement</span></span>](../statements/dim-statement.md)
