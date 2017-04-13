---
title: "Gewusst wie: Verwenden einer Farbumwandlungstabelle | Microsoft Docs"
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
  - "Farbumwandlungstabellen, Verwenden"
  - "Farbtabellen, Neuzuordnen von Farben mit"
  - "Benutzerdefinierte Farben, Erstellen mit einer Farbumwandlungstabelle"
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Verwenden einer Farbumwandlungstabelle
Bei der Farbumwandlung werden die Farben in einem Bild entsprechend einer Farbumwandlungstabelle umgewandelt.  Die Farbumwandlungstabelle besteht aus einem Array von <xref:System.Drawing.Imaging.ColorMap>\-Objekten.  Jedes <xref:System.Drawing.Imaging.ColorMap>\-Objekt im Array verfügt über eine <xref:System.Drawing.Imaging.ColorMap.OldColor%2A>\-Eigenschaft und eine <xref:System.Drawing.Imaging.ColorMap.NewColor%2A>\-Eigenschaft.  
  
 Wenn [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ein Bild zeichnet, wird jedes Pixel im Bild mit dem Array der alten Farben verglichen.  Falls die Farbe eines Pixels mit einer alten Farbe übereinstimmt, wird sie in die entsprechende neue Farbe geändert.  Die Farben werden nur zu Renderingzwecken geändert; die Farbwerte des Bildes selbst \(in einem <xref:System.Drawing.Image>\-Objekt oder einem <xref:System.Drawing.Bitmap>\-Objekt gespeichert\) bleiben unverändert.  
  
 Um ein neu zugeordnetes Bild zu zeichnen, initialisieren Sie ein Array von <xref:System.Drawing.Imaging.ColorMap>\-Objekten.  Übergeben Sie dieses Array an die <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A>\-Methode eines <xref:System.Drawing.Imaging.ImageAttributes>\-Objekts und anschließend das <xref:System.Drawing.Imaging.ImageAttributes>\-Objekt an die <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode eines <xref:System.Drawing.Graphics>\-Objekts.  
  
## Beispiel  
 Im folgenden Beispiel wird aus der Datei RemapInput.bmp ein <xref:System.Drawing.Image>\-Objekt erstellt.  Durch den Code wird eine Farbumwandlungstabelle erstellt, die ein einziges <xref:System.Drawing.Imaging.ColorMap>\-Objekt umfasst.  Die <xref:System.Drawing.Imaging.ColorMap.OldColor%2A>\-Eigenschaft des `ColorRemap` \-Objekts ist rot und die <xref:System.Drawing.Imaging.ColorMap.NewColor%2A>\-Eigenschaft blau.  Das Bild wird einmal ohne und einmal mit Farbumwandlung gezeichnet.  Durch die Farbumwandlung werden alle roten Pixel in blaue Pixel geändert.  
  
 In der folgenden Abbildung ist das ursprüngliche Bild auf der linken und das neu zugeordnete Bild auf der rechten Seite zu sehen.  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 [Neueinfärben von Bildern](../../../../docs/framework/winforms/advanced/recoloring-images.md)   
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)