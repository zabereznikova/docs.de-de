---
title: Festlegen des von einem Steuerelement angezeigten Bilds
ms.date: 08/20/2019
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
ms.openlocfilehash: 5df0068c8462bbaab0cb0135de1dd1b91ababe06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746874"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Gewusst wie: Festlegen des von einem Windows Forms Steuerelement angezeigten Bilds

Mehrere Windows Forms Steuerelemente können Bilder anzeigen. Diese Bilder können Symbole sein, die den Zweck des Steuer Elements verdeutlichen, wie z. b. ein Diskettensymbol auf einer Schaltfläche, die den Befehl "Speichern" bezeichnet. Alternativ können die Symbole Hintergrundbilder sein, um dem Steuerelement das gewünschte Aussehen und Verhalten zu geben.

## <a name="programmatic"></a>Programmgesteuert

Legen Sie die `Image`-oder `BackgroundImage`-Eigenschaft des Steuer Elements auf ein Objekt vom Typ <xref:System.Drawing.Image>fest. Im allgemeinen laden Sie das Image mithilfe der <xref:System.Drawing.Image.FromFile%2A>-Methode aus einer Datei.

Im folgenden Codebeispiel ist der Pfad, der für den Speicherort des Bilds festgelegt wurde, der Ordner **eigene Bilder** . Die meisten Computer unter dem Windows-Betriebssystem enthalten dieses Verzeichnis. Dies ermöglicht es Benutzern mit minimalen System Zugriffsebenen, die Anwendung sicher auszuführen. Das folgende Codebeispiel setzt voraus, dass Sie bereits über ein Formular mit einem hinzugefügten <xref:System.Windows.Forms.PictureBox> Steuerelement verfügen.

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```cpp
// Replace the image named below with your own icon.
pictureBox1->Image = Image::FromFile(String::Concat
   (System::Environment::GetFolderPath
   (System::Environment::SpecialFolder::MyPictures),
   "\\Image.gif"));
```

## <a name="designer"></a>Designer

1. Wählen Sie im **Eigenschaften** Fenster von Visual Studio die **Bild** -oder **BackgroundImage** -Eigenschaft des Steuer Elements aus, und klicken Sie dann auf die Schaltfläche mit den Auslassungs Punkten (![Auslassungs Zeichen in Visual Studio](./media/visual-studio-ellipsis-button.png)), um das Dialogfeld **Ressource auswählen** anzuzeigen.

2. Wählen Sie das Abbild aus, das Sie anzeigen möchten.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
