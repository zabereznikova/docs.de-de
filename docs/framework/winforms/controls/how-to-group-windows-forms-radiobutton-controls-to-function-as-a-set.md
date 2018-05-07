---
title: 'Gewusst wie: Gruppieren von RadioButton-Steuerelementen in Windows Forms für die Verwendung als Set'
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: cbc6ab410fa2ab9d89255f82863e51aad36f8c18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>Gewusst wie: Gruppieren von RadioButton-Steuerelementen in Windows Forms für die Verwendung als Set
Windows Forms <xref:System.Windows.Forms.RadioButton> Steuerelemente wurden dafür entwickelt, darin, Benutzern eine Auswahl aus mindestens zwei Einstellungen, von denen nur eine an eine Prozedur oder das Objekt zugewiesen werden kann. Angenommen, eine Gruppe von <xref:System.Windows.Forms.RadioButton> Steuerelemente können eine Auswahl von Transportunternehmen für eine Bestellung anzeigen, aber nur eines der Netzbetreiber verwendet werden. Daher nur ein <xref:System.Windows.Forms.RadioButton> zu einem Zeitpunkt kann ausgewählt werden, auch wenn sie einen Teil einer funktionalen Gruppe ist.  
  
 Sie Optionsfelder gruppieren, indem Sie z. B. innerhalb eines Containers Zeichnen einer <xref:System.Windows.Forms.Panel> -Steuerelement, ein <xref:System.Windows.Forms.GroupBox> Steuerelement oder ein Formular. Alle Optionsfelder, die direkt auf einem Formular werden einer Gruppe hinzugefügt werden. Um separate Gruppen hinzuzufügen, müssen Sie sie innerhalb von Bereichen oder Gruppenfelder platzieren. Weitere Informationen zu Bereichen oder Gruppenfelder, finden Sie unter [Übersicht über das Panel-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md) oder [Übersicht über das GroupBox-Steuerelement](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md).  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>Zum Gruppieren von RadioButton-Steuerelementen als einen Satz an die Funktion unabhängig von anderen Sätze  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.GroupBox> oder <xref:System.Windows.Forms.Panel> -Steuerelement aus der **Windows Forms** Registerkarte auf die **Toolbox** auf das Formular.  
  
2.  Zeichnen <xref:System.Windows.Forms.RadioButton> auf steuert die <xref:System.Windows.Forms.GroupBox> oder <xref:System.Windows.Forms.Panel> Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.RadioButton>  
 [Übersicht über das RadioButton-Steuerelement](../../../../docs/framework/winforms/controls/radiobutton-control-overview-windows-forms.md)  
 [Übersicht über das Panel-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Übersicht über das GroupBox-Steuerelement](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [Übersicht über das CheckBox-Steuerelement](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [RadioButton-Steuerelement](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
