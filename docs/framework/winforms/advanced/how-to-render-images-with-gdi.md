---
title: 'Vorgehensweise: Darstellen von Bildern mit GDI +'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: d2c626f46862e5fdc7c51b509a6419a3d67c4102
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702827"
---
# <a name="how-to-render-images-with-gdi"></a>Vorgehensweise: Darstellen von Bildern mit GDI +
Sie können [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] zum Rendern von Bildern verwenden, die als Dateien in den Anwendungen vorhanden sind. Hierzu erstellen ein neues Objekt des ein <xref:System.Drawing.Image> Klasse (z. B. <xref:System.Drawing.Bitmap>), wodurch eine <xref:System.Drawing.Graphics> -Objekts einen Verweis auf die Zeichenoberfläche, die Sie verwenden möchten, und dem Aufrufen der <xref:System.Drawing.Graphics.DrawImage%2A> -Methode der der <xref:System.Drawing.Graphics> Objekt. Das Bild wird auf die Zeichenoberfläche gezeichnet, die durch die Grafikklasse dargestellt wird. Sie können mithilfe der Bildbearbeitung Bilddateien zur Entwurfszeit erstellen und bearbeiten und diese mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] zur Laufzeit rendern. Weitere Informationen finden Sie unter [Bildbearbeitung für Symbole](/cpp/windows/image-editor-for-icons).  
  
### <a name="to-render-an-image-with-gdi"></a>So rendern Sie ein Bild mit GDI+  
  
1.  Erstellen Sie ein Objekt, das das anzuzeigende Bild darstellt. Dieses Objekt muss ein Member einer Klasse, die von erbt sein <xref:System.Drawing.Image>, z. B. <xref:System.Drawing.Bitmap> oder <xref:System.Drawing.Imaging.Metafile>. Ein Beispiel:  
  
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
  
2.  Erstellen Sie eine <xref:System.Drawing.Graphics> Objekt, das die Zeichenoberfläche darstellt, Sie verwenden möchten. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](how-to-create-graphics-objects-for-drawing.md).  
  
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
  
3.  Rufen Sie die <xref:System.Drawing.Graphics.DrawImage%2A> der Grafikobjekte auf das Bild zu rendern. Sie müssen das Bild angeben, das gezeichnet werden soll, und die Koordinaten, an denen es gezeichnet werden soll.  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a>Siehe auch
- [Erste Schritte mit Grafikprogrammierung](getting-started-with-graphics-programming.md)
- [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](how-to-create-graphics-objects-for-drawing.md)
- [Stifte, Linien und Rechtecke in GDI+](pens-lines-and-rectangles-in-gdi.md)
- [Vorgehensweise: Zeichnen von Text in einem Windows Form](how-to-draw-text-on-a-windows-form.md)
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Zeichnen von Linien oder geschlossenen Körpern](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [Bildbearbeitung für Symbole](/cpp/windows/image-editor-for-icons)
