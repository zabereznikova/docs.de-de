---
title: 'Gewusst wie: Verbessern der Leistung durch das Vermeiden der automatischen Skalierung'
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
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0130e0745dfca20da5dc723bb7cc84748bb0b148
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a><span data-ttu-id="5abe3-102">Gewusst wie: Verbessern der Leistung durch das Vermeiden der automatischen Skalierung</span><span class="sxs-lookup"><span data-stu-id="5abe3-102">How to: Improve Performance by Avoiding Automatic Scaling</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="5abe3-103">ein Bild kann automatisch skaliert werden, wie Sie es zeichnen.</span><span class="sxs-lookup"><span data-stu-id="5abe3-103"> may automatically scale an image as you draw it, which would decrease performance.</span></span> <span data-ttu-id="5abe3-104">Alternativ können Sie steuern, die Skalierung des Bilds durch Übergeben der Dimensionen des Zielrechtecks an die <xref:System.Drawing.Graphics.DrawImage%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="5abe3-104">Alternatively, you can control the scaling of the image by passing the dimensions of the destination rectangle to the <xref:System.Drawing.Graphics.DrawImage%2A> method.</span></span>  
  
 <span data-ttu-id="5abe3-105">Beispielsweise beim folgenden Aufruf der <xref:System.Drawing.Graphics.DrawImage%2A> Methode gibt einen oberen linken Ecke des (50, 30) aber keine Zielrechtecks an.</span><span class="sxs-lookup"><span data-stu-id="5abe3-105">For example, the following call to the <xref:System.Drawing.Graphics.DrawImage%2A> method specifies an upper-left corner of (50, 30) but does not specify a destination rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 <span data-ttu-id="5abe3-106">Obwohl dies die einfachste Version ist die <xref:System.Drawing.Graphics.DrawImage%2A> Methode im Hinblick auf die Anzahl der erforderlichen Argumente, es ist nicht unbedingt die effizienteste.</span><span class="sxs-lookup"><span data-stu-id="5abe3-106">Although this is the easiest version of the <xref:System.Drawing.Graphics.DrawImage%2A> method in terms of the number of required arguments, it is not necessarily the most efficient.</span></span> <span data-ttu-id="5abe3-107">Wenn die Auflösung von verwendet [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] (in der Regel 96 dpi) unterscheidet sich von der Auflösung, die in gespeicherten der <xref:System.Drawing.Image> -Objekt, und klicken Sie dann die <xref:System.Drawing.Graphics.DrawImage%2A> Methode wird das Bild skaliert.</span><span class="sxs-lookup"><span data-stu-id="5abe3-107">If the resolution used by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] (usually 96 dots per inch) is different from the resolution stored in the <xref:System.Drawing.Image> object, then the <xref:System.Drawing.Graphics.DrawImage%2A> method will scale the image.</span></span> <span data-ttu-id="5abe3-108">Nehmen wir beispielsweise an ein <xref:System.Drawing.Image> Objekt verfügt über eine Breite von 216 Pixel und einen Wert gespeicherte horizontalen Auflösung von 72 Punkte pro Zoll.</span><span class="sxs-lookup"><span data-stu-id="5abe3-108">For example, suppose an <xref:System.Drawing.Image> object has a width of 216 pixels and a stored horizontal resolution value of 72 dots per inch.</span></span> <span data-ttu-id="5abe3-109">Da 216/72 3, ist <xref:System.Drawing.Graphics.DrawImage%2A> wird skaliert das Bild, sodass er eine Breite von 3 Zoll bei einer Auflösung von 96 DPI-Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="5abe3-109">Because 216/72 is 3, <xref:System.Drawing.Graphics.DrawImage%2A> will scale the image so that it has a width of 3 inches at a resolution of 96 dots per inch.</span></span> <span data-ttu-id="5abe3-110">D. h. <xref:System.Drawing.Graphics.DrawImage%2A> zeigt ein Image mit einer Breite von 96 × 3 = 288 Pixel.</span><span class="sxs-lookup"><span data-stu-id="5abe3-110">That is, <xref:System.Drawing.Graphics.DrawImage%2A> will display an image that has a width of 96x3 = 288 pixels.</span></span>  
  
 <span data-ttu-id="5abe3-111">Selbst wenn die Bildschirmauflösung von 96 dpi unterscheidet [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] wahrscheinlich Skalierung das Bild als wären die Bildschirmauflösung 96 dpi.</span><span class="sxs-lookup"><span data-stu-id="5abe3-111">Even if your screen resolution is different from 96 dots per inch, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] will probably scale the image as if the screen resolution were 96 dots per inch.</span></span> <span data-ttu-id="5abe3-112">Grund hierfür ist, eine [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> Objekt bezieht sich auf einen Gerätekontext und wann [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Abfragen, die der Gerätekontext für die Auflösung des Bildschirms, das Ergebnis wird in der Regel 96, unabhängig von der tatsächlichen Bildschirmauflösung.</span><span class="sxs-lookup"><span data-stu-id="5abe3-112">That is because a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> object is associated with a device context, and when [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] queries the device context for the screen resolution, the result is usually 96, regardless of the actual screen resolution.</span></span> <span data-ttu-id="5abe3-113">Sie können die automatische Skalierung durch Angabe des Zielrechtecks im Vermeiden der <xref:System.Drawing.Graphics.DrawImage%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="5abe3-113">You can avoid automatic scaling by specifying the destination rectangle in the <xref:System.Drawing.Graphics.DrawImage%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5abe3-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5abe3-114">Example</span></span>  
 <span data-ttu-id="5abe3-115">Im folgende Beispiel werden zweimal dasselbe Bild gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5abe3-115">The following example draws the same image twice.</span></span> <span data-ttu-id="5abe3-116">Im ersten Fall die Breite und Höhe des Zielrechtecks nicht angegeben wurden, und das Bild wird automatisch skaliert.</span><span class="sxs-lookup"><span data-stu-id="5abe3-116">In the first case, the width and height of the destination rectangle are not specified, and the image is automatically scaled.</span></span> <span data-ttu-id="5abe3-117">Im zweiten Fall sind die Breite und Höhe (gemessen in Pixel) des Zielrechtecks identisch sein, als die Breite und Höhe des ursprünglichen Bilds angegeben.</span><span class="sxs-lookup"><span data-stu-id="5abe3-117">In the second case, the width and height (measured in pixels) of the destination rectangle are specified to be the same as the width and height of the original image.</span></span> <span data-ttu-id="5abe3-118">Die folgende Abbildung zeigt das Bild zweimal gerendert.</span><span class="sxs-lookup"><span data-stu-id="5abe3-118">The following illustration shows the image rendered twice.</span></span>  
  
 <span data-ttu-id="5abe3-119">![Skalierte Struktur](../../../../docs/framework/winforms/advanced/media/csscaledtexture1.png "csscaledtexture1")</span><span class="sxs-lookup"><span data-stu-id="5abe3-119">![Scaled Texture](../../../../docs/framework/winforms/advanced/media/csscaledtexture1.png "csscaledtexture1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5abe3-120">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="5abe3-120">Compiling the Code</span></span>  
 <span data-ttu-id="5abe3-121">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="5abe3-121">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="5abe3-122">Ersetzen Sie Texture.jpg durch ein Image-Name und Pfad, die auf Ihrem System gültig sind.</span><span class="sxs-lookup"><span data-stu-id="5abe3-122">Replace Texture.jpg with an image name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5abe3-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5abe3-123">See Also</span></span>  
 [<span data-ttu-id="5abe3-124">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="5abe3-124">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="5abe3-125">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="5abe3-125">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
