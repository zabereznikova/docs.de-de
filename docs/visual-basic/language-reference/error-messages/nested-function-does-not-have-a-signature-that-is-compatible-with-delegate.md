---
title: Die geschachtelte Funktion verfügt über keine Signatur, die mit dem Delegaten '<delegatename>' kompatibel ist
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 0dde340164f1ba80d0e1d9fbb5d17ba6da0a5bc4
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160053"
---
# <a name="bc36532-nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="c1349-102">BC36532: die in der Funktion "" unterstützt keine Signatur, die mit dem Delegaten "" kompatibel ist. \<delegatename></span><span class="sxs-lookup"><span data-stu-id="c1349-102">BC36532: Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>

<span data-ttu-id="c1349-103">Ein Lambda-Ausdruck wurde einem Delegaten zugewiesen, der über eine inkompatible Signatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="c1349-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="c1349-104">Im folgenden Code verfügt der Delegat beispielsweise `Del` über zwei ganzzahlige Parameter.</span><span class="sxs-lookup"><span data-stu-id="c1349-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

<span data-ttu-id="c1349-105">Der Fehler wird ausgelöst, wenn ein Lambda-Ausdruck mit einem Argument als Typ deklariert wird `Del` :</span><span class="sxs-lookup"><span data-stu-id="c1349-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

<span data-ttu-id="c1349-106">**Fehler-ID:** BC36532</span><span class="sxs-lookup"><span data-stu-id="c1349-106">**Error ID:** BC36532</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c1349-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c1349-107">To correct this error</span></span>

<span data-ttu-id="c1349-108">Passen Sie entweder die Delegatdefinition oder den zugewiesenen Lambda-Ausdruck so an, dass die Signaturen kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="c1349-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1349-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1349-109">See also</span></span>

- [<span data-ttu-id="c1349-110">Gelockerte Delegatenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="c1349-110">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="c1349-111">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="c1349-111">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
