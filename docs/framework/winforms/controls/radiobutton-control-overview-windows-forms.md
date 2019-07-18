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
ms.openlocfilehash: 1210658226d9bcacbf4904fdc90a9908c34f5b73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755947"
---
# <a name="radiobutton-control-overview-windows-forms"></a>Übersicht über das RadioButton-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.RadioButton> Steuerelemente enthalten eine Reihe von mindestens zwei sich gegenseitig ausschließende Auswahlmöglichkeiten für dem Benutzer. Aber Optionsfelder und Kontrollkästchen angezeigt kann auf ähnliche Weise funktionieren, es ist ein wichtiger Unterschied: Wenn ein Benutzer ein Optionsfeld auswählt, die anderen Optionsfelder in der gleichen Gruppe kann nicht ebenfalls ausgewählt sein. Im Gegensatz dazu kann eine beliebige Anzahl von Kontrollkästchen ausgewählt werden. Definieren eine Gruppe von Optionsfeldern wird dem Benutzer mitgeteilt, "Hier ist ein Satz von Optionen, die in denen Sie nur eine auswählen können."  
  
## <a name="using-the-control"></a>Verwenden des Steuerelements  
 Wenn eine <xref:System.Windows.Forms.RadioButton> Steuerelement geklickt wird, seine <xref:System.Windows.Forms.RadioButton.Checked%2A> -Eigenschaftensatz auf `true` und die <xref:System.Windows.Forms.Control.Click> Ereignishandler wird aufgerufen. Die <xref:System.Windows.Forms.RadioButton.CheckedChanged> Ereignis wird ausgelöst, wenn der Wert des der <xref:System.Windows.Forms.RadioButton.Checked%2A> eigenschaftenänderungen. Wenn die <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> -Eigenschaftensatz auf `true` (Standardeinstellung), das Optionsfeld ausgewählt ist, werden alle anderen in der Gruppe automatisch gelöscht. Diese Eigenschaft ist in der Regel legen Sie nur auf `false` Wenn Code für die Überprüfung verwendet wird, um sicherzustellen, dass das Optionsfeld ausgewählt, wird eine zulässige Option. Der Text innerhalb des Steuerelements wird festgelegt, mit der <xref:System.Windows.Forms.Control.Text%2A> -Eigenschaft, die Tastenkombinationen für den Zugriff enthalten kann. Eine Zugriffstaste ermöglicht einen Benutzer das Steuerelement "click", durch Drücken der ALT-Taste durch den Zugriffsschlüssel an. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Zugriffstasten für Windows-Steuerelemente Forms](how-to-create-access-keys-for-windows-forms-controls.md) und [Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement](how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 Die <xref:System.Windows.Forms.RadioButton> Steuerelement angezeigt werden kann, wie eine Befehlsschaltfläche, die angezeigt wird, falls es ausgewählt wird, wenn wurden die <xref:System.Windows.Forms.RadioButton.Appearance%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.Appearance.Button>. Optionsfelder können auch anzeigen, Bilder, die mit der <xref:System.Windows.Forms.ButtonBase.Image%2A> und <xref:System.Windows.Forms.ButtonBase.ImageList%2A> Eigenschaften. Weitere Informationen finden Sie unter [Vorgehensweise: Das Bild angezeigt, die von einer Windows Forms-Steuerelement](how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.RadioButton>
- [Übersicht über das Panel-Steuerelement](panel-control-overview-windows-forms.md)
- [Übersicht über das GroupBox-Steuerelement](groupbox-control-overview-windows-forms.md)
- [Übersicht über das CheckBox-Steuerelement](checkbox-control-overview-windows-forms.md)
- [Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](how-to-create-access-keys-for-windows-forms-controls.md)
- [Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Vorgehensweise: Gruppe Windows Forms-RadioButton-Steuerelementen in als Gruppe](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)
- [RadioButton-Steuerelement](radiobutton-control-windows-forms.md)
