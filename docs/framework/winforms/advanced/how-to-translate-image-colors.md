---
title: 'Gewusst wie: Verschieben von Bildfarben'
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
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c21d20b631d8e0cf68e370dd43b3f5e92144b09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-translate-image-colors"></a>Gewusst wie: Verschieben von Bildfarben
Eine Übersetzung Fügt einen Wert für eine oder mehrere der vier Farbkomponenten. Die Farbe Matrix Einträge, die Übersetzungen darstellen, werden in der folgenden Tabelle angegeben.  
  
|Die Komponente zu übersetzende|Matrixeintrag|  
|--------------------------------|------------------|  
|Rot|[4][0]|  
|Grün|[4][1]|  
|Blau|[4][2]|  
|Alpha|[4][3]|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei ColorBars.bmp. Der Code fügt dann 0,75 an die rote Komponente jedes Pixels in der Abbildung. Das ursprüngliche Image wird zusammen mit den transformierten Bild gezeichnet.  
  
 Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und das transformierte Bild auf der rechten Seite.  
  
 ![Verschieben von Farben](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")  
  
 Die folgende Tabelle enthält die Vektoren Farbe für die vier Balken vor und nach die rote Übersetzung. Beachten Sie, weil der Maximalwert für eine Komponente Farbe 1 ist, nicht die rote Komponente in der zweiten Zeile geändert wird. (Entsprechend ist der minimale Wert für eine Komponente Farbe 0.)  
  
|Ursprünglich|Übersetzt|  
|--------------|----------------|  
|Schwarz (0, 0, 0, 1)|(0.75, 0, 0, 1)|  
|Rot (1, 0, 0, 1)|(1, 0, 0, 1)|  
|Grün (0, 1, 0, 1)|(0.75, 1, 0, 1)|  
|Blau (0, 0, 1, 1)|(0.75, 0, 1, 1)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers. Ersetzen Sie `ColorBars.bmp` mit einem Dateinamen und Pfad, die auf Ihrem System gültig sind.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Neufärben von Bildern](../../../../docs/framework/winforms/advanced/recoloring-images.md)
