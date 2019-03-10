---
title: 'Vorgehensweise: Verwenden des Mischmodus zum Steuern des Alphablendings'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 1b6ff14de7ff524b8af603ae5fa3969d5230b1a7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714124"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a><span data-ttu-id="bcb47-102">Vorgehensweise: Verwenden des Mischmodus zum Steuern des Alphablendings</span><span class="sxs-lookup"><span data-stu-id="bcb47-102">How to: Use Compositing Mode to Control Alpha Blending</span></span>
<span data-ttu-id="bcb47-103">Möglicherweise gibt es Situationen, eine Offscreen-Bitmap zu erstellen, die die folgenden Eigenschaften besitzt:</span><span class="sxs-lookup"><span data-stu-id="bcb47-103">There may be times when you want to create an off-screen bitmap that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="bcb47-104">Farben haben alpha-Werte, die kleiner als 255 sind.</span><span class="sxs-lookup"><span data-stu-id="bcb47-104">Colors have alpha values that are less than 255.</span></span>  
  
-   <span data-ttu-id="bcb47-105">Farben sind nicht alpha miteinander kombiniert werden, wie Sie die Bitmap zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bcb47-105">Colors are not alpha blended with each other as you create the bitmap.</span></span>  
  
-   <span data-ttu-id="bcb47-106">Wenn Sie die fertige Bitmap angezeigt wird, sind die Farben in der Bitmap Alphablending mit den Hintergrundfarben, auf dem Anzeigegerät.</span><span class="sxs-lookup"><span data-stu-id="bcb47-106">When you display the finished bitmap, colors in the bitmap are alpha blended with the background colors on the display device.</span></span>  
  
 <span data-ttu-id="bcb47-107">Um eine solche Bitmap zu erstellen, erstellen Sie ein leeres <xref:System.Drawing.Bitmap> Objekt an, und erstellen dann eine <xref:System.Drawing.Graphics> -Objekt auf Grundlage dieser Bitmap.</span><span class="sxs-lookup"><span data-stu-id="bcb47-107">To create such a bitmap, construct a blank <xref:System.Drawing.Bitmap> object, and then construct a <xref:System.Drawing.Graphics> object based on that bitmap.</span></span> <span data-ttu-id="bcb47-108">Legen Sie den Modus zusammensetzt, von der <xref:System.Drawing.Graphics> -Objekt <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bcb47-108">Set the compositing mode of the <xref:System.Drawing.Graphics> object to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcb47-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bcb47-109">Example</span></span>  
 <span data-ttu-id="bcb47-110">Das folgende Beispiel erstellt eine <xref:System.Drawing.Graphics> Objekt auf Grundlage einer <xref:System.Drawing.Bitmap> Objekt.</span><span class="sxs-lookup"><span data-stu-id="bcb47-110">The following example creates a <xref:System.Drawing.Graphics> object based on a <xref:System.Drawing.Bitmap> object.</span></span> <span data-ttu-id="bcb47-111">Der Code verwendet die <xref:System.Drawing.Graphics> Objekt zusammen mit zwei halb transparenten Pinseln (Alpha = 160) auf die Bitmap gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bcb47-111">The code uses the <xref:System.Drawing.Graphics> object along with two semitransparent brushes (alpha = 160) to paint on the bitmap.</span></span> <span data-ttu-id="bcb47-112">Der Code füllt eine rote und einer grünen Ellipse mit der halb transparenten Pinseln.</span><span class="sxs-lookup"><span data-stu-id="bcb47-112">The code fills a red ellipse and a green ellipse using the semitransparent brushes.</span></span> <span data-ttu-id="bcb47-113">Die grüne Ellipse überschneidet sich mit der roten Ellipse, aber die grüne wird nicht mit dem roten gemischt, da die Mischmodus von der <xref:System.Drawing.Graphics> Objekt nastaven NA hodnotu <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span><span class="sxs-lookup"><span data-stu-id="bcb47-113">The green ellipse overlaps the red ellipse, but the green is not blended with the red because the compositing mode of the <xref:System.Drawing.Graphics> object is set to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span></span>  
  
 <span data-ttu-id="bcb47-114">Der Code zeichnet die Bitmap auf dem Bildschirm zweimal: einmal auf weißem Hintergrund und einmal auf einem Hintergrund mehrfarbige.</span><span class="sxs-lookup"><span data-stu-id="bcb47-114">The code draws the bitmap on the screen twice: once on a white background and once on a multicolored background.</span></span> <span data-ttu-id="bcb47-115">Die Pixel in der Bitmap, die Teil von zwei Ellipsen sind über einen Alphaanteil von 160, müssen mit den Hintergrundfarben, auf dem Bildschirm die Auslassungspunkte gemischt werden.</span><span class="sxs-lookup"><span data-stu-id="bcb47-115">The pixels in the bitmap that are part of the two ellipses have an alpha component of 160, so the ellipses are blended with the background colors on the screen.</span></span>  
  
 <span data-ttu-id="bcb47-116">Die folgende Abbildung zeigt die Ausgabe des Codebeispiels.</span><span class="sxs-lookup"><span data-stu-id="bcb47-116">The following illustration shows the output of the code example.</span></span> <span data-ttu-id="bcb47-117">Beachten Sie, dass die Ellipsen mit dem Hintergrund zwar, aber sie sind nicht miteinander kombiniert.</span><span class="sxs-lookup"><span data-stu-id="bcb47-117">Note that the ellipses are blended with the background, but they are not blended with each other.</span></span>  
  
 <span data-ttu-id="bcb47-118">![Quellcode-Kopie](./media/sourcecopy.png "Sourcecopy")</span><span class="sxs-lookup"><span data-stu-id="bcb47-118">![Source Copy](./media/sourcecopy.png "sourcecopy")</span></span>  
  
 <span data-ttu-id="bcb47-119">Das Codebeispiel enthält die folgende Anweisung:</span><span class="sxs-lookup"><span data-stu-id="bcb47-119">The code example contains this statement:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 <span data-ttu-id="bcb47-120">Wenn Sie die Auslassungspunkte aus, um sowohl miteinander als auch mit dem Hintergrund gemischt werden möchten, ändern Sie diese Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="bcb47-120">If you want the ellipses to be blended with each other as well as with the background, change that statement to the following:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 <span data-ttu-id="bcb47-121">Die folgende Abbildung zeigt die Ausgabe der überarbeitete Code.</span><span class="sxs-lookup"><span data-stu-id="bcb47-121">The following illustration shows the output of the revised code.</span></span>  
  
 <span data-ttu-id="bcb47-122">![Quelle über](./media/sourceover.png "Sourceover")</span><span class="sxs-lookup"><span data-stu-id="bcb47-122">![Source Over](./media/sourceover.png "sourceover")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bcb47-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="bcb47-123">Compiling the Code</span></span>  
 <span data-ttu-id="bcb47-124">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs>`e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.</span><span class="sxs-lookup"><span data-stu-id="bcb47-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcb47-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcb47-125">See also</span></span>
- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="bcb47-126">Alphablending von Linien und Füllungen</span><span class="sxs-lookup"><span data-stu-id="bcb47-126">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
