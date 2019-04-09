---
title: 'Vorgehensweise: Laden eines Bilds mithilfe des Designers (Windows Forms)'
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 5aa8ff1efa045d52382cc5c24a0cae1f0f1bb510
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127139"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Vorgehensweise: Laden eines Bilds mithilfe des Designers (Windows Forms)
Mit der Windows Forms <xref:System.Windows.Forms.PictureBox> -Steuerelement, können Sie laden und anzeigen ein Bilds auf einem Formular zur Entwurfszeit durch Festlegen der <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft, um ein gültiges Bild. Die folgende Tabelle zeigt die zulässigen Dateitypen.  
  
|Typ|Dateinamenerweiterung|  
|----------|-------------------------|  
|Bitmap|.bmp|  
|Symbol|.ico|  
|GIF|GIF|  
|Metadatei|.wmf|  
|JPEG|.jpg|  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-display-a-picture-at-design-time"></a>Zur Entwurfszeit ein Bild anzeigen  
  
1.  Zeichnen einer <xref:System.Windows.Forms.PictureBox> Steuerelement in einem Formular.  
  
2.  Wählen Sie im Fenster Eigenschaften die <xref:System.Windows.Forms.PictureBox.Image%2A> -Eigenschaft, und klicken Sie dann auf klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um anzuzeigen die **öffnen** Dialogfeld.  
  
3.  Wenn Sie für einen bestimmten Dateityp (z. B. GIF-Dateien) suchen, wählen Sie sie in der **Dateityp** Feld.  
  
4.  Wählen Sie die Datei, die Sie anzeigen möchten.  
  
### <a name="to-clear-the-picture-at-design-time"></a>Um das Bild zur Entwurfszeit zu löschen.  
  
1.  Auf der **Eigenschaften** wählen Sie im Fenster der <xref:System.Windows.Forms.PictureBox.Image%2A> -Eigenschaft und mit der rechten Maustaste die kleine Miniaturansicht, die auf der linken Seite den Namen des Image-Objekt angezeigt wird. Wählen Sie **zurücksetzen**.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.PictureBox>
- [Übersicht über das PictureBox-Steuerelement](picturebox-control-overview-windows-forms.md)
- [Vorgehensweise: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Vorgehensweise: Festlegen von Bildern zur Laufzeit](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox-Steuerelement](picturebox-control-windows-forms.md)
