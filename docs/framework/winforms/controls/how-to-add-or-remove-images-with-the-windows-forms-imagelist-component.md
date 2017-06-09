---
title: "Gewusst wie: Hinzuf&#252;gen oder Entfernen von Bildern mit der ImageList-Komponente in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ImageList-Komponente [Windows Forms], Hinzufügen von Grafiken"
  - "ImageList-Komponente [Windows Forms], Entfernen von Bildern"
  - "Bilder [Windows Forms], Hinzufügen zu ImageList-Komponente"
  - "Bilder [Windows Forms], Anzeigen mit Steuerelementen"
  - "Bilder [Windows Forms], Entfernen aus der ImageList-Komponente"
  - "Bilder [Windows Forms], Speichern für Steuerelemente"
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Hinzuf&#252;gen oder Entfernen von Bildern mit der ImageList-Komponente in Windows&#160;Forms
Die <xref:System.Windows.Forms.ImageList>\-Komponente in Windows Forms wird normalerweise mit Bildern gefüllt, bevor sie einem Steuerelement zugeordnet wird.  Bilder können jedoch hinzugefügt oder entfernt werden, nachdem die Bildliste einem Steuerelement zugeordnet wurde.  
  
> [!NOTE]
>  Achten Sie beim Entfernen von Bildern darauf, dass die <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A>\-Eigenschaft aller verknüpften Steuerelemente weiterhin gültig ist.  
  
### So fügen Sie Bilder programmgesteuert hinzu  
  
-   Verwenden Sie die <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A>\-Methode der <xref:System.Windows.Forms.ImageList.Images%2A>\-Eigenschaft der Bildliste.  
  
     Im folgenden Codebeispiel wurde als Speicherort für das Bild der Ordner **Eigene Dateien** festgelegt.  Dieser Speicherort wird verwendet, weil vorausgesetzt werden kann, dass die meisten Computer mit dem Windows\-Betriebssystem über einen Ordner mit dieser Bezeichnung verfügen.  Dieser Speicherort ermöglicht es auch Benutzern mit minimalen Systemzugriffsberechtigungen, die Anwendung sicherer auszuführen.  Im folgenden Codebeispiel wird vorausgesetzt, dass Sie über ein Formular verfügen, dem das <xref:System.Windows.Forms.ImageList>\-Steuerelement bereits hinzugefügt wurde.  
  
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
  
### So fügen Sie Bilder mit einem Schlüsselwert hinzu  
  
-   Verwenden Sie eine der <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A>\-Methoden der <xref:System.Windows.Forms.ImageList.Images%2A>\-Eigenschaft der Bildliste, die einen Schlüsselwert verwendet.  
  
     Im folgenden Codebeispiel wurde als Speicherort für das Bild der Ordner **Eigene Dateien** festgelegt.  Dieser Speicherort wird verwendet, weil vorausgesetzt werden kann, dass die meisten Computer mit dem Windows\-Betriebssystem über einen Ordner mit dieser Bezeichnung verfügen.  Dieser Speicherort ermöglicht es auch Benutzern mit minimalen Systemzugriffsberechtigungen, die Anwendung sicherer auszuführen.  Im folgenden Codebeispiel wird vorausgesetzt, dass Sie über ein Formular verfügen, dem das <xref:System.Windows.Forms.ImageList>\-Steuerelement bereits hinzugefügt wurde.  
  
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
  
### So entfernen Sie alle Bilder programmgesteuert  
  
-   Verwenden Sie die <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A>\-Methode, um ein einzelnes Bild zu entfernen.  
  
     – oder –  
  
     Verwenden Sie die <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A>\-Methode, um alle Bilder in der Bildliste zu löschen.  
  
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
  
### So entfernen Sie Bilder anhand des Schlüsselwerts  
  
-   Verwenden Sie die <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A>\-Methode, um ein einzelnes Bild anhand seines Schlüsselwerts zu entfernen.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
  
```  
  
## Siehe auch  
 [ImageList\-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)   
 [Übersicht über die ImageList\-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-overview-windows-forms.md)   
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)