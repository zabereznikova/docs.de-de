---
title: 'Gewusst wie: Erstellen von vertikalem Text'
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
ms.openlocfilehash: 86401342625f593945b801f7619ef9ca9681317c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182559"
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="15e5b-102">Gewusst wie: Erstellen von vertikalem Text</span><span class="sxs-lookup"><span data-stu-id="15e5b-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="15e5b-103">Sie können <xref:System.Drawing.StringFormat> ein Objekt verwenden, um anzugeben, dass Text vertikal statt horizontal gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="15e5b-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15e5b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="15e5b-104">Example</span></span>  
 <span data-ttu-id="15e5b-105">Im folgenden Beispiel wird <xref:System.Drawing.StringFormatFlags.DirectionVertical> der <xref:System.Drawing.StringFormat.FormatFlags%2A> Wert <xref:System.Drawing.StringFormat> der Eigenschaft eines Objekts zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="15e5b-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="15e5b-106">Dieses <xref:System.Drawing.StringFormat> Objekt wird <xref:System.Drawing.Graphics.DrawString%2A> an die <xref:System.Drawing.Graphics> Methode der Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="15e5b-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="15e5b-107">Der <xref:System.Drawing.StringFormatFlags.DirectionVertical> Wert ist ein <xref:System.Drawing.StringFormatFlags> Member der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="15e5b-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="15e5b-108">Die folgende Abbildung zeigt den vertikalen Text:</span><span class="sxs-lookup"><span data-stu-id="15e5b-108">The following illustration shows the vertical text:</span></span>
  
 ![Grafik, die vertikalen Schrifttext anzeigt.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="15e5b-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="15e5b-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="15e5b-111">Das obige Beispiel ist für die Verwendung <xref:System.Windows.Forms.PaintEventArgs> `e` mit Windows Forms <xref:System.Windows.Forms.PaintEventHandler>konzipiert und erfordert , was ein Parameter von ist.</span><span class="sxs-lookup"><span data-stu-id="15e5b-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15e5b-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15e5b-112">See also</span></span>

- [<span data-ttu-id="15e5b-113">Gewusst wie: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="15e5b-113">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
