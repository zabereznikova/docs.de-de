---
title: "Gewusst wie: Ausf&#252;llen einer Form mit einer Bildstruktur | Microsoft Docs"
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
  - "Bitmaps [Windows Forms], Verwenden von Struktur"
  - "Bilder [Windows Forms], Verwenden mit Pinseln"
  - "Formen, Füllen mit Bildern"
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Ausf&#252;llen einer Form mit einer Bildstruktur
Sie können eine geschlossene Form mit einer Struktur ausfüllen, indem Sie die <xref:System.Drawing.Image>\-Klasse und die <xref:System.Drawing.TextureBrush>\-Klasse verwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Ellipse mit einem Bild ausgefüllt.  Im Code wird ein <xref:System.Drawing.Image>\-Objekt erstellt und dann die Adresse dieses <xref:System.Drawing.Image>\-Objekts als Argument an einen <xref:System.Drawing.TextureBrush.%23ctor%2A>\-Konstruktor übergeben.  Durch die dritte Anweisung wird das Bild skaliert, und durch die vierte Anweisung wird die Ellipse mit aufeinander folgenden Kopien des skalierten Bildes ausgefüllt.  
  
 Im folgenden Code enthält die <xref:System.Drawing.TextureBrush.Transform%2A>\-Eigenschaft die Transformation, die vor dem Zeichnen auf das Bild angewendet wird.  Angenommen, das ursprüngliche Bild hat eine Breite von 640 Pixeln und eine Höhe von 480 Pixeln.  Durch die Transformation wird das Bild auf 75 × 75 Pixel verkleinert, indem horizontale und vertikale Skalierungswerte festgelegt werden.  
  
> [!NOTE]
>  Im folgenden Beispiel ist die Größe des Bildes 75 × 75 und die der Ellipse 150 × 250.  Da das Bild kleiner als die Ellipse ist, die es ausfüllt, wird die Ellipse mit dem Bild gekachelt.  Kacheln bedeutet, dass das Bild so oft horizontal und vertikal wiederholt wird, bis die Begrenzung der Form erreicht ist.  Weitere Informationen über das Kacheln finden Sie unter [Gewusst wie: Kacheln einer Form mit einem Bild](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 [Verwenden eines Pinsels zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)