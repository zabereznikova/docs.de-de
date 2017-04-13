---
title: "Gewusst wie: &#196;ndern der Gr&#246;&#223;e oder Platzierung eines Bildes zur Laufzeit (Windows&#160;Forms) | Microsoft Docs"
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
  - "Beispiele [Windows Forms], PictureBox-Steuerelement"
  - "Bilder [Windows Forms], Steuern der Positionierung in PictureBox-Steuerelementen [Windows Forms]"
  - "PictureBox-Steuerelement [Windows Forms], Bildgröße und -ausrichtung"
  - "Bilder, Steuern der Positionierung in PictureBox-Steuerelementen [Windows Forms]"
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: &#196;ndern der Gr&#246;&#223;e oder Platzierung eines Bildes zur Laufzeit (Windows&#160;Forms)
Wenn Sie das Windows Forms\-Steuerelement <xref:System.Windows.Forms.PictureBox> auf einem Formular verwenden, können Sie die <xref:System.Windows.Forms.PictureBox.SizeMode%2A>\-Eigenschaft wie folgt festlegen:  
  
-   Die obere linke Bildecke wird auf die obere linke Ecke des Steuerelements ausgerichtet.  
  
-   Das Bild wird innerhalb des Steuerelements zentriert.  
  
-   Die Größe des Steuerelements wird an die Größe des Bildes angepasst.  
  
-   Das Bild wird in Anpassung an die Größe des jeweiligen Steuerelements gedehnt.  
  
 Durch das Dehnen von Bildern kann die Bildqualität \(besonders bei Verwendung des Bitmap\-Formats\) gemindert werden.  Metadateien sind besser für das Dehnen von Bildern geeignet, da sie aus einer Auflistung von Grafikanweisungen bestehen, die das Bild während der Laufzeit aufbauen.  
  
### So legen Sie die SizeMode\-Eigenschaft zur Laufzeit fest  
  
1.  Legen Sie <xref:System.Windows.Forms.PictureBox.SizeMode%2A> auf <xref:System.Windows.Forms.PictureBoxSizeMode> \(Standardwert\), <xref:System.Windows.Forms.PictureBoxSizeMode>, <xref:System.Windows.Forms.PictureBoxSizeMode> oder <xref:System.Windows.Forms.PictureBoxSizeMode> fest.  <xref:System.Windows.Forms.PictureBoxSizeMode> bedeutet, dass das Bild in der linken oberen Ecke des Steuerelements platziert wird. Wenn das Bild größer als das Steuerelement ist, werden sein unterer und rechter Rand abgeschnitten.  <xref:System.Windows.Forms.PictureBoxSizeMode> bedeutet, dass das Bild im Steuerelement zentriert wird. Wenn das Bild größer als das Steuerelement ist, werden die äußeren Ränder des Bilds abgeschnitten.  <xref:System.Windows.Forms.PictureBoxSizeMode> bedeutet, dass die Größe des Steuerelements an die Größe des Bilds angepasst wird.  <xref:System.Windows.Forms.PictureBoxSizeMode> bedeutet das Gegenteil, nämlich dass die Größe des Bildes an die Größe des Steuerelements angepasst wird.  
  
     Im unten stehenden Beispiel wurde als Speicherort für das Bild der Ordner **Eigene Dateien** festgelegt.  Dieser Speicherort wird verwendet, weil vorausgesetzt werden kann, dass die meisten Computer mit einem Windows\-Betriebssystem über dieses Verzeichnis verfügen.  Auf diese Weise können auch Benutzer mit minimalen Systemzugriffsberechtigungen die Anwendung sicher ausführen.  Im unten stehenden Beispiel wird davon ausgegangen, dass einem Formular bereits ein <xref:System.Windows.Forms.PictureBox>\-Steuerelement hinzugefügt wurde.  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.PictureBox>   
 [Gewusst wie: Laden eines Bilds mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)   
 [Übersicht über das PictureBox\-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)   
 [Gewusst wie: Festlegen von Bildern zur Laufzeit](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)   
 [PictureBox\-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)