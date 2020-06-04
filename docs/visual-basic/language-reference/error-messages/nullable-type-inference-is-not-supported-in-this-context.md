---
title: Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 52e5391fbcf30a4dada4d64a0e810c900ea85806
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409386"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="eced7-102">Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="eced7-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="eced7-103">Werttypen und Strukturen können als Nullable deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="eced7-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="eced7-104">Es ist jedoch nicht möglich, die Deklaration, die NULL zulässt, in Kombination mit dem Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="eced7-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="eced7-105">In den folgenden Beispielen wird dieser Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="eced7-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="eced7-106">**Fehler-ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="eced7-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eced7-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="eced7-107">To correct this error</span></span>  
  
- <span data-ttu-id="eced7-108">Verwenden Sie eine- `As` Klausel, um die Variable als Werte zulässt-Werttyp zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="eced7-108">Use an `As` clause to declare the variable as a nullable value type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eced7-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eced7-109">See also</span></span>

- [<span data-ttu-id="eced7-110">Nullable-Werttypen</span><span class="sxs-lookup"><span data-stu-id="eced7-110">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="eced7-111">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="eced7-111">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
