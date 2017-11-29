---
title: "Überlauf (Visual Basic-Laufzeitfehler)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1908ad576a499e79102aff23e3e2f11d7d99d52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="332ce-102">Überlauf (Visual Basic-Laufzeitfehler)</span><span class="sxs-lookup"><span data-stu-id="332ce-102">Overflow (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="332ce-103">Ein Überlauf tritt beim Versuch, einer Zuordnung, die die Grenzen eines Ziels für die Zuweisung überschreitet.</span><span class="sxs-lookup"><span data-stu-id="332ce-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="332ce-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="332ce-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="332ce-105">Stellen Sie sicher, dass die Ergebnisse der Zuweisungen, Berechnungen und den Datentyp Konvertierungen sind nicht zu groß, um innerhalb des Bereichs von Variablen, die für diesen Typ des Werts zulässig dargestellt werden, und weisen Sie den Wert einer Variablen eines Typs, die eine größere Anzahl von Werten enthalten kann , falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="332ce-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2.  <span data-ttu-id="332ce-106">Stellen Sie sicher, dass Zuweisungen zu Eigenschaften des Bereichs der Eigenschaft entsprechen, zu dem sie bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="332ce-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3.  <span data-ttu-id="332ce-107">Stellen Sie sicher, dass die Zahlen in Berechnungen, die in Zahlen umgewandelt werden keine Ergebnisse, die größer als ganze Zahlen.</span><span class="sxs-lookup"><span data-stu-id="332ce-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="332ce-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="332ce-108">See Also</span></span>  
 <xref:System.Int32.MaxValue?displayProperty=nameWithType>  
 <xref:System.Double.MaxValue?displayProperty=nameWithType>  
 [<span data-ttu-id="332ce-109">Datentypen</span><span class="sxs-lookup"><span data-stu-id="332ce-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="332ce-110">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="332ce-110">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
