---
title: Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: ea531c7be676e940a263b019a66cc80cf280a772
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593190"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="cd31c-102">Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="cd31c-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="cd31c-103">Werttypen und Strukturen können NULL-Werte zulassen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="cd31c-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="cd31c-104">Sie können nicht jedoch auf NULL festlegbare Deklaration in Kombination mit den Typrückschluss verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd31c-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="cd31c-105">In den folgenden Beispielen wird dieser Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="cd31c-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="cd31c-106">**Fehler-ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="cd31c-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cd31c-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="cd31c-107">To correct this error</span></span>  
  
-   <span data-ttu-id="cd31c-108">Verwenden einer `As` -Klausel, um die Variable als auf NULL festlegbar deklariert.</span><span class="sxs-lookup"><span data-stu-id="cd31c-108">Use an `As` clause to declare the variable as nullable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd31c-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd31c-109">See Also</span></span>  
 [<span data-ttu-id="cd31c-110">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="cd31c-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="cd31c-111">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="cd31c-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
