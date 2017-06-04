---
title: "Gewusst wie: Festlegen von Bildern zur Laufzeit (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Bitmaps [Windows Forms], Anzeigen in PictureBox-Steuerelementen [Windows Forms]"
  - "Beispiele [Windows Forms], PictureBox-Steuerelement"
  - "Bilder [Windows Forms], Hinzufügen mit PictureBox-Steuerelementen [Windows Forms]"
  - "PictureBox-Steuerelement [Windows Forms], Hinzufügen von Grafiken"
  - "PictureBox-Steuerelement [Windows Forms], Hinzufügen von Bildern"
  - "Bilder, Festlegen von Anzeigeoptionen"
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Festlegen von Bildern zur Laufzeit (Windows&#160;Forms)
Sie können programmgesteuert festlegen, welches Bild von einem <xref:System.Windows.Forms.PictureBox>\-Steuerelement in Windows Forms angezeigt wird.  
  
### So legen Sie ein Bild programmgesteuert fest  
  
-   Legen Sie die <xref:System.Windows.Forms.PictureBox.Image%2A>\-Eigenschaft mit der <xref:System.Drawing.Image.FromFile%2A>\-Methode der <xref:System.Drawing.Image>\-Klasse fest.  
  
     Im unten stehenden Beispiel wurde als Speicherort für das Bild der Ordner **Eigene Dateien** festgelegt.  Dieser Speicherort wird verwendet, weil vorausgesetzt werden kann, dass die meisten Computer mit einem Windows\-Betriebssystem über dieses Verzeichnis verfügen.  Auf diese Weise können auch Benutzer mit minimalen Systemzugriffsberechtigungen die Anwendung sicher ausführen.  Im unten stehenden Beispiel wird davon ausgegangen, dass einem Formular bereits ein <xref:System.Windows.Forms.PictureBox>\-Steuerelement hinzugefügt wurde.  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### So löschen Sie eine Grafik  
  
-   Geben Sie zuerst den vom Bild verwendeten Speicherplatz frei, und löschen Sie anschließend die Grafik.  Wenn es bei der Speicherverwaltung zu Problemen kommt, gibt die Garbage Collection den Speicher zu einem späteren Zeitpunkt frei.  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)   
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    >  Weitere Informationen dazu, warum die <xref:System.Drawing.Image.Dispose%2A>\-Methode auf diese Weise verwendet werden sollte, finden Sie unter [Cleaning Up Unmanaged Resources](../../../../docs/standard/garbage-collection/unmanaged.md).  
  
     Der Code löscht das Bild selbst dann, wenn eine Grafik zur Entwurfszeit in das Steuerelement geladen wurde.  
  
## Siehe auch  
 <xref:System.Windows.Forms.PictureBox>   
 <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName>   
 [Übersicht über das PictureBox\-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)   
 [Gewusst wie: Laden eines Bilds mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)   
 [Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)   
 [PictureBox\-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)