---
title: Zeichnen, Positionieren und Klonen von Bildern in GDI+
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
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3ba716a36280d2ac08dae907abbdbe05e563dfc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a><span data-ttu-id="ddb09-102">Zeichnen, Positionieren und Klonen von Bildern in GDI+</span><span class="sxs-lookup"><span data-stu-id="ddb09-102">Drawing, Positioning, and Cloning Images in GDI+</span></span>
<span data-ttu-id="ddb09-103">Können Sie die <xref:System.Drawing.Bitmap> Klasse zum Laden und Anzeigen von Rasterbildern, und Sie können die <xref:System.Drawing.Imaging.Metafile> Klasse zum Laden und Anzeigen von Vektorgrafiken.</span><span class="sxs-lookup"><span data-stu-id="ddb09-103">You can use the <xref:System.Drawing.Bitmap> class to load and display raster images, and you can use the <xref:System.Drawing.Imaging.Metafile> class to load and display vector images.</span></span> <span data-ttu-id="ddb09-104">Die <xref:System.Drawing.Bitmap> und <xref:System.Drawing.Imaging.Metafile> Klassen erben von der <xref:System.Drawing.Image> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ddb09-104">The <xref:System.Drawing.Bitmap> and <xref:System.Drawing.Imaging.Metafile> classes inherit from the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="ddb09-105">Um ein Image des Vektors anzuzeigen, benötigen Sie eine Instanz von der <xref:System.Drawing.Graphics> Klasse und ein <xref:System.Drawing.Imaging.Metafile>.</span><span class="sxs-lookup"><span data-stu-id="ddb09-105">To display a vector image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="ddb09-106">Um ein Rasterbild anzuzeigen, benötigen Sie eine Instanz von der <xref:System.Drawing.Graphics> Klasse und ein <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="ddb09-106">To display a raster image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="ddb09-107">Die Instanz von der <xref:System.Drawing.Graphics> -Klasse stellt die <xref:System.Drawing.Graphics.DrawImage%2A> -Methode, die empfängt die <xref:System.Drawing.Imaging.Metafile> oder <xref:System.Drawing.Bitmap> als Argument.</span><span class="sxs-lookup"><span data-stu-id="ddb09-107">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawImage%2A> method, which receives the <xref:System.Drawing.Imaging.Metafile> or <xref:System.Drawing.Bitmap> as an argument.</span></span>  
  
## <a name="file-types-and-cloning"></a><span data-ttu-id="ddb09-108">Dateitypen und Klonen</span><span class="sxs-lookup"><span data-stu-id="ddb09-108">File Types and Cloning</span></span>  
 <span data-ttu-id="ddb09-109">Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer <xref:System.Drawing.Bitmap> aus der Datei Climber.jpg und zeigt die Bitmap.</span><span class="sxs-lookup"><span data-stu-id="ddb09-109">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Climber.jpg and displays the bitmap.</span></span> <span data-ttu-id="ddb09-110">Der Zielort für die linke obere Ecke des Bilds, (10, 10), in der zweiten und dritten Parameter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="ddb09-110">The destination point for the upper-left corner of the image, (10, 10), is specified in the second and third parameters.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 <span data-ttu-id="ddb09-111">Die folgende Abbildung zeigt das Bild an.</span><span class="sxs-lookup"><span data-stu-id="ddb09-111">The following illustration shows the image.</span></span>  
  
 <span data-ttu-id="ddb09-112">![Abbildung Beispiel](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span><span class="sxs-lookup"><span data-stu-id="ddb09-112">![Image Sample](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span></span>  
  
 <span data-ttu-id="ddb09-113">Das Konstruieren von <xref:System.Drawing.Bitmap> Objekte aus einer Vielzahl von Grafiken Dateiformate: BMP, GIF, JPEG, EXIF, PNG, TIFF und Symbol.</span><span class="sxs-lookup"><span data-stu-id="ddb09-113">You can construct <xref:System.Drawing.Bitmap> objects from a variety of graphics file formats: BMP, GIF, JPEG, EXIF, PNG, TIFF, and ICON.</span></span>  
  
 <span data-ttu-id="ddb09-114">Im folgenden Codebeispiel wird veranschaulicht, wie zum Konstruieren <xref:System.Drawing.Bitmap> Objekte aus einer Vielzahl von Dateitypen und zeigt dann die Bitmaps.</span><span class="sxs-lookup"><span data-stu-id="ddb09-114">The following code example shows how to construct <xref:System.Drawing.Bitmap> objects from a variety of file types and then displays the bitmaps.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <span data-ttu-id="ddb09-115">Die <xref:System.Drawing.Bitmap> Klasse bietet einen <xref:System.Drawing.Bitmap.Clone%2A> -Methode, die Sie verwenden können, um eine Kopie eines vorhandenen <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="ddb09-115">The <xref:System.Drawing.Bitmap> class provides a <xref:System.Drawing.Bitmap.Clone%2A> method that you can use to make a copy of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="ddb09-116">Die <xref:System.Drawing.Bitmap.Clone%2A> -Methode besitzt einen Quelle Rechteck-Parameter, die Sie verwenden können, um den Teil der ursprünglichen Bitmap anzugeben, die Sie kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ddb09-116">The <xref:System.Drawing.Bitmap.Clone%2A> method has a source rectangle parameter that you can use to specify the portion of the original bitmap that you want to copy.</span></span> <span data-ttu-id="ddb09-117">Das folgende Codebeispiel veranschaulicht das Erstellen einer <xref:System.Drawing.Bitmap> durch Klonen die obere Hälfte eines vorhandenen <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="ddb09-117">The following code example shows how to create a <xref:System.Drawing.Bitmap> by cloning the top half of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="ddb09-118">Dann werden beide Bilder gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ddb09-118">Then both images are drawn.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 <span data-ttu-id="ddb09-119">Die folgende Abbildung zeigt die beiden Images.</span><span class="sxs-lookup"><span data-stu-id="ddb09-119">The following illustration shows the two images.</span></span>  
  
 <span data-ttu-id="ddb09-120">![Zuschneiden](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span><span class="sxs-lookup"><span data-stu-id="ddb09-120">![Cropping](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb09-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddb09-121">See Also</span></span>  
 [<span data-ttu-id="ddb09-122">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="ddb09-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="ddb09-123">Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen</span><span class="sxs-lookup"><span data-stu-id="ddb09-123">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="ddb09-124">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="ddb09-124">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
