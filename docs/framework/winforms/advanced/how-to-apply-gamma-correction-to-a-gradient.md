---
title: 'Vorgehensweise: Anwenden der Gammakorrektur bei einem Farbverlauf'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: e812e441233c1d29a67dac639048e20a659549f0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753568"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="9b4ab-102">Vorgehensweise: Anwenden der Gammakorrektur bei einem Farbverlauf</span><span class="sxs-lookup"><span data-stu-id="9b4ab-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="9b4ab-103">Sie können die Gammakorrektur für Pinsels mit linearem Farbverlauf aktivieren, durch Festlegen des Pinsels <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="9b4ab-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="9b4ab-104">Sie können die Gammakorrektur deaktivieren, indem die <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="9b4ab-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="9b4ab-105">Gammakorrektur ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9b4ab-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b4ab-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b4ab-106">Example</span></span>  

<span data-ttu-id="9b4ab-107">Im folgende Beispiel wird eine Methode, die von eines Steuerelements aufgerufen wird <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="9b4ab-107">The following example is a method that is called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="9b4ab-108">Das Beispiel erstellt einen linearen Farbverlaufspinsel und verwendet diesen Pinsel, um zwei Rechtecke zu füllen.</span><span class="sxs-lookup"><span data-stu-id="9b4ab-108">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="9b4ab-109">Das erste Rechteck ohne Gammakorrektur gefüllt ist und das zweite Rechteck mit Gammakorrektur gefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="9b4ab-109">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="9b4ab-110">Die folgende Abbildung zeigt die beiden ausgefüllten Rechtecke.</span><span class="sxs-lookup"><span data-stu-id="9b4ab-110">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="9b4ab-111">Das oberste Rechteck, das Gammakorrektur nicht besitzt, wird in der Mitte dunkel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9b4ab-111">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="9b4ab-112">Die unteren Rechteck, das Gammakorrektur, scheint gleichmäßige Intensität.</span><span class="sxs-lookup"><span data-stu-id="9b4ab-112">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 ![Zwei Verläufen Rechtecke, mit und ohne die Gammakorrektur.](./media/how-to-apply-gamma-correction-to-a-gradient/two-rectangles-gamma-gradient.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9b4ab-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9b4ab-114">Compiling the Code</span></span>  
 <span data-ttu-id="9b4ab-115">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="9b4ab-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b4ab-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b4ab-116">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="9b4ab-117">Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="9b4ab-117">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
