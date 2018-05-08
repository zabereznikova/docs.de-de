---
title: Übersicht über das RadioButton-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
ms.openlocfilehash: 397808c055fd5ba5e8a73d47dfc7fee6c0cf2975
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="radiobutton-control-overview-windows-forms"></a>Übersicht über das RadioButton-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.RadioButton> Steuerelemente enthalten eine Reihe von mindestens zwei sich gegenseitig ausschließende Optionen für dem Benutzer. Während Optionsfelder und Kontrollkästchen scheinbar ordnungsgemäß funktionieren auf ähnliche Weise, gibt es einen wichtigen Unterschied: Wenn ein Benutzer ein Optionsfeld auswählt, die anderen Optionsfelder in der gleichen Gruppe kann nicht ausgewählt werden ebenfalls. Im Gegensatz dazu kann eine beliebige Anzahl von Kontrollkästchen ausgewählt werden. Definieren eine Gruppe von Optionsfeldern wird dem Benutzer mitgeteilt, "Dies ist eine Gruppe von Auswahlmöglichkeiten, die in denen Sie nur einen auswählen können."  
  
## <a name="using-the-control"></a>Verwenden des Steuerelements  
 Wenn eine <xref:System.Windows.Forms.RadioButton> Steuerelement geklickt wird, dessen <xref:System.Windows.Forms.RadioButton.Checked%2A> -Eigenschaftensatz auf `true` und die <xref:System.Windows.Forms.Control.Click> Ereignishandler wird aufgerufen. Der <xref:System.Windows.Forms.RadioButton.CheckedChanged> Ereignis wird ausgelöst, wenn der Wert des der <xref:System.Windows.Forms.RadioButton.Checked%2A> -Eigenschaft ändert. Wenn die <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> -Eigenschaftensatz auf `true` (Standard), das Optionsfeld ausgewählt ist, werden alle anderen in der Gruppe automatisch gelöscht. Diese Eigenschaft ist in der Regel legen Sie nur auf `false` eine zulässige Option wenn Validierungscode verwendet wird, um sicherzustellen, dass das Optionsfeld ausgewählt ist. Der im Steuerelement angezeigte Text wird festgelegt, mit der <xref:System.Windows.Forms.Control.Text%2A> -Eigenschaft, die Tastenkombinationen für Zugriffstasten enthalten kann. Eine Zugriffstaste ermöglicht einem Benutzer das Steuerelement "auf", durch Drücken der ALT-Taste und der Zugriffstaste. Weitere Informationen finden Sie unter [wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) und [Vorgehensweise: Festlegen der Text, die durch ein Windows Forms-Steuerelement angezeigt](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 Die <xref:System.Windows.Forms.RadioButton> Steuerelement kann angezeigt werden, wie eine Befehlsschaltfläche, die angezeigt wird, falls es ausgewählt, wenn wurden die <xref:System.Windows.Forms.RadioButton.Appearance%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.Appearance.Button>. Optionsfelder können auch anzeigen, Bilder, die mithilfe der <xref:System.Windows.Forms.ButtonBase.Image%2A> und <xref:System.Windows.Forms.ButtonBase.ImageList%2A> Eigenschaften. Weitere Informationen finden Sie unter [Vorgehensweise: Legen Sie das Bild nicht angezeigt durch ein Windows Forms-Steuerelement](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.RadioButton>  
 [Übersicht über das Panel-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Übersicht über das GroupBox-Steuerelement](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [Übersicht über das CheckBox-Steuerelement](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Texts](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Gewusst wie: Gruppieren von RadioButton-Steuerelementen in Windows Forms für die Verwendung als Set](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)  
 [RadioButton-Steuerelement](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
