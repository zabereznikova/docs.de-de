---
title: Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- metafiles [Windows Forms], working with
- examples [Windows Forms], bitmaps
- examples [Windows Forms], images
- bitmaps [Windows Forms], working with
- images [Windows Forms], working with
- examples [Windows Forms], metafiles
ms.assetid: a626d701-bd99-4fd8-b92f-7b8f794e042b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 29c8a4ef0a495d63c0263262857002f09d8c885a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="working-with-images-bitmaps-icons-and-metafiles"></a><span data-ttu-id="476b7-102">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="476b7-102">Working with Images, Bitmaps, Icons, and Metafiles</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="476b7-103"> stellt die `Bitmap`-Klasse zum Arbeiten mit Rasterbilder und die `Metafile`-Klasse zum Arbeiten mit Vektorgrafiken bereit.</span><span class="sxs-lookup"><span data-stu-id="476b7-103"> provides the `Bitmap` class for working with raster images and the `Metafile` class for working with vector images.</span></span> <span data-ttu-id="476b7-104">Sowohl die `Bitmap`-Klasse als auch die `Metafile`-Klasse erben von der `Image`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="476b7-104">The `Bitmap` and the `Metafile` classes both inherit from the `Image` class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="476b7-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="476b7-105">In This Section</span></span>  
 [<span data-ttu-id="476b7-106">Gewusst wie: Zeichnen einer vorhandenen Bitmap auf dem Bildschirm</span><span class="sxs-lookup"><span data-stu-id="476b7-106">How to: Draw an Existing Bitmap to the Screen</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-existing-bitmap-to-the-screen.md)  
 <span data-ttu-id="476b7-107">Beschreibt das Laden und Zeichnen von Bitmaps.</span><span class="sxs-lookup"><span data-stu-id="476b7-107">Describes how to load and draw bitmaps.</span></span>  
  
 [<span data-ttu-id="476b7-108">Gewusst wie: Laden und Anzeigen von Metadateien</span><span class="sxs-lookup"><span data-stu-id="476b7-108">How to: Load and Display Metafiles</span></span>](../../../../docs/framework/winforms/advanced/how-to-load-and-display-metafiles.md)  
 <span data-ttu-id="476b7-109">Veranschaulicht das Laden und Zeichnen von Metadateien.</span><span class="sxs-lookup"><span data-stu-id="476b7-109">Shows how to load and draw metafiles.</span></span>  
  
 [<span data-ttu-id="476b7-110">Zuschneiden und Skalieren von Bildern in GDI+</span><span class="sxs-lookup"><span data-stu-id="476b7-110">Cropping and Scaling Images in GDI+</span></span>](../../../../docs/framework/winforms/advanced/cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="476b7-111">Erläutert das Zuschneiden und Skalieren von Vektor- und Rasterbildern.</span><span class="sxs-lookup"><span data-stu-id="476b7-111">Explains how to crop and scale vector and raster images.</span></span>  
  
 [<span data-ttu-id="476b7-112">Gewusst wie: Drehen, Spiegeln und Zerren von Bildern</span><span class="sxs-lookup"><span data-stu-id="476b7-112">How to: Rotate, Reflect, and Skew Images</span></span>](../../../../docs/framework/winforms/advanced/how-to-rotate-reflect-and-skew-images.md)  
 <span data-ttu-id="476b7-113">Beschreibt das Zeichnen gedrehter, gespiegelter und gezerrter Bilder.</span><span class="sxs-lookup"><span data-stu-id="476b7-113">Describes how to draw rotated, reflected and skewed images.</span></span>  
  
 [<span data-ttu-id="476b7-114">Gewusst wie: Verwenden des Interpolationsmodus zum Steuern der Bildqualität während der Skalierung</span><span class="sxs-lookup"><span data-stu-id="476b7-114">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-interpolation-mode-to-control-image-quality-during-scaling.md)  
 <span data-ttu-id="476b7-115">Veranschaulicht, wie die <xref:System.Drawing.Drawing2D.InterpolationMode>-Enumeration verwendet wird, um die Bildqualität zu ändern.</span><span class="sxs-lookup"><span data-stu-id="476b7-115">Shows how to use the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to change image quality.</span></span>  
  
 [<span data-ttu-id="476b7-116">Gewusst wie: Erstellen von Miniaturbildern</span><span class="sxs-lookup"><span data-stu-id="476b7-116">How to: Create Thumbnail Images</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-thumbnail-images.md)  
 <span data-ttu-id="476b7-117">Beschreibt das Erstellen von Miniaturbildern.</span><span class="sxs-lookup"><span data-stu-id="476b7-117">Describes how to create thumbnail images.</span></span>  
  
 [<span data-ttu-id="476b7-118">Gewusst wie: Verbessern der Leistung durch das Vermeiden der automatischen Skalierung</span><span class="sxs-lookup"><span data-stu-id="476b7-118">How to: Improve Performance by Avoiding Automatic Scaling</span></span>](../../../../docs/framework/winforms/advanced/how-to-improve-performance-by-avoiding-automatic-scaling.md)  
 <span data-ttu-id="476b7-119">Erläutert das Zeichnen eines Bildes ohne automatische Skalierung.</span><span class="sxs-lookup"><span data-stu-id="476b7-119">Explains how to draw an image without automatic scaling.</span></span>  
  
 [<span data-ttu-id="476b7-120">Gewusst wie: Lesen von Bildmetadaten</span><span class="sxs-lookup"><span data-stu-id="476b7-120">How to: Read Image Metadata</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-image-metadata.md)  
 <span data-ttu-id="476b7-121">Beschreibt das Lesen von Metadaten aus einem Bild.</span><span class="sxs-lookup"><span data-stu-id="476b7-121">Describes how to read metadata from an image.</span></span>  
  
 [<span data-ttu-id="476b7-122">Gewusst wie: Erstellen einer Bitmap zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="476b7-122">How to: Create a Bitmap at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-bitmap-at-run-time.md)  
 <span data-ttu-id="476b7-123">Veranschaulicht das Zeichnen einer Bitmap zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="476b7-123">Shows how to draw a bitmap at runtime.</span></span>  
  
 [<span data-ttu-id="476b7-124">Gewusst wie: Extrahieren eines mit einer Datei verknüpften Symbols in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="476b7-124">How to: Extract the Icon Associated with a File in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-extract-the-icon-associated-with-a-file-in-windows-forms.md)  
 <span data-ttu-id="476b7-125">Beschreibt, wie ein Symbol extrahiert wird, das eine eingebettete Ressource einer Datei ist.</span><span class="sxs-lookup"><span data-stu-id="476b7-125">Describes how to extract an icon that is an embedded resource of a file.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="476b7-126">Verweis</span><span class="sxs-lookup"><span data-stu-id="476b7-126">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="476b7-127">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="476b7-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Imaging.Metafile>  
 <span data-ttu-id="476b7-128">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="476b7-128">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="476b7-129">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="476b7-129">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="476b7-130">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="476b7-130">Related Sections</span></span>  
 [<span data-ttu-id="476b7-131">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="476b7-131">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 <span data-ttu-id="476b7-132">Enthält Links zu Themen, in denen andere Typen von Bitmaps sowie deren Bearbeitung in Anwendungen erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="476b7-132">Contains links to topics that discuss different types of bitmaps and manipulating them in your applications.</span></span>
