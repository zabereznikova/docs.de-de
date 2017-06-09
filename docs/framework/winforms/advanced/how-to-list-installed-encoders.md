---
title: "Gewusst wie: Auflisten installierter Encoder | Microsoft Docs"
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
  - "Bildencoder, Auflisten"
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Auflisten installierter Encoder
Möglicherweise möchten Sie die auf einem Computer verfügbaren Bildencoder auflisten, um festzustellen, ob Ihre Anwendung ein bestimmtes Bilddateiformat speichern kann.  Über die <xref:System.Drawing.Imaging.ImageCodecInfo>\-Klasse werden die statischen <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A>\-Methoden bereitgestellt, damit Sie feststellen können, welche Bildcodierer verfügbar sind.  <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> gibt ein Array von <xref:System.Drawing.Imaging.ImageCodecInfo>\-Objekten zurück.  
  
## Beispiel  
 Im folgenden Codebeispiel wird die Liste der installierten Encoder mit den zugehörigen Eigenschaftswerten ausgegeben.  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Eine Windows Forms\-Anwendung  
  
-   <xref:System.Windows.Forms.PaintEventArgs>, ein Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 [Gewusst wie: Auflisten installierter Decoder](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)   
 [Verwenden von Bildencodern und \-decodern in Managed GDI\+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)