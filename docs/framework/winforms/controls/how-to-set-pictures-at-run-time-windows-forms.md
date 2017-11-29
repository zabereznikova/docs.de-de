---
title: "Gewusst wie: Festlegen von Bildern zur Laufzeit (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 429c0c928d8bff4f837186040288d9447fc18687
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Gewusst wie: Festlegen von Bildern zur Laufzeit (Windows Forms)
Bild von einer Windows Forms angezeigt können programmgesteuert festgelegt werden <xref:System.Windows.Forms.PictureBox> Steuerelement.  
  
### <a name="to-set-a-picture-programmatically"></a>So legen Sie ein Bild programmgesteuert fest  
  
-   Legen Sie die <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft mit der <xref:System.Drawing.Image.FromFile%2A> Methode der <xref:System.Drawing.Image> Klasse.  
  
     Im folgenden Beispiel wird der Pfad für den Speicherort des Bilds Festlegen der Ordner "Eigene Dokumente". Dies geschieht, da Sie davon ausgehen können, die meisten Computer das Windows-Betriebssystem ausgeführt werden, dieses Verzeichnis enthält. Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen. Im folgenden Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.PictureBox> Steuerelement bereits hinzugefügt.  
  
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
  
-   Zunächst freigegeben Sie vom Image verwendeten Speicherplatz, und deaktivieren Sie dann auf die Grafik. Garbagecollection wird später um den Arbeitsspeicher freizugeben, wenn die Verwaltung des Arbeitsspeichers ein Problem aufgetreten ist.  
  
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
    >  Weitere Informationen dazu, warum sollten Sie verwenden die <xref:System.Drawing.Image.Dispose%2A> Methode auf diese Weise finden Sie unter [Bereinigen von nicht verwalteten Ressourcen](../../../../docs/standard/garbage-collection/unmanaged.md).  
  
     Mit diesem Code wird das Bild gelöscht, selbst wenn das Steuerelement zur Entwurfszeit eine Grafik geladen wurde.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.PictureBox>  
 <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>  
 [Übersicht über das PictureBox-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [Gewusst wie: Laden eines Bilds mithilfe des Designers](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [PictureBox-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
