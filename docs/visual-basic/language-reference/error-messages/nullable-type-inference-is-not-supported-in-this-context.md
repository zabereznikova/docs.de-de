---
title: Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 610d2dc427d882c412b87eb67f021a8a86025f25
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159925"
---
# <a name="bc36629-nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="55988-102">BC36629: der Typrückschluss, der NULL zulässt, wird in diesem Kontext nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="55988-102">BC36629: Nullable type inference is not supported in this context</span></span>

<span data-ttu-id="55988-103">Werttypen und Strukturen können als Nullable deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="55988-103">Value types and structures can be declared nullable.</span></span>

```vb
Dim a? As Integer
Dim b As Integer?
```

 <span data-ttu-id="55988-104">Es ist jedoch nicht möglich, die Deklaration, die NULL zulässt, in Kombination mit dem Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="55988-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="55988-105">In den folgenden Beispielen wird dieser Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="55988-105">The following examples cause this error.</span></span>

```vb
' Not valid.
' Dim c? = 10
' Dim d? = a
```

 <span data-ttu-id="55988-106">**Fehler-ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="55988-106">**Error ID:** BC36629</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="55988-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="55988-107">To correct this error</span></span>

- <span data-ttu-id="55988-108">Verwenden Sie eine- `As` Klausel, um die Variable als Werte zulässt-Werttyp zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="55988-108">Use an `As` clause to declare the variable as a nullable value type.</span></span>

## <a name="see-also"></a><span data-ttu-id="55988-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55988-109">See also</span></span>

- [<span data-ttu-id="55988-110">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="55988-110">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="55988-111">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="55988-111">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
