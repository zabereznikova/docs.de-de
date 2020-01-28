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
ms.openlocfilehash: bd0509c05fd9c1cfc0c631fcd613c64d20296f6b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746745"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Gewusst wie: Festlegen von Bildern zur Laufzeit (Windows Forms)
Sie können das Bild, das von einem Windows Forms <xref:System.Windows.Forms.PictureBox>-Steuerelement angezeigt wird, Programm gesteuert festlegen.  
  
### <a name="to-set-a-picture-programmatically"></a>So legen Sie ein Bildprogramm gesteuert fest  
  
- Legen Sie die <xref:System.Windows.Forms.PictureBox.Image%2A>-Eigenschaft mit der <xref:System.Drawing.Image.FromFile%2A>-Methode der <xref:System.Drawing.Image>-Klasse fest.  
  
     Im folgenden Beispiel ist der Pfad, der für den Speicherort des Bilds festgelegt ist, der Ordner "eigene Dateien". Dies geschieht, da Sie davon ausgehen können, dass die meisten Computer, auf denen das Windows-Betriebssystem ausgeführt wird, dieses Verzeichnis enthalten. Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen. Im folgenden Beispiel wird davon ausgegangen, dass ein <xref:System.Windows.Forms.PictureBox> Formular bereits hinzugefügt wurde.  
  
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
  
- Geben Sie zunächst den Speicher frei, der von dem Image verwendet wird, und löschen Sie dann die Grafik. Durch die Garbage Collection wird der Arbeitsspeicher später freigegeben, wenn die Speicherverwaltung zu einem Problem wird.  
  
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
    > Weitere Informationen dazu, warum Sie die <xref:System.Drawing.Image.Dispose%2A>-Methode auf diese Weise verwenden sollten, finden Sie unter [Bereinigen von nicht verwalteten Ressourcen](../../../standard/garbage-collection/unmanaged.md).  
  
     Mit diesem Code wird das Bild gelöscht, auch wenn eine Grafik zur Entwurfszeit in das Steuerelement geladen wurde.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [Übersicht über das PictureBox-Steuerelement](picturebox-control-overview-windows-forms.md)
- [Gewusst wie: Laden eines Bilds mithilfe des Designers](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [PictureBox-Steuerelement](picturebox-control-windows-forms.md)
