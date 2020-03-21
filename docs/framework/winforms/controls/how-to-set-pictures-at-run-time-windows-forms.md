---
title: 'Gewusst wie: Festlegen von Bildern zur Laufzeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: cd599ac7e07b5210f8bcff1ffbc76b3d9ee563d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182121"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Gewusst wie: Festlegen von Bildern zur Laufzeit (Windows Forms)
Sie können das Bild, das von <xref:System.Windows.Forms.PictureBox> einem Windows Forms-Steuerelement angezeigt wird, programmgesteuert festlegen.  
  
### <a name="to-set-a-picture-programmatically"></a>So legen Sie ein Bild programmgesteuert fest  
  
- Legen <xref:System.Windows.Forms.PictureBox.Image%2A> Sie die <xref:System.Drawing.Image.FromFile%2A> Eigenschaft <xref:System.Drawing.Image> mithilfe der Methode der Klasse fest.  
  
     Im folgenden Beispiel ist der Pfad, der für den Speicherort des Bildes festgelegt ist, der Ordner Eigene Dokumente. Dies ist der Grund, da Sie davon ausgehen können, dass die meisten Computer, auf denen das Windows-Betriebssystem ausgeführt wird, dieses Verzeichnis enthalten. Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen. Im folgenden Beispiel wird <xref:System.Windows.Forms.PictureBox> ein Formular mit einem bereits hinzugefügten Steuerelement angenommen.  
  
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
  
### <a name="to-clear-a-graphic"></a>So löschen Sie eine Grafik  
  
- Lassen Sie zunächst den vom Bild verwendeten Speicher los, und löschen Sie dann die Grafik. Die Garbage Collection gibt den Speicher später frei, wenn die Speicherverwaltung zu einem Problem wird.  
  
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
    > Weitere Informationen dazu, warum <xref:System.Drawing.Image.Dispose%2A> Sie die Methode auf diese Weise verwenden sollten, finden Sie unter [Bereinigen nicht verwalteter Ressourcen](../../../standard/garbage-collection/unmanaged.md).  
  
     Dieser Code löscht das Bild auch dann, wenn eine Grafik zur Entwurfszeit in das Steuerelement geladen wurde.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [Übersicht über das PictureBox-Steuerelement](picturebox-control-overview-windows-forms.md)
- [Gewusst wie: Laden eines Bilds mithilfe des Designers](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [PictureBox-Steuerelement](picturebox-control-windows-forms.md)
