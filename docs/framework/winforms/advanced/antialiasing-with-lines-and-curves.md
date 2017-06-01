---
title: "Antialiasing bei Linien und Kurven | Microsoft Docs"
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
  - "Antialiasing"
  - "Antialiasing, Glättungsmodi"
  - "GDI+, Antialiasing"
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Antialiasing bei Linien und Kurven
Wenn Sie [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] zum Zeichnen einer Linie verwenden, brauchen Sie nur den Anfangs\- und Endpunkt der Linie anzugeben, ohne weitere Informationen zu den einzelnen Pixel in der Linie bereitstellen zu müssen.  Welche Pixel zum Anzeigen der Linie auf einem bestimmten Anzeigegerät erforderlich sind, ermittelt [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] zusammen mit der Bildschirmtreibersoftware.  
  
## Aliasing  
 Betrachten Sie die gerade rote Linie vom Punkt \(4, 2\) zum Punkt \(16, 10\).  Das Koordinatensystem hat seinen Ursprung in der linken oberen Ecke, die Maßeinheit ist Pixel.  Außerdem zeigt die x‑Achse nach rechts und die y‑Achse nach unten.  Die folgende Abbildung zeigt eine vergrößerte Ansicht der roten Linie auf einem mehrfarbigen Hintergrund.  
  
 ![Linie ohne Antialiasing](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.png "AboutGdip02\_Art33")  
  
 Die roten Pixel, mit denen die Linie gerendert wird, sind nicht transparent.  Die Linie enthält keine teilweise transparenten Pixel.  Durch diese Art von Linienrendering sieht die Linie gezackt aus, als ob sie Stufen enthielte.  Diese Technik der Darstellung einer Linie mit Stufen wird als Aliasing bezeichnet. Die "Treppe" ist ein Alias für die theoretische Linie.  
  
## Antialiasing  
 Bei einer ausgereifteren Technik zum Rendern einer Linie werden teilweise transparente Pixel zusammen mit deckenden Pixel verwendet.  Für die Pixel wird reines Rot oder eine Mischung aus Rot und der Hintergrundfarbe festgelegt, je nachdem, wie nahe sie an der Linie liegen.  Diese Art der Darstellung wird als Antialiasing bezeichnet und ergibt eine Linie, die vom menschlichen Auge als glatter wahrgenommen wird.  Die folgende Abbildung zeigt, wie bestimmte Pixel mit dem Hintergrund vermischt werden, um eine Linie mit Antialiasing zu erstellen.  
  
 ![Antialiasing bei einer Linie](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.png "AboutGdip02\_Art34")  
  
 Das auch als Glättung bezeichnete Antialiasing kann außerdem auf Kurven angewendet werden.  Die folgende Abbildung zeigt eine vergrößerte Ansicht einer geglätteten Ellipse.  
  
 ![Antialiasing bei Kurven](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.png "AboutGdip02\_Art35")  
  
 Die folgende Abbildung zeigt die gleiche Ellipse in ihrer tatsächlichen Größe, einmal ohne und einmal mit Antialiasing.  
  
 ![Antialiasingbeispiel](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02\_Art36")  
  
 Um Linien und Kurven mit Antialiasing zu zeichnen, erstellen Sie eine Instanz der <xref:System.Drawing.Graphics>\-Klasse und legen für ihre <xref:System.Drawing.Graphics.SmoothingMode%2A>\-Eigenschaft den Wert <xref:System.Drawing.Drawing2D.SmoothingMode> oder <xref:System.Drawing.Drawing2D.SmoothingMode> fest.  Rufen Sie dann eine der Zeichenmethoden derselben <xref:System.Drawing.Graphics>\-Klasse auf.  
  
 [!code-csharp[LinesCurvesAndShapes#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## Siehe auch  
 <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=fullName>   
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Gewusst wie: Verwenden der Bildkantenglättung mit Text](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)