---
title: Verwenden von Bildencodern und -decodern in Managed GDI+
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: e56bc20eb55d694d19b25d9e94e5c9d9e3952628
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666450"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a><span data-ttu-id="199d9-102">Verwenden von Bildencodern und -decodern in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="199d9-102">Using Image Encoders and Decoders in Managed GDI+</span></span>
<span data-ttu-id="199d9-103">Die <xref:System.Drawing> -Namespace stellt die <xref:System.Drawing.Image> und <xref:System.Drawing.Bitmap> Klassen zum Speichern und Bearbeiten von Bildern.</span><span class="sxs-lookup"><span data-stu-id="199d9-103">The <xref:System.Drawing> namespace provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="199d9-104">Mithilfe von Bildencodern in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], Sie können Images aus dem Arbeitsspeicher auf den Datenträger schreiben.</span><span class="sxs-lookup"><span data-stu-id="199d9-104">By using image encoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can write images from memory to disk.</span></span> <span data-ttu-id="199d9-105">Mithilfe von Bilddecoder in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], können Sie Bilder vom Datenträger in den Arbeitsspeicher laden.</span><span class="sxs-lookup"><span data-stu-id="199d9-105">By using image decoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can load images from disk into memory.</span></span> <span data-ttu-id="199d9-106">Ein Encoder übersetzt, die Daten in eine <xref:System.Drawing.Image> oder <xref:System.Drawing.Bitmap> Objekt in ein festgelegter Datenträger-Dateiformat.</span><span class="sxs-lookup"><span data-stu-id="199d9-106">An encoder translates the data in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object into a designated disk file format.</span></span> <span data-ttu-id="199d9-107">Ein Decoder übersetzt, die Daten in eine Datenträgerdatei in das erforderliche Format der <xref:System.Drawing.Image> und <xref:System.Drawing.Bitmap> Objekte.</span><span class="sxs-lookup"><span data-stu-id="199d9-107">A decoder translates the data in a disk file to the format required by the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="199d9-108">verfügt über integrierte Encoder und Decoder, die die folgenden Dateitypen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="199d9-108">has built-in encoders and decoders that support the following file types:</span></span>  
  
- <span data-ttu-id="199d9-109">BMP</span><span class="sxs-lookup"><span data-stu-id="199d9-109">BMP</span></span>  
  
- <span data-ttu-id="199d9-110">GIF</span><span class="sxs-lookup"><span data-stu-id="199d9-110">GIF</span></span>  
  
- <span data-ttu-id="199d9-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="199d9-111">JPEG</span></span>  
  
- <span data-ttu-id="199d9-112">PNG</span><span class="sxs-lookup"><span data-stu-id="199d9-112">PNG</span></span>  
  
- <span data-ttu-id="199d9-113">TIFF</span><span class="sxs-lookup"><span data-stu-id="199d9-113">TIFF</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="199d9-114">Außerdem verfügt über integrierte Decoder, die die folgenden Dateitypen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="199d9-114">also has built-in decoders that support the following file types:</span></span>  
  
- <span data-ttu-id="199d9-115">WMF</span><span class="sxs-lookup"><span data-stu-id="199d9-115">WMF</span></span>  
  
- <span data-ttu-id="199d9-116">EMF</span><span class="sxs-lookup"><span data-stu-id="199d9-116">EMF</span></span>  
  
- <span data-ttu-id="199d9-117">ICON</span><span class="sxs-lookup"><span data-stu-id="199d9-117">ICON</span></span>  
  
 <span data-ttu-id="199d9-118">Die folgenden Themen wird erläutert, Encoder und Decoder im Detail:</span><span class="sxs-lookup"><span data-stu-id="199d9-118">The following topics discuss encoders and decoders in more detail:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="199d9-119">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="199d9-119">In This Section</span></span>  
 [<span data-ttu-id="199d9-120">Vorgehensweise: Auflisten installierter Encoder</span><span class="sxs-lookup"><span data-stu-id="199d9-120">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)  
 <span data-ttu-id="199d9-121">Beschreibt, wie die auf einem Computer verfügbaren Encoder auflisten.</span><span class="sxs-lookup"><span data-stu-id="199d9-121">Describes how to list the encoders available on a computer.</span></span>  
  
 [<span data-ttu-id="199d9-122">Vorgehensweise: Auflisten installierter Decoder</span><span class="sxs-lookup"><span data-stu-id="199d9-122">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)  
 <span data-ttu-id="199d9-123">Beschreibt das Auflisten von der Decodern auf einem Computer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="199d9-123">Describes how to list the decoders available on a computer.</span></span>  
  
 [<span data-ttu-id="199d9-124">Vorgehensweise: Ermitteln der von einem Encoder unterstützten Parameter</span><span class="sxs-lookup"><span data-stu-id="199d9-124">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 <span data-ttu-id="199d9-125">Beschreibt, wie Sie die Liste der <xref:System.Drawing.Imaging.EncoderParameters> von einem Encoder unterstützten.</span><span class="sxs-lookup"><span data-stu-id="199d9-125">Describes how to list the <xref:System.Drawing.Imaging.EncoderParameters> supported by an encoder.</span></span>  
  
 [<span data-ttu-id="199d9-126">Vorgehensweise: Konvertieren eines BMP-Bilds in ein PNG-Bild</span><span class="sxs-lookup"><span data-stu-id="199d9-126">How to: Convert a BMP image to a PNG image</span></span>](how-to-convert-a-bmp-image-to-a-png-image.md)  
 <span data-ttu-id="199d9-127">Beschreibt, wie ein Bild in ein anderes Bild-Format zu speichern.</span><span class="sxs-lookup"><span data-stu-id="199d9-127">Describes how to save a image in a different image format.</span></span>  
  
 [<span data-ttu-id="199d9-128">Vorgehensweise: Festlegen der JPEG-Komprimierungsebene</span><span class="sxs-lookup"><span data-stu-id="199d9-128">How to: Set JPEG Compression Level</span></span>](how-to-set-jpeg-compression-level.md)  
 <span data-ttu-id="199d9-129">Beschreibt, wie die Qualität eines Bilds zu ändern.</span><span class="sxs-lookup"><span data-stu-id="199d9-129">Describes how to change the quality level of an image.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="199d9-130">Referenz</span><span class="sxs-lookup"><span data-stu-id="199d9-130">Reference</span></span>  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a><span data-ttu-id="199d9-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="199d9-131">Related Sections</span></span>  
 [<span data-ttu-id="199d9-132">Verwalteter Code in GDI+</span><span class="sxs-lookup"><span data-stu-id="199d9-132">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
  
 [<span data-ttu-id="199d9-133">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="199d9-133">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
