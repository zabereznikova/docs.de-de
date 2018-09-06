---
title: 'Gewusst wie: Laden eines Bilds mithilfe des Designers (Windows Forms)'
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: e01e5d1dc0fad8171e705e85debc2b15d6a506eb
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855958"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Gewusst wie: Laden eines Bilds mithilfe des Designers (Windows Forms)
Mit der Windows Forms <xref:System.Windows.Forms.PictureBox> -Steuerelement, können Sie laden und anzeigen ein Bilds auf einem Formular zur Entwurfszeit durch Festlegen der <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft, um ein gültiges Bild. Die folgende Tabelle zeigt die zulässigen Dateitypen.  
  
|Typ|Dateierweiterung|  
|----------|-------------------------|  
|Bitmap|.bmp|  
|Symbol|.ico|  
|GIF|GIF|  
|Metadatei|WMF|  
|JPEG|JPG|  
  
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
 <xref:System.Windows.Forms.PictureBox>  
 [Übersicht über das PictureBox-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [Gewusst wie: Festlegen von Bildern zur Laufzeit](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [PictureBox-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
