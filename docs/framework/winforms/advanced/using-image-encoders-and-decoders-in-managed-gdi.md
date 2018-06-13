---
title: Verwenden von Bildencodern und -decodern in Managed GDI+
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: b2e51587209cb4df41ea1fd18ce5c2088ee07a2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524500"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a><span data-ttu-id="4d61b-102">Verwenden von Bildencodern und -decodern in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="4d61b-102">Using Image Encoders and Decoders in Managed GDI+</span></span>
<span data-ttu-id="4d61b-103">Die <xref:System.Drawing> -Namespace stellt die <xref:System.Drawing.Image> und <xref:System.Drawing.Bitmap> Klassen zum Speichern und Bearbeiten von Bildern.</span><span class="sxs-lookup"><span data-stu-id="4d61b-103">The <xref:System.Drawing> namespace provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="4d61b-104">Mithilfe von Bildencodern in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], können Sie Bilder aus dem Arbeitsspeicher auf dem Datenträger festgeschrieben.</span><span class="sxs-lookup"><span data-stu-id="4d61b-104">By using image encoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can write images from memory to disk.</span></span> <span data-ttu-id="4d61b-105">Mithilfe von Bilddecoder in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], können Sie Bilder vom Datenträger in den Speicher geladen.</span><span class="sxs-lookup"><span data-stu-id="4d61b-105">By using image decoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can load images from disk into memory.</span></span> <span data-ttu-id="4d61b-106">Ein Encoder übersetzt, die Daten in eine <xref:System.Drawing.Image> oder <xref:System.Drawing.Bitmap> Objekt in das Dateiformat festgelegten Datenträger.</span><span class="sxs-lookup"><span data-stu-id="4d61b-106">An encoder translates the data in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object into a designated disk file format.</span></span> <span data-ttu-id="4d61b-107">Ein Decoder übersetzt, die Daten in eine Datei in das erforderliche Format der <xref:System.Drawing.Image> und <xref:System.Drawing.Bitmap> Objekte.</span><span class="sxs-lookup"><span data-stu-id="4d61b-107">A decoder translates the data in a disk file to the format required by the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="4d61b-108"> verfügt über integrierte Encoder und Decoder, die folgenden Dateitypen unterstützen:</span><span class="sxs-lookup"><span data-stu-id="4d61b-108"> has built-in encoders and decoders that support the following file types:</span></span>  
  
-   <span data-ttu-id="4d61b-109">BMP</span><span class="sxs-lookup"><span data-stu-id="4d61b-109">BMP</span></span>  
  
-   <span data-ttu-id="4d61b-110">GIF</span><span class="sxs-lookup"><span data-stu-id="4d61b-110">GIF</span></span>  
  
-   <span data-ttu-id="4d61b-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="4d61b-111">JPEG</span></span>  
  
-   <span data-ttu-id="4d61b-112">PNG</span><span class="sxs-lookup"><span data-stu-id="4d61b-112">PNG</span></span>  
  
-   <span data-ttu-id="4d61b-113">TIFF</span><span class="sxs-lookup"><span data-stu-id="4d61b-113">TIFF</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="4d61b-114"> Außerdem verfügt über integrierte Decoder, die die folgenden Dateitypen unterstützen:</span><span class="sxs-lookup"><span data-stu-id="4d61b-114"> also has built-in decoders that support the following file types:</span></span>  
  
-   <span data-ttu-id="4d61b-115">WMF</span><span class="sxs-lookup"><span data-stu-id="4d61b-115">WMF</span></span>  
  
-   <span data-ttu-id="4d61b-116">EMF</span><span class="sxs-lookup"><span data-stu-id="4d61b-116">EMF</span></span>  
  
-   <span data-ttu-id="4d61b-117">SYMBOL "</span><span class="sxs-lookup"><span data-stu-id="4d61b-117">ICON</span></span>  
  
 <span data-ttu-id="4d61b-118">Die folgenden Themen behandeln Encoder und Decoder ausführlicher:</span><span class="sxs-lookup"><span data-stu-id="4d61b-118">The following topics discuss encoders and decoders in more detail:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4d61b-119">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4d61b-119">In This Section</span></span>  
 [<span data-ttu-id="4d61b-120">Gewusst wie: Auflisten installierter Encoder</span><span class="sxs-lookup"><span data-stu-id="4d61b-120">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 <span data-ttu-id="4d61b-121">Beschreibt, wie die auf einem Computer verfügbaren Encoder aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="4d61b-121">Describes how to list the encoders available on a computer.</span></span>  
  
 [<span data-ttu-id="4d61b-122">Gewusst wie: Auflisten installierter Decoder</span><span class="sxs-lookup"><span data-stu-id="4d61b-122">How to: List Installed Decoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 <span data-ttu-id="4d61b-123">Beschreibt, wie die auf einem Computer verfügbaren Decoder aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="4d61b-123">Describes how to list the decoders available on a computer.</span></span>  
  
 [<span data-ttu-id="4d61b-124">Gewusst wie: Ermitteln der von einem Encoder unterstützten Parameter</span><span class="sxs-lookup"><span data-stu-id="4d61b-124">How to: Determine the Parameters Supported by an Encoder</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)  
 <span data-ttu-id="4d61b-125">Beschreibt, wie Sie die Liste der <xref:System.Drawing.Imaging.EncoderParameters> von einem Encoder unterstützten.</span><span class="sxs-lookup"><span data-stu-id="4d61b-125">Describes how to list the <xref:System.Drawing.Imaging.EncoderParameters> supported by an encoder.</span></span>  
  
 [<span data-ttu-id="4d61b-126">Gewusst wie: Konvertieren eines BMP-Bilds in ein PNG-Bild</span><span class="sxs-lookup"><span data-stu-id="4d61b-126">How to: Convert a BMP image to a PNG image</span></span>](../../../../docs/framework/winforms/advanced/how-to-convert-a-bmp-image-to-a-png-image.md)  
 <span data-ttu-id="4d61b-127">Beschreibt, wie ein Bild in ein anderes Bild-Format gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="4d61b-127">Describes how to save a image in a different image format.</span></span>  
  
 [<span data-ttu-id="4d61b-128">Gewusst wie: Festlegen der JPEG-Komprimierungsebene</span><span class="sxs-lookup"><span data-stu-id="4d61b-128">How to: Set JPEG Compression Level</span></span>](../../../../docs/framework/winforms/advanced/how-to-set-jpeg-compression-level.md)  
 <span data-ttu-id="4d61b-129">Beschreibt, wie die Qualität eines Bilds zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4d61b-129">Describes how to change the quality level of an image.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4d61b-130">Referenz</span><span class="sxs-lookup"><span data-stu-id="4d61b-130">Reference</span></span>  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a><span data-ttu-id="4d61b-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="4d61b-131">Related Sections</span></span>  
 [<span data-ttu-id="4d61b-132">Verwalteter Code in GDI+</span><span class="sxs-lookup"><span data-stu-id="4d61b-132">About GDI+ Managed Code</span></span>](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
  
 [<span data-ttu-id="4d61b-133">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="4d61b-133">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
