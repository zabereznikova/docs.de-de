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
ms.openlocfilehash: 7290b7901714e9b71bda3f85f930f5331b8fd4ab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077328"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="26f9a-102">Vorgehensweise: Anwenden der Gammakorrektur bei einem Farbverlauf</span><span class="sxs-lookup"><span data-stu-id="26f9a-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="26f9a-103">Sie können die Gammakorrektur für Pinsels mit linearem Farbverlauf aktivieren, durch Festlegen des Pinsels <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="26f9a-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="26f9a-104">Sie können die Gammakorrektur deaktivieren, indem die <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="26f9a-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="26f9a-105">Gammakorrektur ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="26f9a-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26f9a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26f9a-106">Example</span></span>  
 <span data-ttu-id="26f9a-107">Das Beispiel erstellt einen linearen Farbverlaufspinsel und verwendet diesen Pinsel, um zwei Rechtecke zu füllen.</span><span class="sxs-lookup"><span data-stu-id="26f9a-107">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="26f9a-108">Das erste Rechteck ohne Gammakorrektur gefüllt ist und das zweite Rechteck mit Gammakorrektur gefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="26f9a-108">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="26f9a-109">Die folgende Abbildung zeigt die beiden ausgefüllten Rechtecke.</span><span class="sxs-lookup"><span data-stu-id="26f9a-109">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="26f9a-110">Das oberste Rechteck, das Gammakorrektur nicht besitzt, wird in der Mitte dunkel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="26f9a-110">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="26f9a-111">Die unteren Rechteck, das Gammakorrektur, scheint gleichmäßige Intensität.</span><span class="sxs-lookup"><span data-stu-id="26f9a-111">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 <span data-ttu-id="26f9a-112">![Farbverlauf](./media/gammagradient1.png "gammagradient1")</span><span class="sxs-lookup"><span data-stu-id="26f9a-112">![Gradient](./media/gammagradient1.png "gammagradient1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="26f9a-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="26f9a-113">Compiling the Code</span></span>  
 <span data-ttu-id="26f9a-114">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="26f9a-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26f9a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26f9a-115">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush>
- [<span data-ttu-id="26f9a-116">Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="26f9a-116">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
