---
title: Übersicht über das CheckBox-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
ms.openlocfilehash: 5e81ac9e8830333e5aadb195563b25fdd93895c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733284"
---
# <a name="checkbox-control-overview-windows-forms"></a>Übersicht über das CheckBox-Steuerelement (Windows Forms)
Das Windows Forms-Steuerelement <xref:System.Windows.Forms.CheckBox> zeigt an, ob eine bestimmte Bedingung aktiviert oder deaktiviert ist. Es wird häufig verwendet, um dem Benutzer eine Ja/Nein- oder Wahr/Falsch-Auswahl zu präsentieren. Sie können Kontrollkästchen-Steuerelemente in Gruppen verwenden, um mehrere Optionen anzuzeigen, unter denen der Benutzer eine oder mehrere auswählen kann.  
  
 Das Kontrollkästchensteuerelement ähnelt das Optionsfeld-Steuerelement, da jede verwendet wird, eine Auswahl an, die vom Benutzer vorgenommen wird. Sie unterscheiden sich, in, denen nur ein Optionsfeld in einer Gruppe zu einem Zeitpunkt ausgewählt werden kann. Mit dem Kontrollkästchen-Steuerelement kann jedoch eine beliebige Anzahl von Kontrollkästchen ausgewählt werden.  
  
 Ein Kontrollkästchen kann auf Elemente in einer Datenbank mit einfacher Datenbindung verbunden sein. Mehrere Kontrollkästchen können gruppiert werden, mithilfe der <xref:System.Windows.Forms.GroupBox> Steuerelement. Dies ist nützlich, für die visuelle Darstellung und für die Gestaltung der Benutzeroberfläche, da die Formular-Designer zusammen gruppierte Steuerelemente verschoben werden können. Weitere Informationen finden Sie unter [Windows Forms-Datenbindung](../../../../docs/framework/winforms/windows-forms-data-binding.md) und [GroupBox-Steuerelement](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).  
  
 Die <xref:System.Windows.Forms.CheckBox> Steuerelement hat zwei wichtige Eigenschaften, <xref:System.Windows.Forms.CheckBox.Checked%2A> und <xref:System.Windows.Forms.CheckBox.CheckState%2A>. Die <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft gibt `true` oder `false`. Die <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft gibt <xref:System.Windows.Forms.CheckState.Checked> oder <xref:System.Windows.Forms.CheckState.Unchecked>; oder, wenn Sie die <xref:System.Windows.Forms.CheckBox.ThreeState%2A> -Eigenschaftensatz auf `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> können zurückgeben <xref:System.Windows.Forms.CheckState.Indeterminate>. In den unbestimmten Zustand befindet wird das Kontrollkästchen abgeblendet, um anzugeben, dass die Option nicht verfügbar ist.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.CheckBox>
- [Vorgehensweise: Festlegen von Optionen mit CheckBox-Steuerelementen für Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)
- [Vorgehensweise: Reagieren Sie auf Windows Forms das Klicken auf Kontrollkästchen](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox-Steuerelement](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
