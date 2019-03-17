---
title: 'Vorgehensweise: Erstellen von vertikalem Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: 720e343f1b3b20fe3df96a03fbd67ee473ec13f6
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2019
ms.locfileid: "58125407"
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="aed3d-102">Vorgehensweise: Erstellen von vertikalem Text</span><span class="sxs-lookup"><span data-stu-id="aed3d-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="aed3d-103">Sie können eine <xref:System.Drawing.StringFormat> Objekt, um anzugeben, dass der Text vertikal oder horizontal gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="aed3d-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aed3d-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aed3d-104">Example</span></span>  
 <span data-ttu-id="aed3d-105">Im folgende Beispiel weist den Wert <xref:System.Drawing.StringFormatFlags.DirectionVertical> auf die <xref:System.Drawing.StringFormat.FormatFlags%2A> Eigenschaft eine <xref:System.Drawing.StringFormat> Objekt.</span><span class="sxs-lookup"><span data-stu-id="aed3d-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="aed3d-106">Dass <xref:System.Drawing.StringFormat> Objekt wird zum Übergeben der <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="aed3d-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="aed3d-107">Der Wert <xref:System.Drawing.StringFormatFlags.DirectionVertical> ist ein Mitglied der <xref:System.Drawing.StringFormatFlags> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="aed3d-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="aed3d-108">Die folgende Abbildung zeigt den vertikalen Text an:</span><span class="sxs-lookup"><span data-stu-id="aed3d-108">The following illustration shows the vertical text:</span></span> 
  
 ![Grafik, die-Schriftart Text zeigt.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="aed3d-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="aed3d-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="aed3d-111">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e` , d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="aed3d-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aed3d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aed3d-112">See also</span></span>
- [<span data-ttu-id="aed3d-113">Vorgehensweise: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="aed3d-113">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
