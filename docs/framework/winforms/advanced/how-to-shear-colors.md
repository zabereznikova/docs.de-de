---
title: 'Vorgehensweise: Scheren von Farben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: bf645cf88c4905cd5cf47c2a6c7af088fa428c8a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076242"
---
# <a name="how-to-shear-colors"></a>Vorgehensweise: Scheren von Farben
Verzerrens erhöht oder verringert eine Farbe Komponente durch eine Menge, die proportional zu einer anderen Farbe-Komponente. Betrachten Sie beispielsweise die Transformation, in denen die Rotkomponente um die Hälfte der Wert des Blauanteils erhöht wird. Unter einer Transformation würde die Farbe ("0.2", "0.5", "1") werden ("0,7", "0.5", "1"). Der neue Rotanteil ist "0,2" + ((1/2)(1) = 0,7.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei ColorBars4.bmp. Anschließend wird der Code im vorherigen Abschnitt auf jedes Pixel in der Abbildung beschriebene Verbiegen Transformation angewendet.  
  
 Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und die Schertransformation auf der rechten Seite an: 
  
 ![Mit Farbiger Streifen Seite-an-Seite zur Veranschaulichung das ursprüngliche Bild und die Schertransformation von zwei Quadraten.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 Die folgende Tabelle enthält die Farbe Vektoren für die vier Balken, vor und nach der Transformation Verbiegen.  
  
|Ursprünglich|Verbogen|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers. Ersetzen Sie dies `ColorBars.bmp` mit einem Image-Name und Pfad auf Ihrem System ungültig.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Neufärben von Bildern](recoloring-images.md)
