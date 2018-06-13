---
title: 'Gewusst wie: Trefferüberprüfung mit einem Bereich'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 40297fada3d042aee8c317eb787de03662f86cfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523083"
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="ebc6c-102">Gewusst wie: Trefferüberprüfung mit einem Bereich</span><span class="sxs-lookup"><span data-stu-id="ebc6c-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="ebc6c-103">Treffertests dient zum bestimmen, ob der Cursor über einem angegebenen Objekt, z. B. ein Symbol oder eine Schaltfläche befindet.</span><span class="sxs-lookup"><span data-stu-id="ebc6c-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebc6c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebc6c-104">Example</span></span>  
 <span data-ttu-id="ebc6c-105">Das folgende Beispiel erstellt eine Region Plus geformten durch, die die Vereinigung der zwei rechteckige Bereiche bilden.</span><span class="sxs-lookup"><span data-stu-id="ebc6c-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="ebc6c-106">Vorausgesetzt, dass die Variable `point` enthält den Speicherort des letzten klicken.</span><span class="sxs-lookup"><span data-stu-id="ebc6c-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="ebc6c-107">Der Code überprüft, ob `point` in der Region Plus strukturiert ist.</span><span class="sxs-lookup"><span data-stu-id="ebc6c-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="ebc6c-108">Wenn der Punkt in der Region (Treffer) ist, wird der Bereich mit einem nicht transparenten Pinselfarbe gefüllt.</span><span class="sxs-lookup"><span data-stu-id="ebc6c-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="ebc6c-109">Andernfalls wird der Bereich mit einer halb transparenten Pinselfarbe gefüllt.</span><span class="sxs-lookup"><span data-stu-id="ebc6c-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ebc6c-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ebc6c-110">Compiling the Code</span></span>  
 <span data-ttu-id="ebc6c-111">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.</span><span class="sxs-lookup"><span data-stu-id="ebc6c-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc6c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebc6c-112">See Also</span></span>  
 <xref:System.Drawing.Region>  
 [<span data-ttu-id="ebc6c-113">Bereiche in GDI+</span><span class="sxs-lookup"><span data-stu-id="ebc6c-113">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [<span data-ttu-id="ebc6c-114">Gewusst wie: Ausschneiden mit einem Bereich</span><span class="sxs-lookup"><span data-stu-id="ebc6c-114">How to: Use Clipping with a Region</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)
