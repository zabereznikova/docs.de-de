---
title: 'Vorgehensweise: Festlegen des Hintergrunds eines Windows Forms-Bereichs mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 6927a7118c43ced03623a9764a3ef1e0814c95cb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211640"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Vorgehensweise: Festlegen des Hintergrunds eines Windows Forms-Bereichs, der mithilfe des Designers

Ein Windows Forms <xref:System.Windows.Forms.Panel> Steuerelement kann sowohl eine Hintergrundfarbe und ein Bild als Hintergrund anzeigen. Die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft legt die Hintergrundfarbe für Steuerelemente, die in den Bereich, z. B. Bezeichnungen enthalten sind, und Optionsfelder fest. Wenn die <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft nicht festgelegt ist, die <xref:System.Windows.Forms.Control.BackColor%2A> Auswahl werden alle im Bereich ausfüllen. Wenn die <xref:System.Windows.Forms.Control.BackgroundImage%2A> -Eigenschaft festgelegt ist, erscheint das Bild hinter den Steuerelementen, die im Bereich enthalten sind.

Das folgende Verfahren benötigt eine **Windows-Anwendung** -Projekt mit einem Formular, enthält eine <xref:System.Windows.Forms.Panel> Steuerelement. Informationen zum Festlegen eines solchen Projekts in Visual Studio finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="set-the-background-in-the-windows-forms-designer"></a>Festlegen des Hintergrunds im Windows Forms-Designer

1. Öffnen Sie das Projekt in Visual Studio, und wählen Sie die <xref:System.Windows.Forms.Panel> Steuerelement.

2. In der **Eigenschaften** Fenster, klicken Sie auf der Pfeil-Schaltfläche neben dem <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft, um ein Fenster mit drei Registerkarten anzuzeigen.

3. Wählen Sie die **benutzerdefinierte** Tab, um ein Farben-Palette anzuzeigen.

4. Wählen Sie die **Web** oder **System** Registerkarte, um eine Liste der vordefinierten Namen für Farben anzuzeigen, und klicken Sie dann eine andere Farbe auswählen.

5. In der **Eigenschaften** Fenster, klicken Sie auf der Pfeil-Schaltfläche neben dem <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft.

6. In der **öffnen** Dialogfeld Feld, wählen Sie die Datei, die Sie anzeigen möchten.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Panel-Steuerelement](panel-control-windows-forms.md)
- [Übersicht über das Panel-Steuerelement](panel-control-overview-windows-forms.md)
- [Vorgehensweise: Gruppieren von Steuerelementen mit dem Panel-Steuerelement in Windows Forms mithilfe des Designers](group-controls-with-wf-panel-control-using-the-designer.md)
