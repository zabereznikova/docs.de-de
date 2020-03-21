---
title: Hinzufügen oder Entfernen von Bildern mit ImageList-Komponente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], removing from ImageList component
- images [Windows Forms], storing for controls
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
- images [Windows Forms], displaying with controls
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
ms.openlocfilehash: e045be7ea9407bc379b0c22282fcd2184ff5db51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182298"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms
Die Windows <xref:System.Windows.Forms.ImageList> Forms-Komponente wird in der Regel mit Bildern aufgefüllt, bevor sie einem Steuerelement zugeordnet wird. Sie können jedoch Bilder hinzufügen und entfernen, nachdem Sie die Bildliste einem Steuerelement zugeordnet haben.  
  
> [!NOTE]
> Wenn Sie Bilder entfernen, <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> stellen Sie sicher, dass die Eigenschaft aller zugeordneten Steuerelemente weiterhin gültig ist.  
  
### <a name="to-add-images-programmatically"></a>So fügen Sie Bilder programmgesteuert hinzu  
  
- Verwenden <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> Sie die Methode der <xref:System.Windows.Forms.ImageList.Images%2A> Eigenschaft der Bildliste.  
  
     Im folgenden Codebeispiel ist der Pfad, der für den Speicherort des Bildes festgelegt ist, der Ordner **Eigene Dokumente.** Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass die meisten Computer, auf denen das Windows-Betriebssystem ausgeführt wird, diesen Ordner enthalten. Wenn Sie diesen Speicherort auswählen, können Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicherer ausführen. Im folgenden Codebeispiel ist erforderlich, <xref:System.Windows.Forms.ImageList> dass Sie ein Formular mit einem Steuerelement bereits hinzugefügt haben.  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    End Sub  
    ```  
  
    ```csharp  
    public void addImage()  
    {  
    // Be sure that you use an appropriate escape sequence (such as the
    // @) when specifying the location of the file.  
       System.Drawing.Image myImage =
         Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
    }  
    ```  
  
    ```cpp  
    public:  
       void addImage()  
       {  
       // Replace the bold image in the following sample
       // with your own icon.  
       // Be sure that you use an appropriate escape sequence (such as
       // \\) when specifying the location of the file.  
          System::Drawing::Image ^ myImage =
             Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
       }  
    ```  
  
### <a name="to-add-images-with-a-key-value"></a>So fügen Sie Bilder mit einem Schlüsselwert hinzu.  
  
- Verwenden Sie <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> eine der Methoden der <xref:System.Windows.Forms.ImageList.Images%2A> Eigenschaft der Bildliste, die einen Schlüsselwert annimmt.  
  
     Im folgenden Codebeispiel ist der Pfad, der für den Speicherort des Bildes festgelegt ist, der Ordner **Eigene Dokumente.** Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass die meisten Computer, auf denen das Windows-Betriebssystem ausgeführt wird, diesen Ordner enthalten. Wenn Sie diesen Speicherort auswählen, können Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicherer ausführen. Im folgenden Codebeispiel ist erforderlich, <xref:System.Windows.Forms.ImageList> dass Sie ein Formular mit einem Steuerelement bereits hinzugefügt haben.  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add("myPhoto", myImage)  
    End Sub  
    ```  
  
```csharp  
public void addImage()  
{  
// Be sure that you use an appropriate escape sequence (such as the
// @) when specifying the location of the file.  
   System.Drawing.Image myImage =
     Image.FromFile  
   (System.Environment.GetFolderPath  
   (System.Environment.SpecialFolder.Personal)  
   + @"\Image.gif");  
   imageList1.Images.Add("myPhoto", myImage);  
}  
```  
  
### <a name="to-remove-all-images-programmatically"></a>So entfernen Sie alle Bilder programmgesteuert  
  
- Verwenden <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> Der Methode zum Entfernen eines einzelnen Bildes  
  
     ,-oder-  
  
     Verwenden <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> Sie die Methode, um alle Bilder in der Bildliste zu löschen.  
  
    ```vb  
    ' Removes the first image in the image list  
    ImageList1.Images.Remove(myImage)  
    ' Clears all images in the image list  
    ImageList1.Images.Clear()  
    ```  
  
```csharp  
// Removes the first image in the image list.  
imageList1.Images.Remove(myImage);  
// Clears all images in the image list.  
imageList1.Images.Clear();  
```  
  
### <a name="to-remove-images-by-key"></a>So entfernen Sie Bilder per Schlüssel  
  
- Verwenden <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> Sie die Methode, um ein einzelnes Bild durch den Schlüssel zu entfernen.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [ImageList-Komponente](imagelist-component-windows-forms.md)
- [Übersicht über die ImageList-Komponente](imagelist-component-overview-windows-forms.md)
- [Bilder, Bitmaps und Metadateien](../advanced/images-bitmaps-and-metafiles.md)
