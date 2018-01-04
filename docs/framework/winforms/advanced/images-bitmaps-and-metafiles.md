---
title: Bilder, Bitmaps und Metadateien
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- metafiles [Windows Forms], about metafiles
- bitmaps [Windows Forms], about bitmaps
- images [Windows Forms], about images
- Windows Forms, images
ms.assetid: 7152b45b-a55c-49bc-8c78-ae002a844f71
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 67f72847e5dca20acd623c566a882e0094e94f68
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="images-bitmaps-and-metafiles"></a><span data-ttu-id="2b8cb-102">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="2b8cb-102">Images, Bitmaps, and Metafiles</span></span>
<span data-ttu-id="2b8cb-103">Die `Image`-Klasse ist eine abstrakte Basisklasse, die Methoden für das Arbeiten mit Rasterbildern (Bitmaps) und Vektorbildern (Metadateien) bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-103">The `Image` class is an abstract base class that provides methods for working with raster images (bitmaps) and vector images (metafiles).</span></span> <span data-ttu-id="2b8cb-104">Die `Bitmap`-Klasse und die <xref:System.Drawing.Imaging.Metafile>-Klasse erben beide von der `Image`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-104">The `Bitmap` class and the <xref:System.Drawing.Imaging.Metafile> class both inherit from the `Image` class.</span></span> <span data-ttu-id="2b8cb-105">Die `Bitmap`-Klasse erweitert die Funktionen der `Image`-Klasse durch zusätzliche Methoden für das Laden, Speichern und Bearbeiten von Rasterbildern.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-105">The `Bitmap` class expands on the capabilities of the `Image` class by providing additional methods for loading, saving, and manipulating raster images.</span></span> <span data-ttu-id="2b8cb-106">Die <xref:System.Drawing.Imaging.Metafile>-Klasse erweitert die Funktionen der `Image`-Klasse durch zusätzliche Methoden für das Aufzeichnen und Überprüfen von Rasterbildern.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-106">The <xref:System.Drawing.Imaging.Metafile> class expands on the capabilities of the `Image` class by providing additional methods for recording and examining vector images.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2b8cb-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2b8cb-107">In This Section</span></span>  
 [<span data-ttu-id="2b8cb-108">Typen von Bitmaps</span><span class="sxs-lookup"><span data-stu-id="2b8cb-108">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 <span data-ttu-id="2b8cb-109">Erläutert die verschiedenen Bildformate.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-109">Discusses the various image formats.</span></span>  
  
 [<span data-ttu-id="2b8cb-110">Metadateien in GDI+</span><span class="sxs-lookup"><span data-stu-id="2b8cb-110">Metafiles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/metafiles-in-gdi.md)  
 <span data-ttu-id="2b8cb-111">Erläutert die [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]-Unterstützung für Metadateien.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-111">Discusses [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] support for metafiles.</span></span>  
  
 [<span data-ttu-id="2b8cb-112">Zeichnen, Positionieren und Klonen von Bildern in GDI+</span><span class="sxs-lookup"><span data-stu-id="2b8cb-112">Drawing, Positioning, and Cloning Images in GDI+</span></span>](../../../../docs/framework/winforms/advanced/drawing-positioning-and-cloning-images-in-gdi.md)  
 <span data-ttu-id="2b8cb-113">Erläutert Methoden für das Zeichnen von Vektor- und Rasterbildern mit verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-113">Discusses methods for drawing vector and raster images with managed code.</span></span>  
  
 [<span data-ttu-id="2b8cb-114">Zuschneiden und Skalieren von Bildern in GDI+</span><span class="sxs-lookup"><span data-stu-id="2b8cb-114">Cropping and Scaling Images in GDI+</span></span>](../../../../docs/framework/winforms/advanced/cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="2b8cb-115">Erläutert Methoden für das Zuschneiden und Skalieren von Vektor- und Rasterbildern mit verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-115">Discusses methods for cropping and scaling vector and raster images with managed code</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2b8cb-116">Verweis</span><span class="sxs-lookup"><span data-stu-id="2b8cb-116">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="2b8cb-117">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-117">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="2b8cb-118">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-118">Describes this class and has links to all of its members</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2b8cb-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="2b8cb-119">Related Sections</span></span>  
 [<span data-ttu-id="2b8cb-120">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="2b8cb-120">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)  
 <span data-ttu-id="2b8cb-121">Enthält Links zu Themen, die veranschaulichen, wie Bilder in Ihrer Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-121">Contains links to topics that demonstrate how to use images in your application.</span></span>
