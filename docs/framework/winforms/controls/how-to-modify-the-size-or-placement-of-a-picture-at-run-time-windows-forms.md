---
title: 'Vorgehensweise: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit (Windows Forms)'
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
ms.openlocfilehash: 695abf51870ef9164e4543a91b3183e801eee55f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649256"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Vorgehensweise: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit (Windows Forms)
Bei Verwendung der Windows Forms <xref:System.Windows.Forms.PictureBox> Steuerelement eines Formulars, Sie können festlegen, die <xref:System.Windows.Forms.PictureBox.SizeMode%2A> Eigenschaft darauf, um:  
  
- Ausrichten der oberen linken Ecke der Grafik mit der linken oberen Ecke des Steuerelements  
  
- Zentrieren Sie das Bild innerhalb des Steuerelements  
  
- Passen Sie die Größe des Steuerelements auf das Bild anzupassen, das er zeigt  
  
- Um ein Bild angezeigt wird, um das Steuerelement eingepasst werden gestreckt  
  
 Strecken ein Bild (vor allem eine Bitmap-Format) kann zu einem Verlust im Bildqualität führen. Metadateien, die Listen der Grafik-Anweisungen zum Darstellen von Bildern zur Laufzeit sind, eignen sich besser für Sie Streckung als Bitmaps sind.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>Um die SizeMode-Eigenschaft zur Laufzeit festzulegen.  
  
1. Legen Sie <xref:System.Windows.Forms.PictureBox.SizeMode%2A> zu <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (Standardeinstellung), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, oder <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> bedeutet, dass das Bild in die linken oberen Ecke des Steuerelements eingefügt wird. Wenn das Bild größer als das Steuerelement ist, werden die unteren und rechten Rand abgeschnitten. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> bedeutet, dass das Bild innerhalb des Steuerelements zentriert wird. Wenn das Bild größer als das Steuerelement ist, werden die äußeren Ränder des Bilds abgeschnitten. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> bedeutet, dass die Größe des Steuerelements auf die Größe des Bilds angepasst wird. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> ist das Gegenteil und bedeutet, dass die Größe des Bilds an die Größe des Steuerelements angepasst wird.  
  
     Im folgenden Beispiel wird der Pfad für den Speicherort des Bilds Ordner "Eigene Dokumente". Dies geschieht, da Sie davon ausgehen können, dass die meisten Computer, die das Windows-Betriebssystem ausgeführt wird dieses Verzeichnis enthält. Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen. Im folgenden Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.PictureBox> Steuerelement bereits hinzugefügt.  
  
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
- [Vorgehensweise: Laden eines Bilds mithilfe des Designers](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Übersicht über das PictureBox-Steuerelement](picturebox-control-overview-windows-forms.md)
- [Vorgehensweise: Festlegen von Bildern zur Laufzeit](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox-Steuerelement](picturebox-control-windows-forms.md)
