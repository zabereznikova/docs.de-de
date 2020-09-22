---
title: Überlauf (Visual Basic-Laufzeitfehler)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: e287d6c24eca75d8bf20181a201056f467d6fc4e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871221"
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="7f1ef-102">Überlauf (Visual Basic-Laufzeitfehler)</span><span class="sxs-lookup"><span data-stu-id="7f1ef-102">Overflow (Visual Basic Run-Time Error)</span></span>

<span data-ttu-id="7f1ef-103">Ein Überlauf Ergebnis, wenn Sie versuchen, eine Zuweisung durchführen, die die Grenzwerte für das Ziel der Zuweisung überschreitet.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7f1ef-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="7f1ef-104">To correct this error</span></span>  
  
1. <span data-ttu-id="7f1ef-105">Stellen Sie sicher, dass die Ergebnisse von Zuweisungen, Berechnungen und Datentyp Konvertierungen nicht zu groß sind, um innerhalb des Bereichs von Variablen, die für diesen Werttyp zulässig sind, dargestellt zu werden, und weisen Sie den Wert einer Variablen eines Typs zu, die ggf. einen größeren Wertebereich enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2. <span data-ttu-id="7f1ef-106">Stellen Sie sicher, dass die Zuweisungen von Eigenschaften dem Bereich der Eigenschaft entsprechen, an der Sie vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3. <span data-ttu-id="7f1ef-107">Stellen Sie sicher, dass die Zahlen, die in Berechnungen verwendet werden, die in ganze Zahlen umgewandelt werden, keine Ergebnisse aufweisen, die größer als ganze Zahlen sind.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f1ef-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f1ef-108">See also</span></span>

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [<span data-ttu-id="7f1ef-109">Datentypen</span><span class="sxs-lookup"><span data-stu-id="7f1ef-109">Data Types</span></span>](../data-types/index.md)
- [<span data-ttu-id="7f1ef-110">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="7f1ef-110">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
