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
ms.openlocfilehash: b390caf644b86de0001387b2c3f41503fd34759a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593208"
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
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler. Ersetzen Sie dies `ColorBars.bmp` mit einem Image-Name und Pfad auf Ihrem System ungültig.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Neufärben von Bildern](recoloring-images.md)
