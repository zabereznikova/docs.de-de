---
title: 'Vorgehensweise: Gruppieren von RadioButton-Steuerelementen in Windows Forms für die Verwendung als Set'
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: 857e61bc89e072aebcf34793d7e8504ece3318c7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307257"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>Vorgehensweise: Gruppieren von RadioButton-Steuerelementen in Windows Forms für die Verwendung als Set
Windows Forms <xref:System.Windows.Forms.RadioButton> Steuerelemente Benutzern eine Auswahl aus zwei oder mehr Einstellungen geben die nur eine an eine Prozedur oder dem Objekt zugewiesen werden kann sollen. Z. B. eine Gruppe von <xref:System.Windows.Forms.RadioButton> Steuerelemente können eine Auswahl von Transportunternehmen für einen Auftrag anzeigen, aber nur ein Unternehmen ausgewählt werden kann. Aus diesem Grund nur eine <xref:System.Windows.Forms.RadioButton> zu einem Zeitpunkt kann ausgewählt werden, auch wenn es sich um einen Teil einer funktionalen Gruppe ist.  
  
 Gruppieren, Optionsfelder werden in einem Container z. B. eine <xref:System.Windows.Forms.Panel> -Steuerelement, ein <xref:System.Windows.Forms.GroupBox> Steuerelement oder Formular. Alle Optionsfelder, die direkt zu einer Form werden einer Gruppe hinzugefügt werden. Um separate Gruppen hinzuzufügen, müssen Sie sie innerhalb von Bereichen oder Gruppenfelder platzieren. Weitere Informationen zu Bereichen oder Gruppenfelder, finden Sie unter [Übersicht über Panel-Steuerelement](panel-control-overview-windows-forms.md) oder [Übersicht über das GroupBox-Steuerelement](groupbox-control-overview-windows-forms.md).  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>Zum Gruppieren von RadioButton-Steuerelementen als Gruppe unabhängig von anderen-Funktion  
  
1. Ziehen Sie eine <xref:System.Windows.Forms.GroupBox> oder <xref:System.Windows.Forms.Panel> -Steuerelement aus der **Windows Forms** Registerkarte die **Toolbox** auf das Formular.  
  
2. Zeichnen Sie <xref:System.Windows.Forms.RadioButton> steuert, auf die <xref:System.Windows.Forms.GroupBox> oder <xref:System.Windows.Forms.Panel> Steuerelement.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.RadioButton>
- [Übersicht über das RadioButton-Steuerelement](radiobutton-control-overview-windows-forms.md)
- [Übersicht über das Panel-Steuerelement](panel-control-overview-windows-forms.md)
- [Übersicht über das GroupBox-Steuerelement](groupbox-control-overview-windows-forms.md)
- [Übersicht über das CheckBox-Steuerelement](checkbox-control-overview-windows-forms.md)
- [RadioButton-Steuerelement](radiobutton-control-windows-forms.md)
