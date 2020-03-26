---
title: Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 42bde0b1843e52bbc16118bb056ade791591904e
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249499"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="04d98-102">Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="04d98-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="04d98-103">Werttypen und -strukturen können als null deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="04d98-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="04d98-104">Sie können die nullfähige Deklaration jedoch nicht in Kombination mit dem Typrückschluss verwenden.</span><span class="sxs-lookup"><span data-stu-id="04d98-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="04d98-105">Die folgenden Beispiele verursachen diesen Fehler.</span><span class="sxs-lookup"><span data-stu-id="04d98-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="04d98-106">**Fehler-ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="04d98-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="04d98-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="04d98-107">To correct this error</span></span>  
  
- <span data-ttu-id="04d98-108">Verwenden `As` Sie eine Klausel, um die Variable als NULL-Werttyp zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="04d98-108">Use an `As` clause to declare the variable as a nullable value type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d98-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04d98-109">See also</span></span>

- [<span data-ttu-id="04d98-110">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="04d98-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="04d98-111">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="04d98-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
