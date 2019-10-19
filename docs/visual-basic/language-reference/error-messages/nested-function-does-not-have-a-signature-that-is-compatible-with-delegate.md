---
title: Die geschachtelte Funktion verfügt über keine Signatur, die mit dem Delegaten '<delegatename>' kompatibel ist
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: d65c8eab661675c955ff6562098248c04036d6e7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72580648"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="5b64a-102">Die in der Funktion für die Funktion mit dem Delegaten "\<delegatename >" kompatible Signatur ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5b64a-102">Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>

<span data-ttu-id="5b64a-103">Ein Lambda-Ausdruck wurde einem Delegaten zugewiesen, der über eine inkompatible Signatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="5b64a-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="5b64a-104">Im folgenden Code verfügt der Delegat `Del` z. b. über zwei ganzzahlige Parameter.</span><span class="sxs-lookup"><span data-stu-id="5b64a-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

<span data-ttu-id="5b64a-105">Der Fehler wird ausgelöst, wenn ein Lambda-Ausdruck mit einem Argument als Typ `Del` deklariert ist:</span><span class="sxs-lookup"><span data-stu-id="5b64a-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

<span data-ttu-id="5b64a-106">**Fehler-ID:** BC36532</span><span class="sxs-lookup"><span data-stu-id="5b64a-106">**Error ID:** BC36532</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="5b64a-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5b64a-107">To correct this error</span></span>

<span data-ttu-id="5b64a-108">Passen Sie entweder die Delegatdefinition oder den zugewiesenen Lambda-Ausdruck so an, dass die Signaturen kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="5b64a-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b64a-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b64a-109">See also</span></span>

- [<span data-ttu-id="5b64a-110">Gelockerte Delegatenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="5b64a-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="5b64a-111">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="5b64a-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
