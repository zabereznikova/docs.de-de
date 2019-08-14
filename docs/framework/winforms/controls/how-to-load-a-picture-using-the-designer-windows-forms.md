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
ms.openlocfilehash: 1d95d5baafa42c7dea40933ba837b684d90b7b2b
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972373"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Vorgehensweise: Laden eines Bilds mithilfe des Designers (Windows Forms)

Mit dem Windows Forms <xref:System.Windows.Forms.PictureBox> -Steuerelement können Sie ein Bild auf einem Formular zur Entwurfszeit laden und anzeigen, indem <xref:System.Windows.Forms.PictureBox.Image%2A> Sie die-Eigenschaft auf ein gültiges Bild festlegen. In der folgenden Tabelle sind die zulässigen Dateitypen aufgeführt.

|Typ|Dateinamenerweiterung|
|----------|-------------------------|
|Bitmap|. bmp|
|Symbol|.ico|
|GIF|GIF|
|Metadatei|. WMF|
|JPEG|JPG|

> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).

## <a name="to-display-a-picture-at-design-time"></a>So zeigen Sie ein Bild zur Entwurfszeit an

1. Zeichnen Sie <xref:System.Windows.Forms.PictureBox> ein-Steuerelement in einem Formular.

2. Wählen Sie auf der Eigenschaftenfenster die <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft aus, und klicken Sie auf die Schaltfläche mit den Auslassungs Punkten, um das Dialogfeld **Öffnen** anzuzeigen.

3. Wenn Sie nach einem bestimmten Dateityp suchen (z. b. GIF-Dateien), wählen Sie ihn im Feld **Dateityp aus** .

4. Wählen Sie die Datei aus, die Sie anzeigen möchten.

## <a name="to-clear-the-picture-at-design-time"></a>So löschen Sie das Bild zur Entwurfszeit

1. Wählen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft aus, und klicken Sie mit der rechten Maustaste auf das kleine Miniaturbild, das links neben dem Namen des Bildobjekts angezeigt wird. Wählen Sie **Zurücksetzen**.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.PictureBox>
- [Übersicht über das PictureBox-Steuerelement](picturebox-control-overview-windows-forms.md)
- [Vorgehensweise: Ändern der Größe oder Platzierung eines Bilds zur Laufzeit](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Vorgehensweise: Festlegen von Bildern zur Laufzeit](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox-Steuerelement](picturebox-control-windows-forms.md)
