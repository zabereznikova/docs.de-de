---
title: "Gewusst wie: Verbessern der Leistung durch das Vermeiden der automatischen Skalierung | Microsoft Docs"
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
  - "Automatisches Skalieren"
  - "Bilder [Windows Forms], Verbessern der Leistung"
  - "Bilder [Windows Forms], Verwenden ohne automatischer Skalierung"
  - "Leistung, Verbessern für Bilder"
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Verbessern der Leistung durch das Vermeiden der automatischen Skalierung
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] skaliert ein Bild möglicherweise automatisch, während Sie es zeichnen. Dadurch wird die Leistung verringert.  Sie können das Skalieren des Bildes jedoch auch steuern, indem Sie die Abmessungen des Zielrechtecks an die <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode übergeben.  
  
 Beispiel: Durch den folgenden Aufruf der <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode wird für die obere linke Ecke die Position \(50, 30\), jedoch kein Zielrechteck festgelegt.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 Obwohl dies im Hinblick auf die Anzahl der erforderlichen Argumente die einfachste Version der <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode ist, muss sie nicht gleichzeitig auch die effizienteste sein.  Wenn die von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] verwendete Auflösung \(in der Regel 96 Punkte pro Zoll\) von der im <xref:System.Drawing.Image>\-Objekt gespeicherten Auflösung abweicht, wird das Bild von der <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode skaliert.  Angenommen, ein <xref:System.Drawing.Image>\-Objekt hat eine Breite von 216 Pixel und einen gespeicherten Wert für die horizontale Auflösung von 72 Punkten pro Zoll.  Da 216\/72 gleich 3 ist, skaliert <xref:System.Drawing.Graphics.DrawImage%2A> das Bild, sodass es eine Breite von 3 Zoll bei einer Auflösung von 96 Punkten pro Zoll besitzt.  Das heißt, <xref:System.Drawing.Graphics.DrawImage%2A> zeigt ein Bild mit einer Breite von 96 × 3 \= 288 Pixel an.  
  
 Auch wenn Sie eine andere Bildschirmauflösung als 96 Punkte pro Zoll \(DPI\) verwenden, skaliert [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] das Bild in der Regel so, als ob die Bildschirmauflösung 96 Punkte pro Zoll betragen würde.  Dies liegt daran, dass ein <xref:System.Drawing.Graphics>\-Objekt in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] einem Gerätekontext zugeordnet ist. Wenn [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] den Gerätekontext nach der Bildschirmauflösung abfragt, ist das Ergebnis unabhängig von der tatsächlichen Bildschirmauflösung in der Regel 96.  Sie können die automatische Skalierung vermeiden, indem Sie das Zielrechteck in der <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode angeben.  
  
## Beispiel  
 Im folgenden Beispiel wird zweimal dasselbe Bild gezeichnet.  Im ersten Fall wurden Breite und Höhe des Zielrechtecks nicht festgelegt, und das Bild wird automatisch skaliert.  Im zweiten Fall wurden Breite und Höhe des Zielrechtecks \(in Pixel\) so festgelegt, dass sie der Breite und Höhe des Originalbilds entsprechen.  In der folgenden Abbildung wurde das Bild zweimal gerendert.  
  
 ![Skalierte Struktur](../../../../docs/framework/winforms/advanced/media/csscaledtexture1.png "csscaledtexture1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  Ersetzen Sie Texture.jpg mit einem Bildnamen und einem Pfad, die auf Ihrem System gültig sind.  
  
## Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)