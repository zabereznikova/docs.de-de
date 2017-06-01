---
title: "Zuschneiden und Skalieren von Bildern in GDI+ | Microsoft Docs"
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
  - "Komprimieren von Daten, Bilder"
  - "GDI+, Zuschneiden von Bildern"
  - "GDI+, Skalieren von Bildern"
  - "Bilder [Windows Forms], Komprimierung"
  - "Bilder [Windows Forms], Zuschneiden"
  - "Bilder [Windows Forms], Erweiterung"
  - "Bilder [Windows Forms], Skalieren"
  - "Rechtecke, Ziel"
  - "Rechtecke, Quelle"
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Zuschneiden und Skalieren von Bildern in GDI+
Mithilfe der <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode der <xref:System.Drawing.Graphics>\-Klasse können Sie Vektor\- und Rasterbilder zeichnen und positionieren.  Da es sich bei <xref:System.Drawing.Graphics.DrawImage%2A> um eine überladene Methode handelt, können Sie auf verschiedene Weisen Argumente für die Methode bereitstellen.  
  
## DrawImage\-Varianten  
 Eine Variante der <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode erhält <xref:System.Drawing.Bitmap> und <xref:System.Drawing.Rectangle>.  Das Rechteck gibt die Zielposition für den Zeichenvorgang an, d. h. das Rechteck, in dem das Bild gezeichnet werden soll.  Weicht die Größe des Zielrechtecks von der Größe des Originalbildes ab, wird das Bild durch Skalierung in das Zielrechteck eingepasst.  Im folgenden Codebeispiel wird dasselbe Bild dreimal gezeichnet: einmal ohne Skalierung, einmal mit einer Ausdehnung und einmal mit einer Komprimierung:  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 Die folgende Abbildung zeigt diese drei Bilder.  
  
 ![Skalieren](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.png "AboutGdip03\_Art06")  
  
 Manche Varianten der <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode haben sowohl einen Parameter für ein Quellrechteck als auch einen Parameter für ein Zielrechteck.  Der Parameter für das Quellrechteck gibt den Teil des Originalbildes an, der gezeichnet werden soll.  Der Parameter für das Zielrechteck gibt das Rechteck an, in dem dieser Teil des Bildes gezeichnet werden soll.  Weicht die Größe des Zielrechtecks von der Größe des Quellrechtecks ab, wird das Bild durch Skalierung in das Zielrechteck eingepasst.  
  
 Im folgenden Codebeispiel wird ein <xref:System.Drawing.Bitmap>\-Objekt aus der Datei Runner.jpg erstellt.  Das gesamte Bild wird an Position \(0, 0\) ohne Skalierung gezeichnet.  Anschließend wird ein kleiner Teil des Bildes zweimal gezeichnet: einmal mit Komprimierung und einmal mit Ausdehnung.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 Die folgende Abbildung zeigt das unskalierte Bild sowie den komprimierten und den ausgedehnten Teil des Bildes.  
  
 ![Zuschneiden und Skalieren](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.png "AboutGdip03\_Art07")  
  
## Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)