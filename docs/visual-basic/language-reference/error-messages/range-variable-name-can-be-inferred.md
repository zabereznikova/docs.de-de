---
title: Der Name einer Bereichsvariablen kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: 63990b7d37388057ff2cdb430d29878a1c7b39ba
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162361"
---
# <a name="bc36599-range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="2ca3e-102">BC36599: der Name der Bereichs Variablen kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="2ca3e-102">BC36599: Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>

<span data-ttu-id="2ca3e-103">Ein Programmier Element, das ein oder mehrere Argumente annimmt, ist in einer LINQ-Abfrage enthalten.</span><span class="sxs-lookup"><span data-stu-id="2ca3e-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="2ca3e-104">Der Compiler kann keine Bereichs Variable von diesem Programmier Element ableiten.</span><span class="sxs-lookup"><span data-stu-id="2ca3e-104">The compiler is unable to infer a range variable from that programming element.</span></span>

<span data-ttu-id="2ca3e-105">**Fehler-ID:** BC36599</span><span class="sxs-lookup"><span data-stu-id="2ca3e-105">**Error ID:** BC36599</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="2ca3e-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="2ca3e-106">To correct this error</span></span>

<span data-ttu-id="2ca3e-107">Geben Sie für das Programmier Element einen expliziten Variablennamen an, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2ca3e-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>

```vb
Dim query = From var1 In collection1
            Select VariableAlias= SampleFunction(var1), var1
```

## <a name="see-also"></a><span data-ttu-id="2ca3e-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ca3e-108">See also</span></span>

- [<span data-ttu-id="2ca3e-109">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2ca3e-109">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="2ca3e-110">SELECT-Klausel</span><span class="sxs-lookup"><span data-stu-id="2ca3e-110">Select Clause</span></span>](../queries/select-clause.md)
