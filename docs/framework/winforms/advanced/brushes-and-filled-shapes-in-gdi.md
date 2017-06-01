---
title: "Pinsel und gef&#252;llte Formen in GDI+ | Microsoft Docs"
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
  - "Pinsel, GDI+"
  - "Pinsel, Farbverlauf"
  - "Gefüllte Formen, GDI+"
  - "GDI+, Pinsel"
  - "GDI+, Gefüllte Formen"
  - "Farbverlaufspinsel"
  - "Formen, GDI+"
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Pinsel und gef&#252;llte Formen in GDI+
Eine geschlossene Form, z. B.ein Rechteck oder eine Ellipse, besteht aus einem Umriss und einer Innenfläche.  Der Umriss wird mit einem Stift gezeichnet und die Innenfläche mit einem Pinsel gefüllt.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet mehrere Pinselklassen, um die Innenflächen geschlossener Formen zu füllen: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush> und <xref:System.Drawing.Drawing2D.PathGradientBrush>.  Alle diese Klassen erben von der <xref:System.Drawing.Brush>\-Klasse.  Die folgende Abbildung zeigt ein Rechteck, das mit einem Pinsel für eine Volltonfarbe gefüllt wurde, und eine Ellipse, die mit einem Pinsel für eine Schraffur gefüllt wurde.  
  
 ![Ausgefüllte Formen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.png "Aboutgdip02\_art17")  
  
## Pinsel für Volltonfarben  
 Um eine geschlossene Form zu füllen, benötigen Sie eine Instanz der <xref:System.Drawing.Graphics>\-Klasse sowie <xref:System.Drawing.Brush>.  Die Instanz der <xref:System.Drawing.Graphics>\-Klasse stellt Methoden, wie <xref:System.Drawing.Graphics.FillRectangle%2A> und <xref:System.Drawing.Graphics.FillEllipse%2A>, bereit, und in <xref:System.Drawing.Brush> werden Attribute für die Füllung, beispielsweise Farbe und Muster, gespeichert.  <xref:System.Drawing.Brush> wird als eines der Argumente an die Füllmethode übergeben.  Im folgenden Codebeispiel wird gezeigt, wie Sie eine Ellipse mit der Volltonfarbe Rot füllen.  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  Im vorangehenden Beispiel hat der Pinsel den Typ <xref:System.Drawing.SolidBrush>, der von <xref:System.Drawing.Brush> erbt.  
  
## Pinsel für Schraffuren  
 Wenn Sie eine Form mit einem Pinsel für eine Schraffur füllen, geben Sie eine Vordergrund\- und eine Hintergrundfarbe sowie einen Schraffurstil an.  Die Vordergrundfarbe ist die Farbe der Schraffur.  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] stellt mehr als 50 Schraffurstile bereit. In der folgenden Abbildung sind die drei Stile <xref:System.Drawing.Drawing2D.HatchStyle>, <xref:System.Drawing.Drawing2D.HatchStyle> und <xref:System.Drawing.Drawing2D.HatchStyle> dargestellt.  
  
 ![Ausgefüllte Formen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.png "Aboutgdip02\_art18")  
  
## Pinsel für Texturen  
 Mit einem Pinsel für eine Textur können Sie eine Form mit einem Muster füllen, das in einer Bitmap gespeichert ist.  Angenommen, das folgende Bild ist in der Datenträgerdatei `MyTexture.bmp` gespeichert.  
  
 ![Ausgefüllte Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.png "Aboutgdip02\_Art19")  
  
 Im folgenden Codebeispiel wird gezeigt, wie eine Ellipse durch Wiederholen des in `MyTexture.bmp` gespeicherten Bildes gefüllt wird.  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 In der folgenden Abbildung ist die ausgefüllte Ellipse dargestellt.  
  
 ![Ausgefüllte Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.png "AboutGdip02\_Art20")  
  
## Pinsel für Farbverläufe  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet zwei Arten von Farbverlaufpinseln: linear und pfadbezogen.  Sie können mit einem Pinsel für einen linearen Farbverlauf eine Form mit Farbe füllen, die in horizontaler, vertikaler oder diagonaler Richtung schrittweise in eine andere Farbe übergeht.  Im folgenden Codebeispiel wird eine Ellipse mit einem Pinsel für einen horizontalen Farbverlauf gefüllt, bei dem die Farbe vom linken Rand der Ellipse zum rechten von Blau in Grün übergeht.  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 In der folgenden Abbildung ist die ausgefüllte Ellipse dargestellt.  
  
 ![Ausgefüllte Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.png "AboutGdip02\_Art21")  
  
 Sie können einen Pinsel für einen pfadbezogenen Farbverlauf konfigurieren, um einen Farbübergang vom Mittelpunkt einer Form aus nach außen zu erstellen.  
  
 ![Ausgefüllte Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.png "AboutGdip02\_Art22")  
  
 Pinsel für pfadbezogene Farbverläufe lassen sich sehr flexibel verwenden.  Der Farbverlaufpinsel, der zum Füllen des Dreiecks in der folgenden Abbildung verwendet wurde, erzeugt einen Farbübergang von Rot in der Mitte des Dreiecks zu den drei unterschiedlichen Farben in den verschiedenen Ecken des Dreiecks.  
  
 ![Ausgefüllte Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.png "AboutGdip02\_Art23")  
  
## Siehe auch  
 <xref:System.Drawing.SolidBrush?displayProperty=fullName>   
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=fullName>   
 <xref:System.Drawing.TextureBrush?displayProperty=fullName>   
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=fullName>   
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Gewusst wie: Zeichnen eines ausgefüllten Rechtecks in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)   
 [Gewusst wie: Zeichnen einer ausgefüllten Ellipse in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)