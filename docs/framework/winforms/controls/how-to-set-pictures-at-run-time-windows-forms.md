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
ms.openlocfilehash: c7a65bcc65710324a4457c17dd728b4771550c06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694073"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Vorgehensweise: Festlegen von Bildern zur Laufzeit (Windows Forms)
Sie können das Bild angezeigt, die von einer Windows Forms programmgesteuert festlegen <xref:System.Windows.Forms.PictureBox> Steuerelement.  
  
### <a name="to-set-a-picture-programmatically"></a>So legen Sie ein Bild programmgesteuert fest  
  
-   Legen Sie die <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft mithilfe der <xref:System.Drawing.Image.FromFile%2A> -Methode der der <xref:System.Drawing.Image> Klasse.  
  
     Im folgenden Beispiel wird der Pfad für den Speicherort des Bilds Ordner "Eigene Dokumente". Dies geschieht, da Sie davon ausgehen können, dass die meisten Computer, die das Windows-Betriebssystem ausgeführt wird dieses Verzeichnis enthält. Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen. Im folgenden Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.PictureBox> Steuerelement bereits hinzugefügt.  
  
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
  
### <a name="to-clear-a-graphic"></a>Um eine Grafik zu löschen.  
  
-   Zunächst freigegeben Sie von der Abbildung verwendeten Arbeitsspeicher, und deaktivieren Sie dann auf die Grafik. Die automatische speicherbereinigung wird später um den Arbeitsspeicher freizugeben, wenn die Verwaltung des Arbeitsspeichers zu einem Problem wird.  
  
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
    >  Verwenden Sie für Weitere Informationen darüber, warum die <xref:System.Drawing.Image.Dispose%2A> -Methode in der auf diese Weise finden Sie unter [Bereinigen von nicht verwalteten Ressourcen](../../../../docs/standard/garbage-collection/unmanaged.md).  
  
     Dieser Code wird das Image gelöscht, selbst wenn eine Grafik in das Steuerelement zur Entwurfszeit geladen wurde.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [Übersicht über das PictureBox-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)
- [Vorgehensweise: Laden eines Bilds mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Vorgehensweise: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [PictureBox-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
