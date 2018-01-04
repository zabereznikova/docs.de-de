---
title: 'Gewusst wie: Verwenden des Mischmodus zum Steuern des Alphablendings'
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
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 40461ddb3fdae8076df5290afe669a8eca9f6a8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a><span data-ttu-id="67b06-102">Gewusst wie: Verwenden des Mischmodus zum Steuern des Alphablendings</span><span class="sxs-lookup"><span data-stu-id="67b06-102">How to: Use Compositing Mode to Control Alpha Blending</span></span>
<span data-ttu-id="67b06-103">Möglicherweise gibt es Zeiten, sollen eine Bitmap außerhalb des Bildschirms erstellen, die über die folgenden Eigenschaften verfügt:</span><span class="sxs-lookup"><span data-stu-id="67b06-103">There may be times when you want to create an off-screen bitmap that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="67b06-104">Farben haben alphanumerische Werte, die kleiner als 255 sind.</span><span class="sxs-lookup"><span data-stu-id="67b06-104">Colors have alpha values that are less than 255.</span></span>  
  
-   <span data-ttu-id="67b06-105">Farben sind keinen alpha miteinander vermischt werden, wie Sie beim Erstellen der Bitmap.</span><span class="sxs-lookup"><span data-stu-id="67b06-105">Colors are not alpha blended with each other as you create the bitmap.</span></span>  
  
-   <span data-ttu-id="67b06-106">Wenn Sie die fertige Bitmap anzeigen, sind Farben in der Bitmap Alphablending mit den Hintergrundfarben auf dem Anzeigegerät.</span><span class="sxs-lookup"><span data-stu-id="67b06-106">When you display the finished bitmap, colors in the bitmap are alpha blended with the background colors on the display device.</span></span>  
  
 <span data-ttu-id="67b06-107">Um eine solche Bitmap zu erstellen, erstellen Sie eine leere <xref:System.Drawing.Bitmap> -Objekt, und erstellen dann eine <xref:System.Drawing.Graphics> -Objekt auf Grundlage dieser Bitmap.</span><span class="sxs-lookup"><span data-stu-id="67b06-107">To create such a bitmap, construct a blank <xref:System.Drawing.Bitmap> object, and then construct a <xref:System.Drawing.Graphics> object based on that bitmap.</span></span> <span data-ttu-id="67b06-108">Legen Sie den Modus wird von der <xref:System.Drawing.Graphics> -Objekt <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="67b06-108">Set the compositing mode of the <xref:System.Drawing.Graphics> object to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67b06-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="67b06-109">Example</span></span>  
 <span data-ttu-id="67b06-110">Das folgende Beispiel erstellt eine <xref:System.Drawing.Graphics> -Objekt auf Grundlage einer <xref:System.Drawing.Bitmap> Objekt.</span><span class="sxs-lookup"><span data-stu-id="67b06-110">The following example creates a <xref:System.Drawing.Graphics> object based on a <xref:System.Drawing.Bitmap> object.</span></span> <span data-ttu-id="67b06-111">Der Code verwendet die <xref:System.Drawing.Graphics> -Objekt zusammen mit zwei halb transparenten Pinseln (Alpha = 160) auf die Bitmap gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="67b06-111">The code uses the <xref:System.Drawing.Graphics> object along with two semitransparent brushes (alpha = 160) to paint on the bitmap.</span></span> <span data-ttu-id="67b06-112">Der Code füllt eine rote und eine grüne Ellipse halb transparenten Pinseln verwenden.</span><span class="sxs-lookup"><span data-stu-id="67b06-112">The code fills a red ellipse and a green ellipse using the semitransparent brushes.</span></span> <span data-ttu-id="67b06-113">Die grüne Ellipse überschneidet sich mit der Ellipse, die Rot, aber die grüne wird nicht mit dem roten gemischt, da die Mischmodus von der <xref:System.Drawing.Graphics> -Objekts festgelegt wird, um <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span><span class="sxs-lookup"><span data-stu-id="67b06-113">The green ellipse overlaps the red ellipse, but the green is not blended with the red because the compositing mode of the <xref:System.Drawing.Graphics> object is set to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span></span>  
  
 <span data-ttu-id="67b06-114">Der Code zeichnet die Bitmap auf dem Bildschirm zweimal: einmal auf weißem Hintergrund und einmal in einem Hintergrundthread mehrfarbige.</span><span class="sxs-lookup"><span data-stu-id="67b06-114">The code draws the bitmap on the screen twice: once on a white background and once on a multicolored background.</span></span> <span data-ttu-id="67b06-115">Die Pixel in der Bitmap, die Teil von zwei Ellipsen haben einen Alphaanteil von 160, damit die Schaltfläche mit die Auslassungszeichen mit den Hintergrundfarben auf dem Bildschirm gemischt werden.</span><span class="sxs-lookup"><span data-stu-id="67b06-115">The pixels in the bitmap that are part of the two ellipses have an alpha component of 160, so the ellipses are blended with the background colors on the screen.</span></span>  
  
 <span data-ttu-id="67b06-116">Die folgende Abbildung zeigt die Ausgabe des Codebeispiels.</span><span class="sxs-lookup"><span data-stu-id="67b06-116">The following illustration shows the output of the code example.</span></span> <span data-ttu-id="67b06-117">Beachten Sie, dass die Ellipse mit dem Hintergrund gemischt werden, aber sie sind nicht miteinander vermischt.</span><span class="sxs-lookup"><span data-stu-id="67b06-117">Note that the ellipses are blended with the background, but they are not blended with each other.</span></span>  
  
 <span data-ttu-id="67b06-118">![Quelle kopieren](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "Sourcecopy")</span><span class="sxs-lookup"><span data-stu-id="67b06-118">![Source Copy](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")</span></span>  
  
 <span data-ttu-id="67b06-119">Das Codebeispiel enthält die folgende Anweisung:</span><span class="sxs-lookup"><span data-stu-id="67b06-119">The code example contains this statement:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 <span data-ttu-id="67b06-120">Wenn Sie die Auslassungszeichen, um sowohl miteinander als auch mit dem Hintergrund gemischt werden soll, ändern Sie diese Anweisung, die der folgenden:</span><span class="sxs-lookup"><span data-stu-id="67b06-120">If you want the ellipses to be blended with each other as well as with the background, change that statement to the following:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 <span data-ttu-id="67b06-121">Die folgende Abbildung zeigt die Ausgabe des überarbeiteten Codes.</span><span class="sxs-lookup"><span data-stu-id="67b06-121">The following illustration shows the output of the revised code.</span></span>  
  
 <span data-ttu-id="67b06-122">![Quelle über](../../../../docs/framework/winforms/advanced/media/sourceover.png "Sourceover")</span><span class="sxs-lookup"><span data-stu-id="67b06-122">![Source Over](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="67b06-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="67b06-123">Compiling the Code</span></span>  
 <span data-ttu-id="67b06-124">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="67b06-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b06-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67b06-125">See Also</span></span>  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [<span data-ttu-id="67b06-126">Alphablending von Linien und Füllungen</span><span class="sxs-lookup"><span data-stu-id="67b06-126">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
