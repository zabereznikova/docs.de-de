---
title: Verwenden von Bildencodern und -decodern in Managed GDI+
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64384e3c283b6596e36d5b2bd583a304faf080b4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a>Verwenden von Bildencodern und -decodern in Managed GDI+
Die <xref:System.Drawing> -Namespace stellt die <xref:System.Drawing.Image> und <xref:System.Drawing.Bitmap> Klassen zum Speichern und Bearbeiten von Bildern. Mithilfe von Bildencodern in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], können Sie Bilder aus dem Arbeitsspeicher auf dem Datenträger festgeschrieben. Mithilfe von Bilddecoder in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], können Sie Bilder vom Datenträger in den Speicher geladen. Ein Encoder übersetzt, die Daten in eine <xref:System.Drawing.Image> oder <xref:System.Drawing.Bitmap> Objekt in das Dateiformat festgelegten Datenträger. Ein Decoder übersetzt, die Daten in eine Datei in das erforderliche Format der <xref:System.Drawing.Image> und <xref:System.Drawing.Bitmap> Objekte.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]verfügt über integrierte Encoder und Decoder, die folgenden Dateitypen unterstützen:  
  
-   BMP  
  
-   GIF  
  
-   JPEG  
  
-   PNG  
  
-   TIFF  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]Außerdem verfügt über integrierte Decoder, die die folgenden Dateitypen unterstützen:  
  
-   WMF  
  
-   EMF  
  
-   SYMBOL "  
  
 Die folgenden Themen behandeln Encoder und Decoder ausführlicher:  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Auflisten installierter Encoder](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 Beschreibt, wie die auf einem Computer verfügbaren Encoder aufgelistet.  
  
 [Gewusst wie: Auflisten installierter Decoder](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 Beschreibt, wie die auf einem Computer verfügbaren Decoder aufgelistet.  
  
 [Gewusst wie: Ermitteln der von einem Encoder unterstützten Parameter](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)  
 Beschreibt, wie Sie die Liste der <xref:System.Drawing.Imaging.EncoderParameters> von einem Encoder unterstützten.  
  
 [Gewusst wie: Konvertieren eines BMP-Bilds in ein PNG-Bild](../../../../docs/framework/winforms/advanced/how-to-convert-a-bmp-image-to-a-png-image.md)  
 Beschreibt, wie ein Bild in ein anderes Bild-Format gespeichert werden.  
  
 [Gewusst wie: Festlegen der JPEG-Komprimierungsebene](../../../../docs/framework/winforms/advanced/how-to-set-jpeg-compression-level.md)  
 Beschreibt, wie die Qualität eines Bilds zu ändern.  
  
## <a name="reference"></a>Verweis  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Verwalteter Code in GDI+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
