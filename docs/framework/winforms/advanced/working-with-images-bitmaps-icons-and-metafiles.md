---
title: Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien
ms.date: 03/30/2017
helpviewer_keywords:
- metafiles [Windows Forms], working with
- examples [Windows Forms], bitmaps
- examples [Windows Forms], images
- bitmaps [Windows Forms], working with
- images [Windows Forms], working with
- examples [Windows Forms], metafiles
ms.assetid: a626d701-bd99-4fd8-b92f-7b8f794e042b
ms.openlocfilehash: 8c778018a2d78fbec67a3bf41b5cbaa8e4bfb606
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504861"
---
# <a name="working-with-images-bitmaps-icons-and-metafiles"></a><span data-ttu-id="50c5f-102">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="50c5f-102">Working with Images, Bitmaps, Icons, and Metafiles</span></span>
<span data-ttu-id="50c5f-103">GDI + bietet die `Bitmap` -Klasse beim Arbeiten mit Rasterbilder und die `Metafile` -Klasse für das Arbeiten mit Vektorgrafiken.</span><span class="sxs-lookup"><span data-stu-id="50c5f-103">GDI+ provides the `Bitmap` class for working with raster images and the `Metafile` class for working with vector images.</span></span> <span data-ttu-id="50c5f-104">Sowohl die `Bitmap`-Klasse als auch die `Metafile`-Klasse erben von der `Image`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="50c5f-104">The `Bitmap` and the `Metafile` classes both inherit from the `Image` class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50c5f-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="50c5f-105">In This Section</span></span>  
 [<span data-ttu-id="50c5f-106">Vorgehensweise: Zeichnen einer vorhandenen Bitmap auf dem Bildschirm</span><span class="sxs-lookup"><span data-stu-id="50c5f-106">How to: Draw an Existing Bitmap to the Screen</span></span>](how-to-draw-an-existing-bitmap-to-the-screen.md)  
 <span data-ttu-id="50c5f-107">Beschreibt das Laden und Zeichnen von Bitmaps.</span><span class="sxs-lookup"><span data-stu-id="50c5f-107">Describes how to load and draw bitmaps.</span></span>  
  
 [<span data-ttu-id="50c5f-108">Vorgehensweise: Laden und Anzeigen von Metadateien</span><span class="sxs-lookup"><span data-stu-id="50c5f-108">How to: Load and Display Metafiles</span></span>](how-to-load-and-display-metafiles.md)  
 <span data-ttu-id="50c5f-109">Veranschaulicht das Laden und Zeichnen von Metadateien.</span><span class="sxs-lookup"><span data-stu-id="50c5f-109">Shows how to load and draw metafiles.</span></span>  
  
 [<span data-ttu-id="50c5f-110">Zuschneiden und Skalieren von Bildern in GDI+</span><span class="sxs-lookup"><span data-stu-id="50c5f-110">Cropping and Scaling Images in GDI+</span></span>](cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="50c5f-111">Erläutert das Zuschneiden und Skalieren von Vektor- und Rasterbildern.</span><span class="sxs-lookup"><span data-stu-id="50c5f-111">Explains how to crop and scale vector and raster images.</span></span>  
  
 [<span data-ttu-id="50c5f-112">Vorgehensweise: Drehen, spiegeln und Zerren von Bildern</span><span class="sxs-lookup"><span data-stu-id="50c5f-112">How to: Rotate, Reflect, and Skew Images</span></span>](how-to-rotate-reflect-and-skew-images.md)  
 <span data-ttu-id="50c5f-113">Beschreibt das Zeichnen gedrehter, gespiegelter und gezerrter Bilder.</span><span class="sxs-lookup"><span data-stu-id="50c5f-113">Describes how to draw rotated, reflected and skewed images.</span></span>  
  
 [<span data-ttu-id="50c5f-114">Vorgehensweise: Verwenden des Interpolationsmodus zum Steuern der Bildqualität während der Skalierung</span><span class="sxs-lookup"><span data-stu-id="50c5f-114">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>](how-to-use-interpolation-mode-to-control-image-quality-during-scaling.md)  
 <span data-ttu-id="50c5f-115">Veranschaulicht, wie die <xref:System.Drawing.Drawing2D.InterpolationMode>-Enumeration verwendet wird, um die Bildqualität zu ändern.</span><span class="sxs-lookup"><span data-stu-id="50c5f-115">Shows how to use the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to change image quality.</span></span>  
  
 [<span data-ttu-id="50c5f-116">Vorgehensweise: Erstellen von Miniaturbildern</span><span class="sxs-lookup"><span data-stu-id="50c5f-116">How to: Create Thumbnail Images</span></span>](how-to-create-thumbnail-images.md)  
 <span data-ttu-id="50c5f-117">Beschreibt das Erstellen von Miniaturbildern.</span><span class="sxs-lookup"><span data-stu-id="50c5f-117">Describes how to create thumbnail images.</span></span>  
  
 [<span data-ttu-id="50c5f-118">Vorgehensweise: Verbessern der Leistung durch Vermeiden der automatischen Skalierung</span><span class="sxs-lookup"><span data-stu-id="50c5f-118">How to: Improve Performance by Avoiding Automatic Scaling</span></span>](how-to-improve-performance-by-avoiding-automatic-scaling.md)  
 <span data-ttu-id="50c5f-119">Erläutert das Zeichnen eines Bildes ohne automatische Skalierung.</span><span class="sxs-lookup"><span data-stu-id="50c5f-119">Explains how to draw an image without automatic scaling.</span></span>  
  
 [<span data-ttu-id="50c5f-120">Vorgehensweise: Lesen von Bildmetadaten</span><span class="sxs-lookup"><span data-stu-id="50c5f-120">How to: Read Image Metadata</span></span>](how-to-read-image-metadata.md)  
 <span data-ttu-id="50c5f-121">Beschreibt das Lesen von Metadaten aus einem Bild.</span><span class="sxs-lookup"><span data-stu-id="50c5f-121">Describes how to read metadata from an image.</span></span>  
  
 [<span data-ttu-id="50c5f-122">Vorgehensweise: Erstellen einer Bitmap zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="50c5f-122">How to: Create a Bitmap at Run Time</span></span>](how-to-create-a-bitmap-at-run-time.md)  
 <span data-ttu-id="50c5f-123">Veranschaulicht das Zeichnen einer Bitmap zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="50c5f-123">Shows how to draw a bitmap at runtime.</span></span>  
  
 [<span data-ttu-id="50c5f-124">Vorgehensweise: Extrahieren Sie das Symbol für den eine Datei in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="50c5f-124">How to: Extract the Icon Associated with a File in Windows Forms</span></span>](how-to-extract-the-icon-associated-with-a-file-in-windows-forms.md)  
 <span data-ttu-id="50c5f-125">Beschreibt, wie ein Symbol extrahiert wird, das eine eingebettete Ressource einer Datei ist.</span><span class="sxs-lookup"><span data-stu-id="50c5f-125">Describes how to extract an icon that is an embedded resource of a file.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="50c5f-126">Referenz</span><span class="sxs-lookup"><span data-stu-id="50c5f-126">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="50c5f-127">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="50c5f-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Imaging.Metafile>  
 <span data-ttu-id="50c5f-128">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="50c5f-128">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="50c5f-129">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="50c5f-129">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="50c5f-130">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="50c5f-130">Related Sections</span></span>  
 [<span data-ttu-id="50c5f-131">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="50c5f-131">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)  
 <span data-ttu-id="50c5f-132">Enthält Links zu Themen, in denen andere Typen von Bitmaps sowie deren Bearbeitung in Anwendungen erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="50c5f-132">Contains links to topics that discuss different types of bitmaps and manipulating them in your applications.</span></span>
