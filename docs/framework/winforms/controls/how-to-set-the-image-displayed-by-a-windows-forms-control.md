---
title: 'Vorgehensweise: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Bildes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: 1de835bda5ac906837ac3fbd97b87f68f14d1953
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333924"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Vorgehensweise: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Bildes
Mehrerer Windows Forms-Steuerelemente können Bilder anzeigen. Diese Images können Symbole, die Erläuterung des Zwecks des Steuerelements, z. B. ein Diskettensymbol auf eine Schaltfläche, werden die **speichern** Befehl. Alternativ können die Symbole Hintergrundbilder, um die Kontrolle zu haben, die Darstellung und das gewünschte Verhalten sein.  
  
### <a name="to-set-the-image-displayed-by-a-control"></a>Das von einem Steuerelement angezeigte Bild festlegen  
  
1. Legen Sie die `Image` oder `BackgroundImage` Eigenschaft, um ein Objekt des Typs <xref:System.Drawing.Image>. In der Regel Laden Sie das Image aus einer Datei mithilfe der <xref:System.Drawing.Image.FromFile%2A> Methode.  
  
     Das folgende Codebeispiel zeigt der Pfad festgelegt, für der Speicherort des Images ist der **eigene Bilder** Ordner. Die meisten Computer, die das Windows-Betriebssystem ausgeführt wird, werden dieses Verzeichnis enthalten. Dies ermöglicht auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen. Das folgende Codebeispiel ist erforderlich, dass Sie bereits ein Formular mit einem <xref:System.Windows.Forms.PictureBox> Steuerelement hinzugefügt.  
  
    ```vb  
    ' Replace the image named below  
    ' with an icon of your own choosing.  
    PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.MyPictures) _  
       & "\Image.gif")  
    ```  
  
    ```csharp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.MyPictures)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    pictureBox1->Image = Image::FromFile(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::MyPictures),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
