---
title: "Pinsel und gefüllte Formen in GDI+"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 01d7359499c858ad7c4f1da2fa24f18e801bb324
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="brushes-and-filled-shapes-in-gdi"></a>Pinsel und gefüllte Formen in GDI+
Eine geschlossene Form, z. B. ein Rechteck oder eine Ellipse besteht aus einer Gliederung und dem inneren. Die Kontur mit einem Stift gezeichnet, und das innere mit einem Pinsel gefüllt ist. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]bietet mehrere für die Innenflächen geschlossene Formen füllen: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, und <xref:System.Drawing.Drawing2D.PathGradientBrush>. Alle diese Klassen erben von der <xref:System.Drawing.Brush> Klasse. Die folgende Abbildung zeigt ein Rechteck mit eines Pinsels in Volltonfarbe gefüllt und eine Ellipse, die mit einem Schraffurpinsel gefüllt.  
  
 ![Gefüllte Formen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")  
  
## <a name="solid-brushes"></a>Einfarbig Pinsel  
 Um eine geschlossene Form zu füllen, benötigen Sie eine Instanz von der <xref:System.Drawing.Graphics> Klasse und ein <xref:System.Drawing.Brush>. Die Instanz von der <xref:System.Drawing.Graphics> Klasse enthält Methoden, wie z. B. <xref:System.Drawing.Graphics.FillRectangle%2A> und <xref:System.Drawing.Graphics.FillEllipse%2A>, und die <xref:System.Drawing.Brush> speichert Attribute für die Füllung, z. B. Farbe und Muster. Die <xref:System.Drawing.Brush> als eines der Argumente an die Füllmethode übergeben wird. Im folgenden Codebeispiel wird veranschaulicht, wie eine Ellipse, die mit einer Volltonfarbe Rot füllen.  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  Im vorherigen Beispiel ist der Pinsel, der vom Typ <xref:System.Drawing.SolidBrush>, erbt die <xref:System.Drawing.Brush>.  
  
## <a name="hatch-brushes"></a>Schraffurpinsel  
 Wenn Sie eine Form mit einem Schraffurpinsel ausfüllen, geben Sie eine Vordergrundfarbe, eine Hintergrundfarbe und ein Schraffurart. Die Vordergrundfarbe ist die Farbe der Schraffur.  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]enthält mehr als 50 Schraffur Stile; sind die drei Stile in der folgenden Abbildung dargestellten <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, und <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.  
  
 ![Gefüllte Formen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")  
  
## <a name="texture-brushes"></a>Strukturpinsel  
 Mit einem Texturpinsel können Sie eine Form mit einem Muster, die in einer Bitmap gespeichert ausfüllen. Nehmen wir beispielsweise an, das folgende Bild befindet sich in einer Datenträgerdatei mit dem Namen `MyTexture.bmp`.  
  
 ![Gefüllt Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Ellipse, die durch die Wiederholung des Bilds in gespeicherten gefüllt `MyTexture.bmp`.  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 Die folgende Abbildung zeigt das ausgefüllte Ellipse.  
  
 ![Gefüllt Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")  
  
## <a name="gradient-brushes"></a>Farbverlaufspinsel  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]bietet zwei Arten von Farbverlaufspinsel: linear und Pfad. Sie können einen linearen Farbverlaufspinsel verwenden, eine Form Farbe gefüllt, die Änderungen schrittweise, während Sie über die Form verschieben, horizontal, vertikal oder diagonal angezeigt. Im folgenden Codebeispiel wird veranschaulicht, wie eine Ellipse, die mit einem horizontalen Farbverlaufspinsel zu füllen, die von Blau in Grün ändern, wie Sie vom linken Rand der Ellipse, die an den rechten Rand verschieben.  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 Die folgende Abbildung zeigt das ausgefüllte Ellipse.  
  
 ![Gefüllt Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")  
  
 Pfadfarbverlaufs kann konfiguriert werden, um Farbe zu ändern, wie Sie von der Mitte einer Form auf den Rand verschieben.  
  
 ![Gefüllt Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")  
  
 Pfad Farbverlaufspinsel sind sehr flexibel. Die Farbverlaufspinsel verwendet, um das Dreieck in der folgenden Abbildung Änderungen allmählich von Rot in der Mitte auf jedem der drei verschiedenen Farben an den Scheitelpunkten zu füllen.  
  
 ![Gefüllt Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Gewusst wie: Zeichnen eines ausgefüllten Rechtecks in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)  
 [Gewusst wie: Zeichnen einer ausgefüllten Ellipse in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)
