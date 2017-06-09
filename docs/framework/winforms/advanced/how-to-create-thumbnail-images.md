---
title: "Gewusst wie: Erstellen von Miniaturbildern | Microsoft Docs"
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
  - "Bilder [Windows Forms], Erstellen von Miniaturansichten"
  - "Miniaturansichtsbilder, Erstellen"
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Gewusst wie: Erstellen von Miniaturbildern
Eine Miniaturansicht ist eine verkleinerte Darstellung eines Bildes.  Sie können eine Miniaturansicht erstellen, indem Sie die <xref:System.Drawing.Image.GetThumbnailImage%2A>\-Methode eines <xref:System.Drawing.Image>\-Objekts aufrufen.  
  
## Beispiel  
 Im folgenden Beispiel wird aus einer JPG\-Datei ein <xref:System.Drawing.Image>\-Objekt erstellt.  Das ursprüngliche Bild hat eine Breite von 640 Pixel und eine Höhe von 479 Pixel.  Durch den Code wird eine Miniaturansicht mit einer Breite und einer Höhe von 100 Pixel erstellt.  
  
 In der folgenden Abbildung ist die Miniaturansicht dargestellt.  
  
 ![Miniaturbild](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")  
  
> [!NOTE]
>  In diesem Beispiel wird eine Rückrufmethode deklariert, jedoch niemals verwendet.  Dabei werden alle Versionen von GDI\+ unterstützt.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  Gehen Sie folgendermaßen vor, um das Beispiel auszuführen:  
  
1.  Erstellen Sie eine neue Windows Forms\-Anwendung.  
  
2.  Fügen Sie dem Formular den Beispielcode hinzu.  
  
3.  Erstellen Sie einen Handler für das <xref:System.Windows.Forms.Control.Paint>\-Ereignis des Formulars.  
  
4.  Rufen Sie im <xref:System.Windows.Forms.Control.Paint>\-Handler die `GetThumbnail`\-Methode auf, und übergeben Sie `e` für <xref:System.Windows.Forms.PaintEventArgs>.  
  
5.  Suchen Sie eine Bilddatei, von der Sie eine Miniaturansicht erstellen möchten.  
  
6.  Geben Sie in der `GetThumbnail`\-Methode den Pfad und den Dateinamen zum Bild an.  
  
7.  Drücken Sie F5, um das Beispiel auszuführen.  
  
     Ein Miniaturbild mit der Größe 100x100 wird im Formular angezeigt.  
  
## Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)