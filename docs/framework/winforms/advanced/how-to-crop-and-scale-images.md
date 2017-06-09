---
title: "Gewusst wie: Zuschneiden und Skalieren von Bildern | Microsoft Docs"
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
  - "Bilder [Windows Forms], Zuschneiden"
  - "Bilder [Windows Forms], Skalieren"
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Zuschneiden und Skalieren von Bildern
Die <xref:System.Drawing.Graphics>\-Klasse enthält mehrere <xref:System.Drawing.Graphics.DrawImage%2A>\-Methoden, von denen einige über Parameter für Quell\- und Zielrechtecke verfügen, mit deren Hilfe Sie Bilder zuschneiden und skalieren können.  
  
## Beispiel  
 Im folgenden Beispiel wird aus der Datenträgerdatei Apple.gif ein <xref:System.Drawing.Image>\-Objekt erstellt.  Das gesamte Bild des Apfels wird vom Code in der Originalgröße gezeichnet.  Anschließend ruft der Code die <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode eines <xref:System.Drawing.Graphics>\-Objekts auf, um einen Teil des Apfels in einem Zielrechteck zu zeichnen, das größer als das ursprüngliche Apfelbild ist.  
  
 Die <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode bestimmt den zu zeichnenden Teil des Apfels unter Verwendung des Quellrechtecks. Das Quellrechteck wird durch das dritte, vierte, fünfte und sechste Argument angegeben.  Der Apfel wird in diesem Fall auf 75 Prozent seiner Breite und auf 75 Prozent seiner Höhe zugeschnitten.  
  
 Die <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode bestimmt die Zeichenposition und die Zeichengröße des zugeschnittenen Apfels anhand des Zielrechtecks, das im zweiten Argument angegeben wird.  Das Zielrechteck ist in diesem Fall um 30 Prozent breiter und um 30 Prozent höher als das Originalbild.  
  
 In der folgenden Abbildung ist der Apfel in der Originaldarstellung sowie in der skalierten, zugeschnittenen Darstellung zu sehen.  
  
 ![Zuschneiden und Skalieren](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  Ersetzen Sie `Apple.gif` durch einen im System gültigen Bilddateinamen und \-pfad.  
  
## Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)