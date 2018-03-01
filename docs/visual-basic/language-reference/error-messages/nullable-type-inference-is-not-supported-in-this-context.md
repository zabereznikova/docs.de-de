---
title: "Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e7a5450d812260d3916296dff56abee27b3d586c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="652d8-102">Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="652d8-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="652d8-103">Werttypen und Strukturen können NULL-Werte zulassen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="652d8-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="652d8-104">Sie können nicht jedoch auf NULL festlegbare Deklaration in Kombination mit den Typrückschluss verwenden.</span><span class="sxs-lookup"><span data-stu-id="652d8-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="652d8-105">In den folgenden Beispielen wird dieser Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="652d8-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="652d8-106">**Fehler-ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="652d8-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="652d8-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="652d8-107">To correct this error</span></span>  
  
-   <span data-ttu-id="652d8-108">Verwenden einer `As` -Klausel, um die Variable als auf NULL festlegbar deklariert.</span><span class="sxs-lookup"><span data-stu-id="652d8-108">Use an `As` clause to declare the variable as nullable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="652d8-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="652d8-109">See Also</span></span>  
 [<span data-ttu-id="652d8-110">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="652d8-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="652d8-111">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="652d8-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
