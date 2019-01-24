---
title: 'Vorgehensweise: Festlegen des Hintergrunds eines Windows Forms-Bereichs mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: be0359e13bcab868374189c6b42df392327b8eb8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645061"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Vorgehensweise: Festlegen des Hintergrunds eines Windows Forms-Bereichs mithilfe des Designers
Ein Windows Forms <xref:System.Windows.Forms.Panel> Steuerelement kann sowohl eine Hintergrundfarbe und ein Bild als Hintergrund anzeigen. Die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft legt die Hintergrundfarbe für Steuerelemente, die in den Bereich, z. B. Bezeichnungen enthalten sind, und Optionsfelder fest. Wenn die <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft nicht festgelegt ist, die <xref:System.Windows.Forms.Control.BackColor%2A> Auswahl werden alle im Bereich ausfüllen. Wenn die <xref:System.Windows.Forms.Control.BackgroundImage%2A> -Eigenschaft festgelegt ist, erscheint das Bild hinter den Steuerelementen, die im Bereich enthalten sind.  
  
 Das folgende Verfahren benötigt eine **Windows-Anwendung** -Projekt mit einem Formular, enthält eine <xref:System.Windows.Forms.Panel> Steuerelement. Informationen zum Festlegen eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-the-background-in-the-windows-forms-designer"></a>Zum Festlegen von Hintergrund in der Windows Forms-Designer  
  
1.  Wählen Sie das <xref:System.Windows.Forms.Panel>-Steuerelement.  
  
2.  In der **Eigenschaften** Fenster, klicken Sie auf der Pfeil-Schaltfläche neben dem <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft, um ein Fenster mit drei Registerkarten anzuzeigen.  
  
3.  Wählen Sie die **benutzerdefinierte** Tab, um ein Farben-Palette anzuzeigen.  
  
4.  Wählen Sie die **Web** oder **System** Registerkarte, um eine Liste der vordefinierten Namen für Farben anzuzeigen, und klicken Sie dann eine andere Farbe auswählen.  
  
5.  In der **Eigenschaften** Fenster, klicken Sie auf der Pfeil-Schaltfläche neben dem <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft.  
  
6.  In der **öffnen** Dialogfeld Feld, wählen Sie die Datei, die Sie anzeigen möchten.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Panel-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)
- [Übersicht über das Panel-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)
- [Vorgehensweise: Gruppieren von Steuerelementen mit dem Panel-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)
