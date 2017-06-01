---
title: "Gewusst wie: Verwenden des Interpolationsmodus zum Steuern der Bildqualit&#228;t w&#228;hrend der Skalierung | Microsoft Docs"
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
  - "Bilder [Windows Forms], Steuern der Qualität"
  - "Bilder [Windows Forms], Skalieren"
  - "Interpolationsmodus, Steuern der Bildqualität"
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Verwenden des Interpolationsmodus zum Steuern der Bildqualit&#228;t w&#228;hrend der Skalierung
Der Interpolationsmodus eines <xref:System.Drawing.Graphics>\-Objekts beeinflusst die Art und Weise, wie Bilder in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] skaliert \(gestreckt bzw. verkleinert\) werden.  Durch die <xref:System.Drawing.Drawing2D.InterpolationMode>\-Enumeration werden mehrere Interpolationsmodi definiert, von denen einige im Folgenden aufgelistet sind:  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
 Zum Strecken eines Bildes muss jedes Pixel des Originalbilds einer Gruppe von Pixeln im größeren Bild zugeordnet werden.  Zum Verkleinern eines Bildes müssen Pixelgruppen im Originalbild einzelnen Pixeln im kleineren Bild zugeordnet werden.  Die Qualität eines skalierten Bildes hängt von der Effizienz der Algorithmen ab, durch die diese Zuordnungen berechnet werden.  Algorithmen, die höherwertige skalierte Bilder produzieren, erfordern tendenziell eine höhere Verarbeitungszeit.  Die Einstellung <xref:System.Drawing.Drawing2D.InterpolationMode> aus der vorangehenden Liste entspricht dem Modus mit der niedrigsten und die Einstellung <xref:System.Drawing.Drawing2D.InterpolationMode> dem Modus mit der höchsten Qualität.  
  
 Um den Interpolationsmodus festzulegen, weisen Sie der <xref:System.Drawing.Graphics.InterpolationMode%2A>\-Eigenschaft eines <xref:System.Drawing.Graphics>\-Objekts einen der Member der <xref:System.Drawing.Drawing2D.InterpolationMode>\-Enumeration zu.  
  
## Beispiel  
 Im folgenden Beispiel wird ein Bild gezeichnet, das anschließend mit drei verschiedenen Interpolationsmodi verkleinert wird.  
  
 In der folgenden Abbildung sind das Originalbild sowie die drei kleineren Bilder dargestellt.  
  
 ![Bild mit unterschiedlichen Interpolationseinstellungen](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)