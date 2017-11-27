---
title: 'Gewusst wie: Zeichnen mit nicht transparenten und halb transparenten Pinseln'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- semi-transparent shapes [Windows Forms], drawing
- transparency [Windows Forms], semi-transparent shapes
- alpha blending [Windows Forms], brush
- brushes [Windows Forms], using semi-transparent
ms.assetid: a4f6f6b8-3bc8-440a-84af-d62ef0f8ff40
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4af2664851ed0903a362a4b88edf1db9bb042dfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-with-opaque-and-semitransparent-brushes"></a><span data-ttu-id="0930d-102">Gewusst wie: Zeichnen mit nicht transparenten und halb transparenten Pinseln</span><span class="sxs-lookup"><span data-stu-id="0930d-102">How to: Draw with Opaque and Semitransparent Brushes</span></span>
<span data-ttu-id="0930d-103">Wenn Sie eine Form ausfüllen, müssen Sie ein <xref:System.Drawing.Brush>-Objekt an eine der Füllmethoden der <xref:System.Drawing.Graphics>-Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="0930d-103">When you fill a shape, you must pass a <xref:System.Drawing.Brush> object to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="0930d-104">Der einzige Parameter des <xref:System.Drawing.SolidBrush.%23ctor%2A>-Konstruktors ist ein <xref:System.Drawing.Color>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="0930d-104">The one parameter of the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="0930d-105">Um eine nicht transparente Form auszufüllen, legen Sie den Alphaanteil der Farbe auf 255 fest.</span><span class="sxs-lookup"><span data-stu-id="0930d-105">To fill an opaque shape, set the alpha component of the color to 255.</span></span> <span data-ttu-id="0930d-106">Um eine halb transparente Form auszufüllen, legen Sie den Alphaanteil auf einen beliebigen Wert von 1 bis 254 fest.</span><span class="sxs-lookup"><span data-stu-id="0930d-106">To fill a semitransparent shape, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="0930d-107">Wenn Sie eine halb transparente Form ausfüllen, wird die Farbe der Form mit den Hintergrundfarben gemischt.</span><span class="sxs-lookup"><span data-stu-id="0930d-107">When you fill a semitransparent shape, the color of the shape is blended with the colors of the background.</span></span> <span data-ttu-id="0930d-108">Mit dem Alphaanteil wird das Mischungsverhältnis zwischen Form- und Hintergrundfarben angegeben. Bei Alphawerten nahe 0 werden die Hintergrundfarben höher gewichtet, und bei Alphawerten nahe 255 wird die Formfarbe höher gewichtet.</span><span class="sxs-lookup"><span data-stu-id="0930d-108">The alpha component specifies how the shape and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the shape color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0930d-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0930d-109">Example</span></span>  
 <span data-ttu-id="0930d-110">Im folgenden Beispiel wird erst eine Bitmap gezeichnet, und anschließend werden drei Ellipsen ausgefüllt, die die Bitmap überlappen</span><span class="sxs-lookup"><span data-stu-id="0930d-110">The following example draws a bitmap and then fills three ellipses that overlap the bitmap.</span></span> <span data-ttu-id="0930d-111">Für die erste Ellipse wird ein Alphaanteil von 255 verwendet. Die Ellipse ist daher nicht transparent.</span><span class="sxs-lookup"><span data-stu-id="0930d-111">The first ellipse uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="0930d-112">Die zweite und die dritte Ellipse verwenden einen Alphaanteil von 128. Sie sind daher halb transparent. Das Hintergrundbild scheint also durch die Ellipsen hindurch.</span><span class="sxs-lookup"><span data-stu-id="0930d-112">The second and third ellipses use an alpha component of 128, so they are semitransparent; you can see the background image through the ellipses.</span></span> <span data-ttu-id="0930d-113">Der Aufruf, mit dem die <xref:System.Drawing.Graphics.CompositingQuality%2A>-Eigenschaft festgelegt wird, sorgt dafür, dass die Mischung für die dritte Ellipse unter Verwendung der Gammakorrektur erfolgt.</span><span class="sxs-lookup"><span data-stu-id="0930d-113">The call that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third ellipse to be done in conjunction with gamma correction.</span></span>  
  
 <span data-ttu-id="0930d-114">In der folgenden Abbildung ist das Ergebnis des angegebenen Codes dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0930d-114">The following illustration shows the output of the following code.</span></span>  
  
 <span data-ttu-id="0930d-115">![Deckend und halb transparent](../../../../docs/framework/winforms/advanced/media/compqualellipse.png "Compqualellipse")</span><span class="sxs-lookup"><span data-stu-id="0930d-115">![Opaque and Semitransparent](../../../../docs/framework/winforms/advanced/media/compqualellipse.png "compqualellipse")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.AlphaBlending#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0930d-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0930d-116">Compiling the Code</span></span>  
 <span data-ttu-id="0930d-117">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs>`e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.</span><span class="sxs-lookup"><span data-stu-id="0930d-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0930d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0930d-118">See Also</span></span>  
 [<span data-ttu-id="0930d-119">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0930d-119">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="0930d-120">Alphablending von Linien und Füllungen</span><span class="sxs-lookup"><span data-stu-id="0930d-120">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 [<span data-ttu-id="0930d-121">Gewusst wie: Verwenden eines transparenten Hintergrunds für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0930d-121">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 [<span data-ttu-id="0930d-122">Gewusst wie: Zeichnen deckender und halbtransparenter Linien</span><span class="sxs-lookup"><span data-stu-id="0930d-122">How to: Draw Opaque and Semitransparent Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)
