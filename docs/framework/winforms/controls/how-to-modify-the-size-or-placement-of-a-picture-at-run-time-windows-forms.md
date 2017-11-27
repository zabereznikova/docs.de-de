---
title: "Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit (Windows Forms)"
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
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: df67871b0b133297a6f53ff9e4a42c7630a5f56d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit (Windows Forms)
Bei Verwendung von Windows Forms <xref:System.Windows.Forms.PictureBox> Steuerelement eines Formulars, können Sie festlegen der <xref:System.Windows.Forms.PictureBox.SizeMode%2A> Eigenschaft darauf:  
  
-   Richten Sie das Bild oben links mit der linken oberen Ecke des Steuerelements  
  
-   Zentrieren Sie das Bild innerhalb des Steuerelements  
  
-   Passen Sie die Größe des Steuerelements auf dem Bild anzupassen, die angezeigt  
  
-   Stretch-Bild angezeigt wird, um das Steuerelement eingepasst werden  
  
 Strecken ein Bild (vor allem eine Bitmap-Format), kann ein Verlust Bildqualität erzeugen. Metadateien, die Listen von Graphics-Anweisungen zum Darstellen von Bildern zur Laufzeit sind, sind besser geeignet als Bitmaps sind Strecken.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>Die SizeMode-Eigenschaft zur Laufzeit festgelegt  
  
1.  Legen Sie <xref:System.Windows.Forms.PictureBox.SizeMode%2A> auf <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (Standard), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, oder <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal>bedeutet, dass das Bild in der linken oberen Ecke befindet. Wenn das Bild größer als das Steuerelement ist, werden die unteren und rechten Rand abgeschnitten. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>bedeutet, dass das Bild im Steuerelement zentriert wird. Wenn das Bild größer als das Steuerelement ist, werden das Bild äußeren Kanten abgeschnitten. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>bedeutet, dass die Größe des Steuerelements auf die Größe des Bilds angepasst wird. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>ist das Gegenteil und bedeutet, dass die Größe des Bilds an die Größe des Steuerelements angepasst wird.  
  
     Im folgenden Beispiel wird der Pfad für den Speicherort des Bilds Festlegen der Ordner "Eigene Dokumente". Dies geschieht, da Sie davon ausgehen können, die meisten Computer das Windows-Betriebssystem ausgeführt werden, dieses Verzeichnis enthält. Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen. Im folgenden Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.PictureBox> Steuerelement bereits hinzugefügt.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.PictureBox>  
 [Gewusst wie: Laden eines Bilds mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [Übersicht über das PictureBox-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [Gewusst wie: Festlegen von Bildern zur Laufzeit](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [PictureBox-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
