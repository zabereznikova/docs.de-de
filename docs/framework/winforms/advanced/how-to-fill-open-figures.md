---
title: 'Vorgehensweise: Füllen offener Körper aus'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: e9743d3268a7a2acfb6266872c3346a05269c369
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702724"
---
# <a name="how-to-fill-open-figures"></a><span data-ttu-id="6e9d5-102">Vorgehensweise: Füllen offener Körper aus</span><span class="sxs-lookup"><span data-stu-id="6e9d5-102">How to: Fill Open Figures</span></span>
<span data-ttu-id="6e9d5-103">Sie können einen Pfad eingeben, durch Übergeben einer <xref:System.Drawing.Drawing2D.GraphicsPath> -Objekt an die <xref:System.Drawing.Graphics.FillPath%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-103">You can fill a path by passing a <xref:System.Drawing.Drawing2D.GraphicsPath> object to the <xref:System.Drawing.Graphics.FillPath%2A> method.</span></span> <span data-ttu-id="6e9d5-104">Die <xref:System.Drawing.Graphics.FillPath%2A> Methode füllt den Pfad entsprechend der Füllmodus (alternative oder wicklungsreihenfolgen), die derzeit für den Pfad festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-104">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the fill mode (alternate or winding) currently set for the path.</span></span> <span data-ttu-id="6e9d5-105">Wenn der Pfad offener Körper enthält, wird der Pfad gefüllt, als ob diese Zahlen geschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-105">If the path has any open figures, the path is filled as if those figures were closed.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="6e9d5-106">Schließt eine Abbildung durch Zeichnen einer geraden Linie vom Endpunkt zum Ausgangspunkt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-106">closes a figure by drawing a straight line from its ending point to its starting point.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e9d5-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e9d5-107">Example</span></span>  
 <span data-ttu-id="6e9d5-108">Das folgende Beispiel erstellt einen Pfad an, der eine offene Form (einen Bogen) und eine geschlossene Form (eine Ellipse) verfügt.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-108">The following example creates a path that has one open figure (an arc) and one closed figure (an ellipse).</span></span> <span data-ttu-id="6e9d5-109">Die <xref:System.Drawing.Graphics.FillPath%2A> Methode füllt den Pfad entsprechend der Standardmodus für die Füllung, handelt es sich <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-109">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the default fill mode, which is <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span></span>  
  
 <span data-ttu-id="6e9d5-110">Die folgende Abbildung zeigt die Ausgabe des Beispielcodes.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-110">The following illustration shows the output of the example code.</span></span> <span data-ttu-id="6e9d5-111">Beachten Sie, dass der Pfad gefüllt wird (gemäß <xref:System.Drawing.Drawing2D.FillMode.Alternate>), als ob der geöffnete Figur mit einer geraden Linie vom Endpunkt zum Ausgangspunkt geschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-111">Note that the path is filled (according to <xref:System.Drawing.Drawing2D.FillMode.Alternate>) as if the open figure were closed by a straight line from its ending point to its starting point.</span></span>  
  
 <span data-ttu-id="6e9d5-112">![Offenen Pfad ausfüllen](./media/fillopenpath.png "FillOpenPath")</span><span class="sxs-lookup"><span data-stu-id="6e9d5-112">![Fill Open Path](./media/fillopenpath.png "FillOpenPath")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6e9d5-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6e9d5-113">Compiling the Code</span></span>  
 <span data-ttu-id="6e9d5-114">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e9d5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e9d5-115">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="6e9d5-116">Grafikpfade in GDI+</span><span class="sxs-lookup"><span data-stu-id="6e9d5-116">Graphics Paths in GDI+</span></span>](graphics-paths-in-gdi.md)
