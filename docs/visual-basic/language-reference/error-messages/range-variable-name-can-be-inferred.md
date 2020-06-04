---
title: Der Name einer Bereichsvariablen kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: d6b155de0bb62f667ca76ec9454dec1466976a9b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400408"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="bcb19-102">Der Name einer Bereichsvariablen kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden</span><span class="sxs-lookup"><span data-stu-id="bcb19-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>

<span data-ttu-id="bcb19-103">Ein Programmier Element, das ein oder mehrere Argumente annimmt, ist in einer LINQ-Abfrage enthalten.</span><span class="sxs-lookup"><span data-stu-id="bcb19-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="bcb19-104">Der Compiler kann keine Bereichs Variable von diesem Programmier Element ableiten.</span><span class="sxs-lookup"><span data-stu-id="bcb19-104">The compiler is unable to infer a range variable from that programming element.</span></span>

<span data-ttu-id="bcb19-105">**Fehler-ID:** BC36599</span><span class="sxs-lookup"><span data-stu-id="bcb19-105">**Error ID:** BC36599</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="bcb19-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="bcb19-106">To correct this error</span></span>

<span data-ttu-id="bcb19-107">Geben Sie für das Programmier Element einen expliziten Variablennamen an, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="bcb19-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>

```vb
Dim query = From var1 In collection1
            Select VariableAlias= SampleFunction(var1), var1
```

## <a name="see-also"></a><span data-ttu-id="bcb19-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bcb19-108">See also</span></span>

- [<span data-ttu-id="bcb19-109">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bcb19-109">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="bcb19-110">SELECT-Klausel</span><span class="sxs-lookup"><span data-stu-id="bcb19-110">Select Clause</span></span>](../queries/select-clause.md)
