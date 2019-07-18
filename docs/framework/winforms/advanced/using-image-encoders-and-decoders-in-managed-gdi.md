---
title: Verwenden von Bildencodern und -decodern in Managed GDI+
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: 8cd66f3ce3da462867da9e23c38b3f6d877c058c
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505090"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a>Verwenden von Bildencodern und -decodern in Managed GDI+
Die <xref:System.Drawing> -Namespace stellt die <xref:System.Drawing.Image> und <xref:System.Drawing.Bitmap> Klassen zum Speichern und Bearbeiten von Bildern. Bildencoder in GDI + verwenden, können Sie Bilder aus dem Arbeitsspeicher auf den Datenträger schreiben. Bilddecoder in GDI + verwenden, können Sie Bilder vom Datenträger in den Arbeitsspeicher laden. Ein Encoder übersetzt, die Daten in eine <xref:System.Drawing.Image> oder <xref:System.Drawing.Bitmap> Objekt in ein festgelegter Datenträger-Dateiformat. Ein Decoder übersetzt, die Daten in eine Datenträgerdatei in das erforderliche Format der <xref:System.Drawing.Image> und <xref:System.Drawing.Bitmap> Objekte.  
  
 GDI + verfügt über integrierte Encoder und Decoder, die die folgenden Dateitypen unterstützt:  
  
- BMP  
  
- GIF  
  
- JPEG  
  
- PNG  
  
- TIFF  
  
 GDI + hat auch integrierte Decoder, die die folgenden Dateitypen unterstützt:  
  
- WMF  
  
- EMF  
  
- ICON  
  
 Die folgenden Themen wird erläutert, Encoder und Decoder im Detail:  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Auflisten installierter Encoder](how-to-list-installed-encoders.md)  
 Beschreibt, wie die auf einem Computer verfügbaren Encoder auflisten.  
  
 [Vorgehensweise: Auflisten installierter Decoder](how-to-list-installed-decoders.md)  
 Beschreibt das Auflisten von der Decodern auf einem Computer verfügbar.  
  
 [Vorgehensweise: Ermitteln der von einem Encoder unterstützten Parameter](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 Beschreibt, wie Sie die Liste der <xref:System.Drawing.Imaging.EncoderParameters> von einem Encoder unterstützten.  
  
 [Vorgehensweise: Konvertieren eines BMP-Bilds in ein PNG-Bild](how-to-convert-a-bmp-image-to-a-png-image.md)  
 Beschreibt, wie ein Bild in ein anderes Bild-Format zu speichern.  
  
 [Vorgehensweise: Festlegen der JPEG-Komprimierungsebene](how-to-set-jpeg-compression-level.md)  
 Beschreibt, wie die Qualität eines Bilds zu ändern.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Verwalteter Code in GDI+](about-gdi-managed-code.md)  
  
 [Bilder, Bitmaps und Metadateien](images-bitmaps-and-metafiles.md)
