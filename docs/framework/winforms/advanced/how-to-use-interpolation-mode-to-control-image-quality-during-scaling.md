---
title: "Gewusst wie: Verwenden des Interpolationsmodus zum Steuern der Bildqualität während der Skalierung"
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
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10a0ef4e7fd8514245a7659dd515d8f363a716ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a><span data-ttu-id="6884f-102">Gewusst wie: Verwenden des Interpolationsmodus zum Steuern der Bildqualität während der Skalierung</span><span class="sxs-lookup"><span data-stu-id="6884f-102">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>
<span data-ttu-id="6884f-103">Der Interpolationsmodus eine <xref:System.Drawing.Graphics> Objekt beeinflusst die Möglichkeit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Bilder skaliert (gestreckt bzw. verkleinert).</span><span class="sxs-lookup"><span data-stu-id="6884f-103">The interpolation mode of a <xref:System.Drawing.Graphics> object influences the way [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] scales (stretches and shrinks) images.</span></span> <span data-ttu-id="6884f-104">Die <xref:System.Drawing.Drawing2D.InterpolationMode> -Enumeration definiert mehrere Interpolationsmodi, von denen einige sind in der folgenden Liste:</span><span class="sxs-lookup"><span data-stu-id="6884f-104">The <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration defines several interpolation modes, some of which are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 <span data-ttu-id="6884f-105">Um ein Bild gestreckt wird, muss jedes Pixels in das ursprüngliche Image für eine Gruppe von Pixel im größeren Bild zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="6884f-105">To stretch an image, each pixel in the original image must be mapped to a group of pixels in the larger image.</span></span> <span data-ttu-id="6884f-106">Um ein Bild zu verkleinern, müssen Gruppen von Pixeln in das ursprüngliche Image auf einzelnen Pixel im kleineren Bild zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="6884f-106">To shrink an image, groups of pixels in the original image must be mapped to single pixels in the smaller image.</span></span> <span data-ttu-id="6884f-107">Die Effektivität der Algorithmen, die diese Zuordnungen ausführen bestimmt die Qualität eines skalierte Images.</span><span class="sxs-lookup"><span data-stu-id="6884f-107">The effectiveness of the algorithms that perform these mappings determines the quality of a scaled image.</span></span> <span data-ttu-id="6884f-108">Algorithmen, die skalierte Bilder von höherer Qualität produzieren tendenziell mehr Verarbeitungszeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="6884f-108">Algorithms that produce higher-quality scaled images tend to require more processing time.</span></span> <span data-ttu-id="6884f-109">In der vorangehenden Liste <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> ist der niedrigste Qualität-Modus und <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> Modus mit der höchsten Qualität ist.</span><span class="sxs-lookup"><span data-stu-id="6884f-109">In the preceding list, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> is the lowest-quality mode and <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> is the highest-quality mode.</span></span>  
  
 <span data-ttu-id="6884f-110">Um den Interpolationsmodus festzulegen, weisen Sie einem der Mitglieder von der <xref:System.Drawing.Drawing2D.InterpolationMode> -Enumeration der <xref:System.Drawing.Graphics.InterpolationMode%2A> Eigenschaft ein <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="6884f-110">To set the interpolation mode, assign one of the members of the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to the <xref:System.Drawing.Graphics.InterpolationMode%2A> property of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6884f-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6884f-111">Example</span></span>  
 <span data-ttu-id="6884f-112">Im folgenden Beispiel zeichnet ein Bild, und klicken Sie dann mit drei verschiedenen Interpolationsmodi verkleinert wird.</span><span class="sxs-lookup"><span data-stu-id="6884f-112">The following example draws an image and then shrinks the image with three different interpolation modes.</span></span>  
  
 <span data-ttu-id="6884f-113">Die folgende Abbildung zeigt das ursprüngliche Bild und die drei kleinere Bilder.</span><span class="sxs-lookup"><span data-stu-id="6884f-113">The following illustration shows the original image and the three smaller images.</span></span>  
  
 <span data-ttu-id="6884f-114">![Bild mit Interpolationseinstellungen](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")</span><span class="sxs-lookup"><span data-stu-id="6884f-114">![Image with Varied Interpolation Settings](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6884f-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6884f-115">Compiling the Code</span></span>  
 <span data-ttu-id="6884f-116">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="6884f-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6884f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6884f-117">See Also</span></span>  
 [<span data-ttu-id="6884f-118">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="6884f-118">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="6884f-119">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="6884f-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
