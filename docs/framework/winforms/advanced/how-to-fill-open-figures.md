---
title: 'Gewusst wie: Ausfüllen offener Körper'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: b7422ae2a4dc4d59fd337ab2294caa0d65057bae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521159"
---
# <a name="how-to-fill-open-figures"></a><span data-ttu-id="09f89-102">Gewusst wie: Ausfüllen offener Körper</span><span class="sxs-lookup"><span data-stu-id="09f89-102">How to: Fill Open Figures</span></span>
<span data-ttu-id="09f89-103">Sie können einen Pfad ausfüllen, durch das Übergeben einer <xref:System.Drawing.Drawing2D.GraphicsPath> -Objekt an die <xref:System.Drawing.Graphics.FillPath%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="09f89-103">You can fill a path by passing a <xref:System.Drawing.Drawing2D.GraphicsPath> object to the <xref:System.Drawing.Graphics.FillPath%2A> method.</span></span> <span data-ttu-id="09f89-104">Die <xref:System.Drawing.Graphics.FillPath%2A> -Methode füllt den Pfad entsprechend der Füllmodus (alternate oder winding), die derzeit für den Pfad festlegen.</span><span class="sxs-lookup"><span data-stu-id="09f89-104">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the fill mode (alternate or winding) currently set for the path.</span></span> <span data-ttu-id="09f89-105">Wenn der Pfad offener Körper verfügt, wird der Pfad gefüllt, als ob diese Zahlen geschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="09f89-105">If the path has any open figures, the path is filled as if those figures were closed.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="09f89-106"> Schließt eine Abbildung durch Zeichnen einer geraden Linie vom Endpunkt an seinem Ausgangspunkt.</span><span class="sxs-lookup"><span data-stu-id="09f89-106"> closes a figure by drawing a straight line from its ending point to its starting point.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09f89-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="09f89-107">Example</span></span>  
 <span data-ttu-id="09f89-108">Das folgende Beispiel erstellt einen Pfad mit einer offenen Figur (einen Bogen) und eine geschlossene Form (Ellipse).</span><span class="sxs-lookup"><span data-stu-id="09f89-108">The following example creates a path that has one open figure (an arc) and one closed figure (an ellipse).</span></span> <span data-ttu-id="09f89-109">Die <xref:System.Drawing.Graphics.FillPath%2A> -Methode füllt den Pfad entsprechend der Standardmodus für die Füllung, also <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span><span class="sxs-lookup"><span data-stu-id="09f89-109">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the default fill mode, which is <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span></span>  
  
 <span data-ttu-id="09f89-110">Die folgende Abbildung zeigt die Ausgabe des Beispielcodes.</span><span class="sxs-lookup"><span data-stu-id="09f89-110">The following illustration shows the output of the example code.</span></span> <span data-ttu-id="09f89-111">Beachten Sie, dass der Pfad ist gefüllt (gemäß <xref:System.Drawing.Drawing2D.FillMode.Alternate>), als wäre der offene Körper durch eine gerade Linie vom Endpunkt an seinem Ausgangspunkt geschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="09f89-111">Note that the path is filled (according to <xref:System.Drawing.Drawing2D.FillMode.Alternate>) as if the open figure were closed by a straight line from its ending point to its starting point.</span></span>  
  
 <span data-ttu-id="09f89-112">![Offenen Pfad ausfüllen](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")</span><span class="sxs-lookup"><span data-stu-id="09f89-112">![Fill Open Path](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="09f89-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="09f89-113">Compiling the Code</span></span>  
 <span data-ttu-id="09f89-114">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="09f89-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09f89-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09f89-115">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [<span data-ttu-id="09f89-116">Grafikpfade in GDI+</span><span class="sxs-lookup"><span data-stu-id="09f89-116">Graphics Paths in GDI+</span></span>](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)
