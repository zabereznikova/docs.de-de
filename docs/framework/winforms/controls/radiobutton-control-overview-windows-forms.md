---
title: Übersicht über das RadioButton-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
ms.openlocfilehash: bbc93046b69d39caadde4986ff56f067fc206a9e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741134"
---
# <a name="radiobutton-control-overview-windows-forms"></a>Übersicht über das RadioButton-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.RadioButton>-Steuerelemente stellen dem Benutzer einen Satz von zwei oder mehr gegenseitig ausschließender Auswahlmöglichkeiten zur Verfügung. Es ist zwar möglich, dass Options Felder und Kontrollkästchen ähnlich funktionieren, es gibt jedoch einen wichtigen Unterschied: Wenn ein Benutzer eine Options Schaltfläche auswählt, können die anderen Options Felder in der gleichen Gruppe ebenfalls nicht ausgewählt werden. Im Gegensatz dazu können beliebig viele Kontrollkästchen ausgewählt werden. Durch Definieren einer Optionsfeld Gruppe wird dem Benutzer mitgeteilt, dass es sich hier um einen Satz von Auswahl Optionen handelt, von denen Sie nur eine auswählen können.  
  
## <a name="using-the-control"></a>Verwenden des Steuer Elements  
 Wenn auf ein <xref:System.Windows.Forms.RadioButton>-Steuerelement geklickt wird, wird dessen <xref:System.Windows.Forms.RadioButton.Checked%2A>-Eigenschaft auf `true` festgelegt, und der <xref:System.Windows.Forms.Control.Click> Ereignishandler wird aufgerufen. Das <xref:System.Windows.Forms.RadioButton.CheckedChanged>-Ereignis wird ausgelöst, wenn sich der Wert der <xref:System.Windows.Forms.RadioButton.Checked%2A>-Eigenschaft ändert. Wenn die <xref:System.Windows.Forms.RadioButton.AutoCheck%2A>-Eigenschaft auf `true` (Standard) festgelegt ist, werden alle anderen in der Gruppe automatisch gelöscht, wenn das Optionsfeld ausgewählt ist. Diese Eigenschaft wird in der Regel nur auf `false` festgelegt, wenn der Überprüfungs Code verwendet wird, um sicherzustellen, dass das Optionsfeld ausgewählt ist. Der im-Steuerelement angezeigte Text wird mit der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft festgelegt, die Zugriffstasten Kombinationen enthalten kann. Mithilfe einer Zugriffstaste kann ein Benutzer durch Drücken der Alt-Taste mit der Zugriffstaste auf das Steuerelement klicken. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen von Zugriffs Schlüsseln für Windows Forms Steuerelemente](how-to-create-access-keys-for-windows-forms-controls.md) und Gewusst [wie: Festlegen des Texts, der von einem Windows Forms Steuerelement angezeigt wird](how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 Das <xref:System.Windows.Forms.RadioButton> Steuerelement kann wie eine Befehls Schaltfläche angezeigt werden, die ggf. als nicht markiert angezeigt wird, wenn die Eigenschaft <xref:System.Windows.Forms.RadioButton.Appearance%2A> auf <xref:System.Windows.Forms.Appearance.Button>festgelegt ist. Mithilfe von Options Feldern können auch Bilder mithilfe der Eigenschaften <xref:System.Windows.Forms.ButtonBase.Image%2A> und <xref:System.Windows.Forms.ButtonBase.ImageList%2A> angezeigt werden. Weitere Informationen finden Sie unter Gewusst [wie: Festlegen des Bilds, das von einem Windows Forms-Steuerelement angezeigt wird](how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.RadioButton>
- [Übersicht über das Panel-Steuerelement](panel-control-overview-windows-forms.md)
- [Übersicht über das GroupBox-Steuerelement](groupbox-control-overview-windows-forms.md)
- [Übersicht über das CheckBox-Steuerelement](checkbox-control-overview-windows-forms.md)
- [Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](how-to-create-access-keys-for-windows-forms-controls.md)
- [Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Texts](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Gewusst wie: Gruppieren von RadioButton-Steuerelementen in Windows Forms für die Verwendung als Set](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)
- [RadioButton-Steuerelement](radiobutton-control-windows-forms.md)
