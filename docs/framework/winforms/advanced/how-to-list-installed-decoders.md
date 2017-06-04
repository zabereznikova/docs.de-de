---
title: "Gewusst wie: Auflisten installierter Decoder | Microsoft Docs"
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
  - "Bildcodecs, Auflisten"
  - "Bilddecoder, Auflisten"
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Auflisten installierter Decoder
Möglicherweise möchten Sie die auf einem Computer verfügbaren Bilddecoder auflisten, um festzustellen, ob Ihre Anwendung ein bestimmtes Bilddateiformat lesen kann.  Über die <xref:System.Drawing.Imaging.ImageCodecInfo>\-Klasse werden die statischen <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A>\-Methoden bereitgestellt, damit Sie feststellen können, welche Bilddecoder verfügbar sind.  <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> gibt ein Array von <xref:System.Drawing.Imaging.ImageCodecInfo>\-Objekten zurück.  
  
## Beispiel  
 Im folgenden Codebeispiel wird die Liste der installierten Decoder mit den zugehörigen Eigenschaftswerten ausgegeben.  
  
 [!code-csharp[UsingImageEncodersDecoders#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Eine Windows Forms\-Anwendung  
  
-   <xref:System.Windows.Forms.PaintEventArgs>, ein Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 [Gewusst wie: Auflisten installierter Encoder](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)   
 [Verwenden von Bildencodern und \-decodern in Managed GDI\+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)