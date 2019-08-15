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
ms.openlocfilehash: 99bde4fac7b3057358c7e6a8550efdb4cc351eb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037882"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Vorgehensweise: Festlegen des von einem Windows Forms Steuerelement angezeigten Bilds

Mehrere Windows Forms Steuerelemente können Bilder anzeigen. Diese Bilder können Symbole sein, die den Zweck des Steuer Elements verdeutlichen, wie z. b. ein Diskettensymbol auf einer Schaltfläche, die den Befehl " **Speichern** " bezeichnet. Alternativ können die Symbole Hintergrundbilder sein, um dem Steuerelement das gewünschte Aussehen und Verhalten zu geben.

## <a name="to-set-the-image-displayed-by-a-control"></a>So legen Sie das von einem Steuerelement angezeigte Bild fest

1. Legen Sie die- `Image` Eigenschaft `BackgroundImage` oder-Eigenschaft des Steuer Elements <xref:System.Drawing.Image>auf ein Objekt vom Typ fest. Im allgemeinen laden Sie das Bild mithilfe der <xref:System.Drawing.Image.FromFile%2A> -Methode aus einer Datei.

     Im folgenden Codebeispiel ist der Pfad, der für den Speicherort des Bilds festgelegt wurde, der Ordner **eigene Bilder** . Die meisten Computer, auf denen das Windows-Betriebssystem ausgeführt wird, enthalten dieses Verzeichnis. Dies ermöglicht es Benutzern mit minimalen System Zugriffsebenen, die Anwendung sicher auszuführen. Im folgenden Codebeispiel ist es erforderlich, dass Sie bereits über ein <xref:System.Windows.Forms.PictureBox> Formular mit einem hinzugefügten Steuerelement verfügen.

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
