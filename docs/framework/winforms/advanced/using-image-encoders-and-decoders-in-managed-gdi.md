---
title: "Verwenden von Bildencodern und -decodern in Managed GDI+ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Bilddecoder, Verwenden"
  - "Bildencoder, Verwenden"
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Verwenden von Bildencodern und -decodern in Managed GDI+
Der <xref:System.Drawing>\-Namespace stellt die <xref:System.Drawing.Image>\-Klasse und die <xref:System.Drawing.Bitmap>\-Klasse zum Speichern und Bearbeiten von Bildern bereit.  Mit Bildcodierern in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können Sie Bilder aus dem Arbeitsspeicher auf die Festplatte schreiben. Mit Bilddecodern in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können Sie Bilder von einem Datenträger in den Arbeitsspeicher laden.  Ein Encoder übersetzt die in einem <xref:System.Drawing.Image>\-Objekt oder <xref:System.Drawing.Bitmap>\-Objekt enthaltenen Daten in ein bestimmtes Datenträgerdateiformat.  Ein Decoder übersetzt die in einer Datenträgerdatei enthaltenen Daten in das Format, das vom <xref:System.Drawing.Image>\-Objekt und <xref:System.Drawing.Bitmap>\-Objekt benötigt wird.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] verfügt über integrierte Encoder und Decoder, die die folgenden Dateitypen unterstützen:  
  
-   BMP  
  
-   GIF  
  
-   JPEG  
  
-   PNG  
  
-   TIFF  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] verfügt außerdem über integrierte Decoder, die die folgenden Dateitypen unterstützen:  
  
-   WMF  
  
-   EMF  
  
-   SYMBOL  
  
 In den folgenden Themen werden Encoder und Decoder ausführlicher erörtert:  
  
## In diesem Abschnitt  
 [Gewusst wie: Auflisten installierter Encoder](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 Beschreibt, wie die auf einem Computer verfügbaren Encoder aufgelistet werden.  
  
 [Gewusst wie: Auflisten installierter Decoder](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 Beschreibt, wie die auf einem Computer verfügbaren Decoder aufgelistet werden.  
  
 [Gewusst wie: Ermitteln der von einem Encoder unterstützten Parameter](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)  
 Beschreibt, wie die von einem Encoder unterstützten <xref:System.Drawing.Imaging.EncoderParameters> aufgelistet werden.  
  
 [Gewusst wie: Konvertieren eines BMP\-Bildes in ein PNG\-Bild](../../../../docs/framework/winforms/advanced/how-to-convert-a-bmp-image-to-a-png-image.md)  
 Beschreibt, wie ein Bild in einem anderen Bildformat gespeichert wird.  
  
 [Gewusst wie: Festlegen der JPEG\-Komprimierungsebene](../../../../docs/framework/winforms/advanced/how-to-set-jpeg-compression-level.md)  
 Beschreibt, wie die Qualitätsstufe eines Bildes geändert wird.  
  
## Referenz  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## Verwandte Abschnitte  
 [Verwalteter Code in GDI\+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)