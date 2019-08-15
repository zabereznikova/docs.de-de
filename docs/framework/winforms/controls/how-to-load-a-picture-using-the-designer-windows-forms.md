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
ms.openlocfilehash: 818bc63b5b3bea6c73804f716a72ba3cd1a62b4c
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039680"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Vorgehensweise: Laden eines Bilds mithilfe des Designers (Windows Forms)

Mit dem Windows Forms <xref:System.Windows.Forms.PictureBox> -Steuerelement können Sie ein Bild auf einem Formular zur Entwurfszeit laden und anzeigen, indem <xref:System.Windows.Forms.PictureBox.Image%2A> Sie die-Eigenschaft auf ein gültiges Bild festlegen. In der folgenden Tabelle sind die zulässigen Dateitypen aufgeführt.

|Typ|Dateinamenerweiterung|
|---|---|
|Bitmap|. bmp|
|Symbol|.ico|
|GIF|GIF|
|Metadatei|. WMF|
|JPEG|JPG|

## <a name="to-display-a-picture-at-design-time"></a>So zeigen Sie ein Bild zur Entwurfszeit an

1. Zeichnen Sie <xref:System.Windows.Forms.PictureBox> ein-Steuerelement in einem Formular.

2. Wählen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.PictureBox.Image%2A> Eigenschaft aus, und klicken Sie dann auf die Schaltfläche mit den Auslassungs Punkten, um das Dialogfeld **Öffnen** anzuzeigen.

3. Wenn Sie nach einem bestimmten Dateityp suchen (z. b. GIF-Dateien), wählen Sie ihn im Feld **Dateityp aus** .

4. Wählen Sie die Datei aus, die Sie anzeigen möchten.

## <a name="to-clear-the-picture-at-design-time"></a>So löschen Sie das Bild zur Entwurfszeit

1. Wählen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.PictureBox.Image%2A> -Eigenschaft aus. Klicken Sie mit der rechten Maustaste auf das kleine Miniaturbild, das links neben dem Namen des Bildobjekts angezeigt wird, und wählen Sie dann **Zurücksetzen**aus.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.PictureBox>
- [Übersicht über das PictureBox-Steuerelement](picturebox-control-overview-windows-forms.md)
- [Vorgehensweise: Ändern der Größe oder Platzierung eines Bilds zur Laufzeit](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Vorgehensweise: Festlegen von Bildern zur Laufzeit](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox-Steuerelement](picturebox-control-windows-forms.md)
