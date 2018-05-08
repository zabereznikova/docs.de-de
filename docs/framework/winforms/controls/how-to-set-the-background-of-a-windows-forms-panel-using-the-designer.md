---
title: 'Gewusst wie: Festlegen des Hintergrunds eines Windows Forms-Bereichs mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 896aa61f3f0900760dffd09bcab6a08bbc01628d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Gewusst wie: Festlegen des Hintergrunds eines Windows Forms-Bereichs mithilfe des Designers
Eine Windows Forms <xref:System.Windows.Forms.Panel> -Steuerelement kann eine Hintergrundfarbe und ein Hintergrundbild anzeigen. Die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft legt die Hintergrundfarbe für Steuerelemente, die in der Systemsteuerung, wie Beschriftungen enthalten sind und Optionsfelder fest. Wenn die <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft nicht festgelegt ist, die <xref:System.Windows.Forms.Control.BackColor%2A> Auswahl werden alle im Bereich auszufüllen. Wenn die <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft festgelegt ist, wird das Bild angezeigt, hinter den Steuerelementen, die im Bereich enthalten sind.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** -Projekts mit einem Formular, enthält ein <xref:System.Windows.Forms.Panel> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-the-background-in-the-windows-forms-designer"></a>Der Hintergrund in Windows Forms-Designer festlegen.  
  
1.  Wählen Sie das <xref:System.Windows.Forms.Panel>-Steuerelement.  
  
2.  In der **Eigenschaften** Fenster, klicken Sie auf der Pfeil neben der <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft, um ein Fenster mit drei Registerkarten angezeigt.  
  
3.  Wählen Sie die **benutzerdefinierte** Tab, um ein Farben-Palette anzuzeigen.  
  
4.  Wählen Sie die **Web** oder **System** Registerkarte, um eine Liste der vordefinierten Namen für Farben anzuzeigen, und klicken Sie dann eine andere Farbe auswählen.  
  
5.  In der **Eigenschaften** Fenster, klicken Sie auf der Pfeil neben der <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft.  
  
6.  In der **öffnen** Dialogfeld wählen die Datei, die Sie anzeigen möchten.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Control.BackColor%2A>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [Panel-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Übersicht über das Panel-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Gewusst wie: Gruppieren von Steuerelementen mit dem Windows Forms-Bereichssteuerelement im Designer](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)
