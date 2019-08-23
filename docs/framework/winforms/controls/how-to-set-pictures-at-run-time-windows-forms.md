---
title: 'Vorgehensweise: Festlegen von Bildern zur Laufzeit (Windows Forms)'
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
ms.openlocfilehash: 99d78a275c8ad8f55d9b0832a794545b65da7e20
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917530"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Vorgehensweise: Festlegen von Bildern zur Laufzeit (Windows Forms)
Sie können das Bild, das von einem Windows Forms <xref:System.Windows.Forms.PictureBox> -Steuerelement angezeigt wird, Programm gesteuert festlegen.  
  
### <a name="to-set-a-picture-programmatically"></a>So legen Sie ein Bildprogramm gesteuert fest  
  
- Legen Sie <xref:System.Windows.Forms.PictureBox.Image%2A> die-Eigenschaft <xref:System.Drawing.Image.FromFile%2A> mithilfe der- <xref:System.Drawing.Image> Methode der-Klasse fest.  
  
     Im folgenden Beispiel ist der Pfad, der für den Speicherort des Bilds festgelegt ist, der Ordner "eigene Dateien". Dies geschieht, da Sie davon ausgehen können, dass die meisten Computer, auf denen das Windows-Betriebssystem ausgeführt wird, dieses Verzeichnis enthalten. Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen. Im folgenden Beispiel wird davon ausgegangen, dass <xref:System.Windows.Forms.PictureBox> ein Formular bereits hinzugefügt wurde.  
  
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
    > Weitere Informationen dazu, warum Sie die <xref:System.Drawing.Image.Dispose%2A> Methode auf diese Weise verwenden sollten, finden Sie unter [Bereinigen von nicht verwalteten Ressourcen](../../../standard/garbage-collection/unmanaged.md).  
  
     Mit diesem Code wird das Bild gelöscht, auch wenn eine Grafik zur Entwurfszeit in das Steuerelement geladen wurde.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [Übersicht über das PictureBox-Steuerelement](picturebox-control-overview-windows-forms.md)
- [Vorgehensweise: Laden eines Bilds mithilfe des Designers](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Vorgehensweise: Ändern der Größe oder Platzierung eines Bilds zur Laufzeit](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [PictureBox-Steuerelement](picturebox-control-windows-forms.md)
