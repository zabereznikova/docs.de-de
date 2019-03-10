---
title: Pinsel und gefüllte Formen in GDI+
ms.date: 03/30/2017
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
ms.openlocfilehash: fc6d6857e912ba14fca382eb49373655004534d5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720942"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a>Pinsel und gefüllte Formen in GDI+
Eine geschlossene Form, wie z. B. ein Rechteck oder eine Ellipse, besteht aus einer Gliederung und einem inneren. Die Kontur mit einem Stift gezeichnet wird, und das innere wird mit einem Pinsel gefüllt. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet mehrere für füllt das Innere der geschlossene Formen: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, und <xref:System.Drawing.Drawing2D.PathGradientBrush>. Alle diese Klassen erben von der <xref:System.Drawing.Brush> Klasse. Die folgende Abbildung zeigt ein Rechteck mit einer Volltonfarbe gefüllt, und eine Ellipse mit einer Schraffurpinsel gefüllt.  
  
 ![Gefüllte Formen](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")  
  
## <a name="solid-brushes"></a>Pinsel mit Volltonfarbe  
 Um eine geschlossene Form zu füllen, benötigen Sie eine Instanz von der <xref:System.Drawing.Graphics> Klasse und ein <xref:System.Drawing.Brush>. Die Instanz von der <xref:System.Drawing.Graphics> Klasse stellt Methoden bereit, z. B. <xref:System.Drawing.Graphics.FillRectangle%2A> und <xref:System.Drawing.Graphics.FillEllipse%2A>, und die <xref:System.Drawing.Brush> speichert Attribute für die Füllung, z. B. Farbe und Muster. Die <xref:System.Drawing.Brush> als eines der Argumente an die Fill-Methode übergeben wird. Im folgenden Codebeispiel wird veranschaulicht, wie eine Ellipse mit einer Volltonfarbe Rot gefüllt wird.  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  Im vorherigen Beispiel ist der Pinsel vom Typ <xref:System.Drawing.SolidBrush>, erbt von <xref:System.Drawing.Brush>.  
  
## <a name="hatch-brushes"></a>Schraffurpinsel  
 Wenn Sie eine Form mit einem Schraffurpinsel ausfüllen, geben Sie eine Vordergrundfarbe, Hintergrundfarbe und einer Schraffurart. Die Vordergrundfarbe ist die Farbe der Schraffur an.  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] enthält mehr als 50 Schraffur Stile; sind die drei Stile, die in der folgenden Abbildung dargestellten <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, und <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.  
  
 ![Gefüllte Formen](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")  
  
## <a name="texture-brushes"></a>Strukturpinsel  
 Mit einem Texturpinsel können Sie eine Form mit einem Muster, die in einer Bitmap gespeichert ausfüllen. Nehmen wir beispielsweise an, in der folgende Abbildung befindet sich in einer Datenträgerdatei mit dem Namen `MyTexture.bmp`.  
  
 ![Form gefüllt](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie eine Ellipse zu füllen, Bild in gespeicherten `MyTexture.bmp`.  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 Die folgende Abbildung zeigt die ausgefüllte Ellipse.  
  
 ![Form gefüllt](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")  
  
## <a name="gradient-brushes"></a>Pinsel mit Farbverlauf  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] stellt zwei Arten von Farbverlaufspinsel bereit: linear und Pfad. Sie können einen linearen Farbverlaufspinsel verwenden, eine Form mit Farbe zu füllen, die Änderungen schrittweise, wie Sie über die Form verschieben, horizontal, vertikal oder diagonal angezeigt. Im folgenden Codebeispiel wird veranschaulicht, wie Sie eine Ellipse mit einem horizontalen Farbverlaufspinsel zu füllen, die sich von Blau in Grün ändern, wie der Wechsel vom linken Rand der Ellipse am rechten Rand wird.  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 Die folgende Abbildung zeigt die ausgefüllte Ellipse.  
  
 ![Form gefüllt](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")  
  
 Ein Pinsel mit Farbverlauf kann konfiguriert werden, um Farbe zu ändern, wenn Sie von der Mitte des eine Form auf den Rand bewegen.  
  
 ![Form gefüllt](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")  
  
 Pinsel mit Farbverlauf Pfad sind recht flexibel. Die Farbverlaufspinsel verwendet, um das Dreieck in der folgenden Abbildung ändern allmählich von Rot in der Mitte jeder der drei verschiedenen Farben an den Vertices zu füllen.  
  
 ![Form gefüllt](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [Linien, Kurven und Formen](lines-curves-and-shapes.md)
- [Vorgehensweise: Zeichnen eines ausgefüllten Rechtecks in Windows Forms](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [Vorgehensweise: Zeichnen einer ausgefüllten Ellipse in einem Windows Form](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
