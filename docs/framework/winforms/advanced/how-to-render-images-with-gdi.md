---
title: 'Gewusst wie: Darstellen von Bildern mit GDI+'
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
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c0b4c128667cab04ca8ed015b44dae60d11b474
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-render-images-with-gdi"></a>Gewusst wie: Darstellen von Bildern mit GDI+
Sie können [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] zum Rendern von Bildern verwenden, die als Dateien in den Anwendungen vorhanden sind. Hierzu erstellen ein neues Objekt der ein <xref:System.Drawing.Image> Klasse (z. B. <xref:System.Drawing.Bitmap>), erstellen eine <xref:System.Drawing.Graphics> -Objekts, verweist auf die Zeichenoberfläche, die Sie verwenden möchten, und dem Aufrufen der <xref:System.Drawing.Graphics.DrawImage%2A> Methode der <xref:System.Drawing.Graphics> Objekt. Das Bild wird auf die Zeichenoberfläche gezeichnet, die durch die Grafikklasse dargestellt wird. Sie können mithilfe der Bildbearbeitung Bilddateien zur Entwurfszeit erstellen und bearbeiten und diese mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] zur Laufzeit rendern. Weitere Informationen finden Sie unter [Bildbearbeitung für Symbole](/cpp/windows/image-editor-for-icons).  
  
### <a name="to-render-an-image-with-gdi"></a>So rendern Sie ein Bild mit GDI+  
  
1.  Erstellen Sie ein Objekt, das das anzuzeigende Bild darstellt. Dieses Objekt muss ein Member einer Klasse, die von erben <xref:System.Drawing.Image>, wie z. B. <xref:System.Drawing.Bitmap> oder <xref:System.Drawing.Imaging.Metafile>. Ein Beispiel:  
  
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
  
2.  Erstellen einer <xref:System.Drawing.Graphics> Objekt, das die Zeichenoberfläche darstellt, Sie verwenden möchten. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
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
  
3.  Rufen Sie die <xref:System.Drawing.Graphics.DrawImage%2A> Ihres Graphics-Objekts, um das Bild zu rendern. Sie müssen das Bild angeben, das gezeichnet werden soll, und die Koordinaten, an denen es gezeichnet werden soll.  
  
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
 [Erste Schritte mit Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Stifte, Linien und Rechtecke in GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)  
 [Gewusst wie: Zeichnen von Text in Windows Form](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Zeichnen von Linien oder geschlossenen Körpern](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)  
 [Bildbearbeitung für Symbole](/cpp/windows/image-editor-for-icons)
