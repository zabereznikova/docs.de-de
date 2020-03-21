---
title: 'Gewusst wie: Darstellen von Bildern mit GDI+'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: fffe1f1052d7323d234985b7e752866f2e89657d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182507"
---
# <a name="how-to-render-images-with-gdi"></a>Gewusst wie: Darstellen von Bildern mit GDI+
Sie können GDI+ verwenden, um Bilder zu rendern, die als Dateien in Ihren Anwendungen vorhanden sind. Dazu erstellen Sie ein neues <xref:System.Drawing.Image> Objekt einer <xref:System.Drawing.Bitmap>Klasse (z. B. ), indem Sie ein <xref:System.Drawing.Graphics> Objekt <xref:System.Drawing.Graphics.DrawImage%2A> erstellen, <xref:System.Drawing.Graphics> das auf die gewünschte Zeichnungsfläche verweist, und die Methode des Objekts aufrufen. Das Bild wird auf die Zeichenoberfläche gezeichnet, die durch die Grafikklasse dargestellt wird. Sie können den Bildeditor verwenden, um Bilddateien zur Entwurfszeit zu erstellen und zu bearbeiten und sie zur Laufzeit mit GDI+ zu rendern. Weitere Informationen finden Sie unter [Bildbearbeitung für Symbole](/cpp/windows/image-editor-for-icons).  
  
### <a name="to-render-an-image-with-gdi"></a>So rendern Sie ein Bild mit GDI+  
  
1. Erstellen Sie ein Objekt, das das anzuzeigende Bild darstellt. Dieses Objekt muss ein Member einer Klasse <xref:System.Drawing.Image>sein, <xref:System.Drawing.Bitmap> die <xref:System.Drawing.Imaging.Metafile>von erbt, z. B. oder . Ein Beispiel:  
  
    ```vb  
    ' Uses the System.Environment.GetFolderPath to get the path to the
    ' current user's MyPictures folder.  
    Dim myBitmap as New Bitmap _  
       (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.MyPictures))  
    ```  
  
    ```csharp  
    // Uses the System.Environment.GetFolderPath to get the path to the
    // current user's MyPictures folder.  
    Bitmap myBitmap = new Bitmap  
       (System.Environment.GetFolderPath  
          (System.Environment.SpecialFolder.MyPictures));  
    ```  
  
    ```cpp  
    // Uses the System.Environment.GetFolderPath to get the path to the
    // current user's MyPictures folder.  
    Bitmap^ myBitmap = gcnew Bitmap  
       (System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::MyPictures));  
    ```  
  
2. Erstellen <xref:System.Drawing.Graphics> Sie ein Objekt, das die Zeichnungsfläche darstellt, die Sie verwenden möchten. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](how-to-create-graphics-objects-for-drawing.md).  
  
    ```vb  
    ' Creates a Graphics object that represents the drawing surface of
    ' Button1.  
    Dim g as Graphics = Button1.CreateGraphics  
    ```  
  
    ```csharp  
    // Creates a Graphics object that represents the drawing surface of
    // Button1.  
    Graphics g = Button1.CreateGraphics();  
    ```  
  
    ```cpp  
    // Creates a Graphics object that represents the drawing surface of
    // Button1.  
    Graphics^ g = button1->CreateGraphics();  
    ```  
  
3. Rufen <xref:System.Drawing.Graphics.DrawImage%2A> Sie das Grafikobjekt auf, um das Bild zu rendern. Sie müssen das Bild angeben, das gezeichnet werden soll, und die Koordinaten, an denen es gezeichnet werden soll.  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [Erste Schritte mit der Grafikprogrammierung](getting-started-with-graphics-programming.md)
- [Gewusst wie: Erstellen von Graphics-Objekten zum Zeichnen](how-to-create-graphics-objects-for-drawing.md)
- [Stifte, Linien und Rechtecke in GDI+](pens-lines-and-rectangles-in-gdi.md)
- [Gewusst wie: Zeichnen von Text in einem Windows Form](how-to-draw-text-on-a-windows-form.md)
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Zeichnen von Linien oder geschlossenen Figuren](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [Bildbearbeitung für Symbole](/cpp/windows/image-editor-for-icons)
