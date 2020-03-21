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
ms.openlocfilehash: fea813d7b9fe585e35b729b8b64e3a5f414ef76d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141965"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit (Windows Forms)
Wenn Sie das <xref:System.Windows.Forms.PictureBox> Windows Forms-Steuerelement in einem <xref:System.Windows.Forms.PictureBox.SizeMode%2A> Formular verwenden, können Sie die Eigenschaft darauf auf:  
  
- Richten Sie die obere linke Ecke des Bildes mit der oberen linken Ecke des Steuerelements aus.  
  
- Zentrieren Sie das Bild innerhalb des Steuerelements  
  
- Passen Sie die Größe des Steuerelements an das angezeigte Bild an  
  
- Dehnen Sie jedes angezeigte Bild, um es an das Steuerelement anzupassen  
  
 Das Dehnen eines Bildes (insbesondere eines im Bitmap-Format) kann zu einem Verlust der Bildqualität führen. Metadateien, die Listen von Grafikanweisungen zum Zeichnen von Bildern zur Laufzeit sind, eignen sich besser zum Dehnen als Bitmaps.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>So legen Sie die SizeMode-Eigenschaft zur Laufzeit fest  
  
1. Wird <xref:System.Windows.Forms.PictureBox.SizeMode%2A> <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> auf (Standardeinstellung), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>oder <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>festgelegt. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal>bedeutet, dass das Bild in der oberen linken Ecke des Steuerelements platziert wird; Wenn das Bild größer als das Steuerelement ist, werden die unteren und rechten Ränder abgeschnitten. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>bedeutet, dass das Bild innerhalb des Steuerelements zentriert ist; Wenn das Bild größer als das Steuerelement ist, werden die Außenkanten des Bildes abgeschnitten. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>bedeutet, dass die Größe des Steuerelements an die Größe des Bildes angepasst wird. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>ist die Rückseite und bedeutet, dass die Größe des Bildes an die Größe des Steuerelements angepasst wird.  
  
     Im folgenden Beispiel ist der Pfad, der für den Speicherort des Bildes festgelegt ist, der Ordner Eigene Dokumente. Dies ist der Grund, da Sie davon ausgehen können, dass die meisten Computer, auf denen das Windows-Betriebssystem ausgeführt wird, dieses Verzeichnis enthalten. Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen. Im folgenden Beispiel wird <xref:System.Windows.Forms.PictureBox> ein Formular mit einem bereits hinzugefügten Steuerelement angenommen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.PictureBox>
- [Gewusst wie: Laden eines Bilds mithilfe des Designers](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Übersicht über das PictureBox-Steuerelement](picturebox-control-overview-windows-forms.md)
- [Gewusst wie: Festlegen von Bildern zur Laufzeit](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox-Steuerelement](picturebox-control-windows-forms.md)
