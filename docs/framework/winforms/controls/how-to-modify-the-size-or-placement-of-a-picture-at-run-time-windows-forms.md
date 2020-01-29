---
title: 'Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit'
ms.date: 03/30/2017
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
ms.openlocfilehash: 9bb094ce0b7945f23a2e9b8614e56c9492d5f832
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736036"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit (Windows Forms)
Wenn Sie die Windows Forms <xref:System.Windows.Forms.PictureBox>-Steuerelement in einem Formular verwenden, können Sie die Eigenschaft <xref:System.Windows.Forms.PictureBox.SizeMode%2A> auf Folgendes festlegen:  
  
- Ausrichten der oberen linken Ecke des Bilds mit der linken oberen Ecke des Steuer Elements  
  
- Zentrieren des Bilds innerhalb des Steuer Elements  
  
- Passen Sie die Größe des Steuer Elements an das Bild an, das es anzeigt.  
  
- Bildstrecken, das angezeigt wird, um das Steuerelement anzupassen  
  
 Das Strecken eines Bilds (insbesondere eines im Bitmapformat) kann zu einem Verlust bei der Bildqualität führen. Metadatendateien, die Listen mit Grafik Anweisungen zum Zeichnen von Bildern zur Laufzeit sind, eignen sich besser für die Streckung als Bitmaps.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>So legen Sie die SizeMode-Eigenschaft zur Laufzeit fest  
  
1. Legen Sie <xref:System.Windows.Forms.PictureBox.SizeMode%2A> auf <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (Standardeinstellung), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>oder <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>fest. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> bedeutet, dass das Bild in der oberen linken Ecke des Steuer Elements platziert wird. Wenn das Bild größer als das Steuerelement ist, werden die unteren und rechten Ränder abgeschnitten. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> bedeutet, dass das Bild im Steuerelement zentriert ist. Wenn das Bild größer als das Steuerelement ist, werden die äußeren Ränder des Bilds abgeschnitten. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> bedeutet, dass die Größe des Steuer Elements an die Größe des Bilds angepasst wird. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> ist die umgekehrte und bedeutet, dass die Größe des Bilds an die Größe des Steuer Elements angepasst wird.  
  
     Im folgenden Beispiel ist der Pfad, der für den Speicherort des Bilds festgelegt ist, der Ordner "eigene Dateien". Dies geschieht, da Sie davon ausgehen können, dass die meisten Computer, auf denen das Windows-Betriebssystem ausgeführt wird, dieses Verzeichnis enthalten. Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen. Im folgenden Beispiel wird davon ausgegangen, dass ein <xref:System.Windows.Forms.PictureBox> Formular bereits hinzugefügt wurde.  
  
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

- <xref:System.Windows.Forms.PictureBox>
- [Gewusst wie: Laden eines Bilds mithilfe des Designers](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Übersicht über das PictureBox-Steuerelement](picturebox-control-overview-windows-forms.md)
- [Gewusst wie: Festlegen von Bildern zur Laufzeit](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox-Steuerelement](picturebox-control-windows-forms.md)
