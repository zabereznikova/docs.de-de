---
title: 'Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms'
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
ms.openlocfilehash: e5c563c4f46924a95936bc5a51862230f2cbdb99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527637"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms
Windows Forms <xref:System.Windows.Forms.ImageList> Komponente wird in der Regel mit Bildern aufgefüllt, bevor sie ein Steuerelement zugeordnet ist. Sie können jedoch hinzufügen und entfernen Bilder, nachdem die Bildliste mit einem Steuerelement.  
  
> [!NOTE]
>  Beim Entfernen von Bildern, vergewissern Sie sich, die die <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> Eigenschaft aller verknüpften Steuerelemente noch gültig ist.  
  
### <a name="to-add-images-programmatically"></a>Programmgesteuertes Hinzufügen von Bildern  
  
-   Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> Methode der Bildliste <xref:System.Windows.Forms.ImageList.Images%2A> Eigenschaft.  
  
     Im folgenden Codebeispiel legen der Pfad für der Speicherort des Bilds wird die **eigene** Ordner. Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass die meisten Computer, auf denen die Windows-Betriebssystem ausgeführt werden dieser Ordner enthält. Dieser Speicherort kann auch Benutzer mit minimalen Zugriffsebenen Weitere sicher führen Sie die Anwendung aus. Das folgende Codebeispiel erfordert, dass ein Formular mit einem <xref:System.Windows.Forms.ImageList> Steuerelement bereits hinzugefügt.  
  
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
  
### <a name="to-add-images-with-a-key-value"></a>Hinzufügen von Bildern mit einem Schlüsselwert.  
  
-   Gehen Sie die <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> Methoden der Bildliste <xref:System.Windows.Forms.ImageList.Images%2A> Eigenschaft, die einen Schlüsselwert.  
  
     Im folgenden Codebeispiel legen der Pfad für der Speicherort des Bilds wird die **eigene** Ordner. Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass die meisten Computer, auf denen die Windows-Betriebssystem ausgeführt werden dieser Ordner enthält. Dieser Speicherort kann auch Benutzer mit minimalen Zugriffsebenen Weitere sicher führen Sie die Anwendung aus. Das folgende Codebeispiel erfordert, dass ein Formular mit einem <xref:System.Windows.Forms.ImageList> Steuerelement bereits hinzugefügt.  
  
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
  
1.  
  
### <a name="to-remove-all-images-programmatically"></a>So entfernen Sie alle Bilder programmgesteuert  
  
-   Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> -Methode zum Entfernen eines einzelnen Images  
  
     , - oder -  
  
     Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> Methode, um alle Bilder in der Bildliste zu löschen.  
  
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
  
### <a name="to-remove-images-by-key"></a>So entfernen Sie die Bilder nach Schlüssel  
  
-   Verwenden der <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> Methode, um ein einzelnes Bild anhand ihres Schlüssels zu entfernen.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a>Siehe auch  
 [ImageList-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)  
 [Übersicht über die ImageList-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-overview-windows-forms.md)  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
