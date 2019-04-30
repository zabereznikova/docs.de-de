---
title: Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 9f7f878649d8b96f050b56d5b878eb3d67e027ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918221"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="fad81-102">Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="fad81-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="fad81-103">Werttypen und Strukturen können auf NULL festlegbare deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="fad81-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="fad81-104">Sie können nicht jedoch die NULL-Werte zulassen Deklaration in Kombination mit den Typrückschluss verwenden.</span><span class="sxs-lookup"><span data-stu-id="fad81-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="fad81-105">In den folgenden Beispielen werden diese Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="fad81-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="fad81-106">**Fehler-ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="fad81-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fad81-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fad81-107">To correct this error</span></span>  
  
- <span data-ttu-id="fad81-108">Verwenden einer `As` -Klausel, um die Variable als auf NULL festlegbar deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="fad81-108">Use an `As` clause to declare the variable as nullable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad81-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fad81-109">See also</span></span>

- [<span data-ttu-id="fad81-110">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="fad81-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="fad81-111">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="fad81-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
