---
title: "Gewusst wie: Laden und Anzeigen von Metadateien | Microsoft Docs"
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
  - "Beispiele [Windows Forms], Metadateien"
  - "Metadateien, Anzeigen"
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Laden und Anzeigen von Metadateien
Die <xref:System.Drawing.Imaging.Metafile>\-Klasse, die von der <xref:System.Drawing.Image>\-Klasse erbt, enthält Methoden für das Aufzeichnen, Anzeigen und Überprüfen von Vektorbildern.  
  
## Beispiel  
 Für die Anzeige eines Vektorbilds \(Metadatei\) auf dem Bildschirm benötigen Sie ein <xref:System.Drawing.Imaging.Metafile>\-Objekt und ein <xref:System.Drawing.Graphics>\-Objekt.  Übergeben Sie den Namen einer Datei \(oder eines Streams\) an einen <xref:System.Drawing.Imaging.Metafile>\-Konstruktor.  Erstellen Sie ein <xref:System.Drawing.Imaging.Metafile>\-Objekt, und übergeben Sie dieses <xref:System.Drawing.Imaging.Metafile>\-Objekt an die <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode eines <xref:System.Drawing.Graphics>\-Objekts.  
  
 Im Beispiel wird erst ein <xref:System.Drawing.Imaging.Metafile>\-Objekt aus einer EMF\-Datei \(Enhanced Metafile\) erstellt, und anschließend wird das Bild mit der oberen linken Ecke an der Position \(60, 10\) gezeichnet.  
  
 In der folgenden Abbildung wird gezeigt, wie die Metadatei an der angegebenen Position gezeichnet wird.  
  
 ![Bildposition](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)