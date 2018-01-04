---
title: Zuschneiden und Skalieren von Bildern in GDI+
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
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0bbe7ac4b8c541ea76392f94f538e41816cf5c3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="cropping-and-scaling-images-in-gdi"></a><span data-ttu-id="1fe3f-102">Zuschneiden und Skalieren von Bildern in GDI+</span><span class="sxs-lookup"><span data-stu-id="1fe3f-102">Cropping and Scaling Images in GDI+</span></span>
<span data-ttu-id="1fe3f-103">Können Sie die <xref:System.Drawing.Graphics.DrawImage%2A> Methode von der <xref:System.Drawing.Graphics> -Klasse gezeichnet werden soll, und Positionieren von Vektor- und Rasterbildern.</span><span class="sxs-lookup"><span data-stu-id="1fe3f-103">You can use the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> class to draw and position vector images and raster images.</span></span> <span data-ttu-id="1fe3f-104"><xref:System.Drawing.Graphics.DrawImage%2A>ist eine überladene Methode, damit es gibt mehrere Möglichkeiten, die sie mit Argumenten bereitstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="1fe3f-104"><xref:System.Drawing.Graphics.DrawImage%2A> is an overloaded method, so there are several ways you can supply it with arguments.</span></span>  
  
## <a name="drawimage-variations"></a><span data-ttu-id="1fe3f-105">DrawImage-Varianten</span><span class="sxs-lookup"><span data-stu-id="1fe3f-105">DrawImage Variations</span></span>  
 <span data-ttu-id="1fe3f-106">Eine Variante der der <xref:System.Drawing.Graphics.DrawImage%2A> Methode empfängt einen <xref:System.Drawing.Bitmap> und ein <xref:System.Drawing.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="1fe3f-106">One variation of the <xref:System.Drawing.Graphics.DrawImage%2A> method receives a <xref:System.Drawing.Bitmap> and a <xref:System.Drawing.Rectangle>.</span></span> <span data-ttu-id="1fe3f-107">Das Rechteck wird das Ziel für den Zeichenvorgang angibt; also gibt es das Rechteck in der das Bild gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1fe3f-107">The rectangle specifies the destination for the drawing operation; that is, it specifies the rectangle in which to draw the image.</span></span> <span data-ttu-id="1fe3f-108">Wenn die Größe des Zielrechtecks von der Größe des dem ursprungsabbild unterscheidet, wird das Bild skaliert, um Zielrechtecks zu passen.</span><span class="sxs-lookup"><span data-stu-id="1fe3f-108">If the size of the destination rectangle is different from the size of the original image, the image is scaled to fit the destination rectangle.</span></span> <span data-ttu-id="1fe3f-109">Im folgenden Codebeispiel wird veranschaulicht, wie dasselbe Bild dreimal gezeichnet: einmal mit keine Skalierung, einmal mit einer Erweiterung und einmal mit einer Komprimierung:</span><span class="sxs-lookup"><span data-stu-id="1fe3f-109">The following code example shows how to draw the same image three times: once with no scaling, once with an expansion, and once with a compression:</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 <span data-ttu-id="1fe3f-110">Die folgende Abbildung zeigt die drei Bilder.</span><span class="sxs-lookup"><span data-stu-id="1fe3f-110">The following illustration shows the three pictures.</span></span>  
  
 <span data-ttu-id="1fe3f-111">![Skalierung](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span><span class="sxs-lookup"><span data-stu-id="1fe3f-111">![Scaling](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span></span>  
  
 <span data-ttu-id="1fe3f-112">Einige Varianten der der <xref:System.Drawing.Graphics.DrawImage%2A> Methode verfügen, einen Quellrechteck Parameter als auch ein Zielrechteck Parameter.</span><span class="sxs-lookup"><span data-stu-id="1fe3f-112">Some variations of the <xref:System.Drawing.Graphics.DrawImage%2A> method have a source-rectangle parameter as well as a destination-rectangle parameter.</span></span> <span data-ttu-id="1fe3f-113">Das Quellrechteck Parameter gibt an, die Teil des ursprünglichen Bilds gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1fe3f-113">The source-rectangle parameter specifies the portion of the original image to draw.</span></span> <span data-ttu-id="1fe3f-114">Das Zielrechteck gibt das Rechteck in der dieser Teil des Bilds gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1fe3f-114">The destination rectangle specifies the rectangle in which to draw that portion of the image.</span></span> <span data-ttu-id="1fe3f-115">Wenn die Größe des Zielrechtecks von der Größe des Quellrechtecks abweicht, wird das Bild skaliert um Zielrechtecks zu passen.</span><span class="sxs-lookup"><span data-stu-id="1fe3f-115">If the size of the destination rectangle is different from the size of the source rectangle, the picture is scaled to fit the destination rectangle.</span></span>  
  
 <span data-ttu-id="1fe3f-116">Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer <xref:System.Drawing.Bitmap> aus der Datei Runner.jpg.</span><span class="sxs-lookup"><span data-stu-id="1fe3f-116">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Runner.jpg.</span></span> <span data-ttu-id="1fe3f-117">Das gesamte Bild ohne Skalierung auf gezeichnet wird (0, 0).</span><span class="sxs-lookup"><span data-stu-id="1fe3f-117">The entire image is drawn with no scaling at (0, 0).</span></span> <span data-ttu-id="1fe3f-118">Und klicken Sie dann zweimal ein kleiner Teil des Bilds gezeichnet: einmal mit Komprimierung und einmal mit einer Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="1fe3f-118">Then a small portion of the image is drawn twice: once with a compression and once with an expansion.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 <span data-ttu-id="1fe3f-119">Die folgende Abbildung zeigt nicht skalierten Bild und dem komprimierte und erweiterten Image Teile.</span><span class="sxs-lookup"><span data-stu-id="1fe3f-119">The following illustration shows the unscaled image, and the compressed and expanded image portions.</span></span>  
  
 <span data-ttu-id="1fe3f-120">![Zuschneiden und Skalieren von](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span><span class="sxs-lookup"><span data-stu-id="1fe3f-120">![Cropping and Scaling](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fe3f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1fe3f-121">See Also</span></span>  
 [<span data-ttu-id="1fe3f-122">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="1fe3f-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="1fe3f-123">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="1fe3f-123">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
