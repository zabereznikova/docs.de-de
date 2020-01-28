---
title: Gruppieren von RadioButton-Steuerelementen als Satz
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: c4b37c84bf0f93837b91c743c7681d39fd83a659
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732955"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>Gewusst wie: Gruppieren von RadioButton-Steuerelementen in Windows Forms für die Verwendung als Set
Windows Forms <xref:System.Windows.Forms.RadioButton>-Steuerelemente sollen Benutzern eine Auswahl zwischen zwei oder mehr Einstellungen geben, von denen nur eine einer Prozedur oder einem Objekt zugewiesen werden kann. Beispielsweise kann eine Gruppe von <xref:System.Windows.Forms.RadioButton>-Steuerelementen eine Auswahl von Paket Trägern für eine Bestellung anzeigen, es wird jedoch nur einer der Betreiber verwendet. Daher kann jeweils nur eine <xref:System.Windows.Forms.RadioButton> ausgewählt werden, auch wenn Sie Teil einer Funktionsgruppe ist.  
  
 Sie gruppieren Options Felder, indem Sie Sie in einen Container, z. b. ein <xref:System.Windows.Forms.Panel> Steuerelement, ein <xref:System.Windows.Forms.GroupBox> Steuerelement oder ein Formular, zeichnen. Alle Options Felder, die einem Formular direkt hinzugefügt werden, werden zu einer Gruppe. Um separate Gruppen hinzuzufügen, müssen Sie Sie in Panels oder Gruppen Feldern platzieren. Weitere Informationen zu Panels oder Gruppen Feldern finden Sie unter Übersicht über das [Panel-Steuer](panel-control-overview-windows-forms.md) Element oder Übersicht über das [GroupBox-Steuer](groupbox-control-overview-windows-forms.md)Element.  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>So gruppieren Sie RadioButton-Steuerelemente als eine Menge, die unabhängig von anderen Sätzen funktioniert  
  
1. Ziehen Sie ein <xref:System.Windows.Forms.GroupBox> oder <xref:System.Windows.Forms.Panel> Steuerelement von der Registerkarte **Windows Forms** der **Toolbox** auf das Formular.  
  
2. Zeichnen Sie <xref:System.Windows.Forms.RadioButton> Steuerelemente auf der <xref:System.Windows.Forms.GroupBox> oder <xref:System.Windows.Forms.Panel> Steuerelement.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.RadioButton>
- [Übersicht über das RadioButton-Steuerelement](radiobutton-control-overview-windows-forms.md)
- [Übersicht über das Panel-Steuerelement](panel-control-overview-windows-forms.md)
- [Übersicht über das GroupBox-Steuerelement](groupbox-control-overview-windows-forms.md)
- [Übersicht über das CheckBox-Steuerelement](checkbox-control-overview-windows-forms.md)
- [RadioButton-Steuerelement](radiobutton-control-windows-forms.md)
