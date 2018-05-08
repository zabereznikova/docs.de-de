---
title: 'Gewusst wie: Verwenden einer Farbumwandlungstabelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: ba763cc7960e71c6fc705d40eefdbde163d06181
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-color-remap-table"></a>Gewusst wie: Verwenden einer Farbumwandlungstabelle
Neuzuordnen wird der Vorgang des Konvertierens der Farben in einem Bild entsprechend einer Farbumwandlungstabelle. Die Farbumwandlungstabelle ist ein Array von <xref:System.Drawing.Imaging.ColorMap> Objekte. Jede <xref:System.Drawing.Imaging.ColorMap> Objekt im Array verfügt über eine <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> Eigenschaft und eine <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> Eigenschaft.  
  
 Wenn [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] zeichnet ein Bild, aus jedem Pixel des Bilds in das Array der alten Farben verglichen wird. Wenn ein Pixel Farbe einer alten Farbe übereinstimmt, wird dessen Farbe auf die entsprechende neue Farbe geändert. Die Farben sind nur für das Rendering geändert – die Farbwerte, der das Bild selbst (gespeichert ein <xref:System.Drawing.Image> oder <xref:System.Drawing.Bitmap> Objekt) werden nicht geändert.  
  
 Um eine neu zugeordnete Bild gezeichnet werden soll, initialisieren Sie ein Array von <xref:System.Drawing.Imaging.ColorMap> Objekte. Dieses Arrays zum Übergeben der <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> Methode ein <xref:System.Drawing.Imaging.ImageAttributes> Objekts, und übergeben Sie dann der <xref:System.Drawing.Imaging.ImageAttributes> -Objekt an der <xref:System.Drawing.Graphics.DrawImage%2A> Methode eine <xref:System.Drawing.Graphics> Objekt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei RemapInput.bmp. Der Code erstellt eine Farbumwandlungstabelle, die aus einer einzelnen besteht <xref:System.Drawing.Imaging.ColorMap> Objekt. Die <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> Eigenschaft von der `ColorRemap` Objekt ist rot, und die <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> Eigenschaft ist Blau. Das Bild ist gezeichneten einmal ohne und einmal mit der neuzuordnung. Der neuzuordnung ändert die roten Pixel Blau.  
  
 Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und das neu zugeordnete Bild auf der rechten Seite.  
  
 ![Farbe Neuzuordnung](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch  
 [Neufärben von Bildern](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
