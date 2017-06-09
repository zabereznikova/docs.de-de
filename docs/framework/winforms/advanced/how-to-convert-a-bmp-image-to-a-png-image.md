---
title: "Gewusst wie: Konvertieren eines BMP-Bildes in ein PNG-Bild | Microsoft Docs"
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
  - "BMP-Bilder, Konvertieren in PNG"
  - "Bildformate, Konvertieren zwischen"
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Konvertieren eines BMP-Bildes in ein PNG-Bild
Sie möchten sicher oft eine Datei von einem Bilddateiformat in ein anderes konvertieren.  Sie können diese Konvertierung einfach durchführen, indem Sie die <xref:System.Drawing.Image.Save%2A>\-Methode der <xref:System.Drawing.Image>\-Klasse aufrufen und das <xref:System.Drawing.Imaging.ImageFormat> für das gewünschte Bilddateiformat angeben.  
  
## Beispiel  
 Im folgenden Beispiel wird ein BMP\-Bild eines Typs geladen und im PNG\-Format gespeichert.  
  
 [!code-csharp[UsingImageEncodersDecoders#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Eine Windows Forms\-Anwendung  
  
-   Einen Verweis auf den `System.Drawing.Imaging`\-Namespace  
  
## Siehe auch  
 [Gewusst wie: Auflisten installierter Encoder](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)   
 [Verwenden von Bildencodern und \-decodern in Managed GDI\+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)   
 [Bitmaptypen](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)