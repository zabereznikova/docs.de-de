---
title: "Gewusst wie: Festlegen der JPEG-Komprimierungsebene | Microsoft Docs"
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
  - "Bilder [Windows Forms], Ändern von Encoderparametern"
  - "JPEG-Bilder, Festlegen der Qualitätsstufe"
ms.assetid: 4b9a74e3-9504-43c1-9f28-ace651d0772e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Festlegen der JPEG-Komprimierungsebene
Möglicherweise möchten Sie die Parameter eines Bildes ändern, wenn Sie das Bild auf einem Datenträger speichern, um dadurch die Dateigröße zu minimieren oder die Qualität zu verbessern.  Sie können die Qualität eines JPEG\-Bildes anpassen, indem Sie dessen Komprimierungsebene ändern.  Um die Komprimierungsebene beim Speichern eines JPEG\-Bildes anzugeben, müssen Sie ein <xref:System.Drawing.Imaging.EncoderParameters>\-Objekt erstellen und es an die <xref:System.Drawing.Image.Save%2A>\-Methode der <xref:System.Drawing.Image>\-Klasse übergeben.  Initialisieren Sie das <xref:System.Drawing.Imaging.EncoderParameters>\-Objekt, sodass es ein aus einem <xref:System.Drawing.Imaging.EncoderParameter> bestehendes Array aufweist.  Wenn Sie den <xref:System.Drawing.Imaging.EncoderParameter> erstellen, geben Sie den <xref:System.Drawing.Imaging.Encoder.Quality>\-Encoder und die gewünschte Komprimierungsebene an.  
  
## Beispiel  
 Im folgenden Beispielcode werden ein <xref:System.Drawing.Imaging.EncoderParameter>\-Objekt erstellt und drei JPEG\-Bilder gespeichert.  Jedes JPEG\-Bild wird mit einer anderen Qualitätsstufe gespeichert, indem der an den <xref:System.Drawing.Imaging.EncoderParameter>\-Konstruktor übergebene `long`\-Wert geändert wird.  Die Qualitätsstufe 0 steht für die höchste und die Qualitätsstufe 100 für die niedrigste Komprimierung.  
  
 [!code-csharp[UsingImageEncodersDecoders#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#8)]
 [!code-vb[UsingImageEncodersDecoders#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#8)]  
[!code-csharp[UsingImageEncodersDecoders#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#6)]
[!code-vb[UsingImageEncodersDecoders#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#6)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Eine Windows Forms\-Anwendung  
  
-   <xref:System.Windows.Forms.PaintEventArgs>, ein Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
-   Eine Bilddatei mit dem Namen `TestPhoto.jpg`, die unter **c:\\** gespeichert ist.  
  
## Siehe auch  
 [Gewusst wie: Ermitteln der von einem Encoder unterstützten Parameter](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)   
 [Bitmaptypen](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)   
 [Verwenden von Bildencodern und \-decodern in Managed GDI\+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)