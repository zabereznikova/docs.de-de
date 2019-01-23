---
title: 'Vorgehensweise: Trefferüberprüfung mit einem Bereich'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 1866810b875063271e206da1fe5d6fc06f7b5de0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564304"
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="c6c4e-102">Vorgehensweise: Trefferüberprüfung mit einem Bereich</span><span class="sxs-lookup"><span data-stu-id="c6c4e-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="c6c4e-103">Für den Treffertest dient zu bestimmen, ob der Cursor über ein bestimmtes Objekt, z. B. ein Symbol oder eine Schaltfläche befindet.</span><span class="sxs-lookup"><span data-stu-id="c6c4e-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6c4e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c6c4e-104">Example</span></span>  
 <span data-ttu-id="c6c4e-105">Das folgende Beispiel erstellt eine Region Plus gestalteten durch, die die Union der zwei rechteckige Bereiche bilden.</span><span class="sxs-lookup"><span data-stu-id="c6c4e-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="c6c4e-106">Vorausgesetzt, dass die Variable `point` enthält den Speicherort aus, klicken Sie im letzten.</span><span class="sxs-lookup"><span data-stu-id="c6c4e-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="c6c4e-107">Der Code prüft, ob `point` ist in der Region Pluszeichen bildet.</span><span class="sxs-lookup"><span data-stu-id="c6c4e-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="c6c4e-108">Wenn der Punkt in der Region (ein Treffer) ist, wird der Bereich mit einem roten transparenten Pinsel gefüllt.</span><span class="sxs-lookup"><span data-stu-id="c6c4e-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="c6c4e-109">Andernfalls wird der Bereich mit einem roten halb transparenten Pinsel gefüllt.</span><span class="sxs-lookup"><span data-stu-id="c6c4e-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c6c4e-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c6c4e-110">Compiling the Code</span></span>  
 <span data-ttu-id="c6c4e-111">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.</span><span class="sxs-lookup"><span data-stu-id="c6c4e-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c4e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6c4e-112">See also</span></span>
- <xref:System.Drawing.Region>
- [<span data-ttu-id="c6c4e-113">Bereiche in GDI+</span><span class="sxs-lookup"><span data-stu-id="c6c4e-113">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)
- [<span data-ttu-id="c6c4e-114">Vorgehensweise: Verwenden von Clipping mit einer Region</span><span class="sxs-lookup"><span data-stu-id="c6c4e-114">How to: Use Clipping with a Region</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)
