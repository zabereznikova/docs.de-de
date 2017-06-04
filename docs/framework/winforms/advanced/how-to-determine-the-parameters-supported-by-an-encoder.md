---
title: "Gewusst wie: Ermitteln der von einem Encoder unterst&#252;tzten Parameter | Microsoft Docs"
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
  - "Encoderparameter, Bestimmen von unterstützten"
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Ermitteln der von einem Encoder unterst&#252;tzten Parameter
Sie können Bildparameter wie Qualitätsstufe und Komprimierungsebene anpassen, müssen gleichzeitig jedoch wissen, welche Parameter von einem bestimmten Bildencoder unterstützt werden.  Über die <xref:System.Drawing.Image>\-Klasse wird die <xref:System.Drawing.Image.GetEncoderParameterList%2A>\-Methode bereitgestellt, sodass Sie ermitteln können, welche Bildparameter für einen bestimmten Encoder unterstützt werden.  Sie geben den Encoder mit einer GUID an.  Die <xref:System.Drawing.Image.GetEncoderParameterList%2A>\-Methode gibt ein Array von <xref:System.Drawing.Imaging.EncoderParameter>\-Objekten zurück.  
  
## Beispiel  
 Im folgenden Beispielcode werden die unterstützten Parameter für den JPEG\-Encoder ausgegeben.  Verwenden Sie die Liste der Parameterkategorien und zugehörigen GUIDs aus der Übersicht der <xref:System.Drawing.Imaging.Encoder>\-Klasse, um die Kategorie der einzelnen Parameter zu ermitteln.  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Eine Windows Forms\-Anwendung  
  
-   <xref:System.Windows.Forms.PaintEventArgs>, ein Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 [Gewusst wie: Auflisten installierter Encoder](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)   
 [Bitmaptypen](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)   
 [Verwenden von Bildencodern und \-decodern in Managed GDI\+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)