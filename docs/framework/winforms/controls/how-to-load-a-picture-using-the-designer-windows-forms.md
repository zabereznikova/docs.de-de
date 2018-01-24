---
title: 'Gewusst wie: Laden eines Bilds mithilfe des Designers (Windows Forms)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1dec3c71c0c93ce580925744fe55f05cd2e5f383
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Gewusst wie: Laden eines Bilds mithilfe des Designers (Windows Forms)
Mit dem Windows Forms <xref:System.Windows.Forms.PictureBox> -Steuerelement, laden und anzeigen ein Bilds auf einem Formular zur Entwurfszeit durch Festlegen der <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft, um ein gültiges Bild. Die folgende Tabelle zeigt die zulässige Dateitypen.  
  
|Typ|Dateinamenerweiterung|  
|----------|-------------------------|  
|Bitmap|.bmp|  
|Symbol|.ico|  
|GIF|GIF|  
|Metadatei|.wmf|  
|JPEG|.jpg|  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-display-a-picture-at-design-time"></a>Zum Anzeigen eines Bilds zur Entwurfszeit  
  
1.  Zeichnen einer <xref:System.Windows.Forms.PictureBox> Steuerelement eines Formulars.  
  
2.  Wählen Sie im Fenster Eigenschaften die <xref:System.Windows.Forms.PictureBox.Image%2A> -Eigenschaft, und klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um anzuzeigen die **öffnen** (Dialogfeld).  
  
3.  Wenn Sie für einen bestimmten Dateityp (z. B. GIF-Dateien) suchen, wählen Sie diese in die **Dateityp** Feld.  
  
4.  Wählen Sie die Datei, die Sie anzeigen möchten.  
  
### <a name="to-clear-the-picture-at-design-time"></a>So löschen Sie das Bild zur Entwurfszeit  
  
1.  Auf der **Eigenschaften** wählen die <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft und mit der rechten Maustaste die kleine Miniaturansicht, die auf der linken Seite des Namens des Image-Objekt angezeigt wird. Wählen Sie **zurücksetzen**.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.PictureBox>  
 [Übersicht über das PictureBox-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [Gewusst wie: Ändern der Größe oder Platzierung eines Bildes zur Laufzeit](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [Gewusst wie: Festlegen von Bildern zur Laufzeit](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [PictureBox-Steuerelement](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
