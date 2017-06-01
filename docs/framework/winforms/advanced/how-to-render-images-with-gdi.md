---
title: "Gewusst wie: Darstellen von Bildern mit GDI+ | Microsoft Docs"
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
  - "GDI+, Darstellen vorhandener Bilder"
  - "Bilder [Windows Forms], Erstellen"
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Darstellen von Bildern mit GDI+
Mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können Bilder gerendert werden, die als Dateien in Anwendungen vorliegen.  Zu diesem Zweck erstellen Sie ein neues Objekt einer <xref:System.Drawing.Image>\-Klasse \(beispielsweise <xref:System.Drawing.Bitmap>\), indem Sie ein <xref:System.Drawing.Graphics>\-Objekt erstellen, das sich auf die gewünschte Zeichnungsoberfläche bezieht, und die <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode des <xref:System.Drawing.Graphics>\-Objekts aufrufen.  Das Bild wird auf der von der Grafikklasse dargestellten Zeichnungsoberfläche gezeichnet.  Mit dem Grafik\-Editor können Sie Bilddateien zur Entwurfszeit erstellen und bearbeiten, die mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] zur Laufzeit gerendert werden.  Weitere Informationen finden Sie unter [Image Editor for Icons](../Topic/Image%20Editor%20for%20Icons.md).  
  
### So rendern Sie Bilder mit GDI\+  
  
1.  Erstellen Sie ein Objekt, das das anzuzeigende Bild darstellt.  Dieses Objekt muss ein Member einer Klasse sein, die von <xref:System.Drawing.Image> erbt, beispielsweise <xref:System.Drawing.Bitmap> oder <xref:System.Drawing.Imaging.Metafile>.  Beispiel:  
  
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
  
2.  Erstellen Sie ein <xref:System.Drawing.Graphics>\-Objekt, das der gewünschten Zeichnungsoberfläche entspricht.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen von Graphics\-Objekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
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
  
3.  Rufen Sie die <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode des Grafikobjekts auf, um das Bild zu rendern.  Sie müssen das zu zeichnende Bild und die Koordinaten der Stelle angeben, an der es gezeichnet werden soll.  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## Siehe auch  
 [Erste Schritte mit der Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Gewusst wie: Erstellen von Graphics\-Objekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Stifte, Linien und Rechtecke in GDI\+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)   
 [Gewusst wie: Zeichnen von Text in einem Windows Form](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)   
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Drawing Lines or Closed Figures](../Topic/Drawing%20Lines%20or%20Closed%20Figures%20\(Image%20Editor%20for%20Icons\).md)   
 [Image Editor for Icons](../Topic/Image%20Editor%20for%20Icons.md)