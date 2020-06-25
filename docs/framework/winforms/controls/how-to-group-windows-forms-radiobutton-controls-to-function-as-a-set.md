---
title: Gruppieren von RadioButton-Steuerelementen als Satz
description: Erfahren Sie, wie Sie Windows Forms RadioButton-Steuerelemente gruppieren, um unabhängig von anderen Sätzen zu funktionieren.
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: 9f6795330922e739cca1f2b5c11bb2ec68bb4e84
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325919"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>Vorgehensweise: Gruppieren von RadioButton-Steuerelementen in Windows Forms für die Verwendung als Set
Windows Forms Steuer <xref:System.Windows.Forms.RadioButton> Elemente dienen dazu, Benutzern eine Auswahl zwischen zwei oder mehr Einstellungen zu geben, denen nur eine Prozedur oder ein Objekt zugewiesen werden kann. Beispielsweise kann eine Gruppe von Steuer <xref:System.Windows.Forms.RadioButton> Elementen eine Auswahl von Paket Trägern für eine Bestellung anzeigen, es wird jedoch nur einer der Träger verwendet. Daher kann nur jeweils eine <xref:System.Windows.Forms.RadioButton> ausgewählt werden, auch wenn Sie Teil einer Funktionsgruppe ist.  
  
 Sie gruppieren Options Felder, indem Sie Sie in einem Container, z. b. einem <xref:System.Windows.Forms.Panel> Steuerelement, einem <xref:System.Windows.Forms.GroupBox> Steuerelement oder einem Formular, zeichnen. Alle Options Felder, die einem Formular direkt hinzugefügt werden, werden zu einer Gruppe. Um separate Gruppen hinzuzufügen, müssen Sie Sie in Panels oder Gruppen Feldern platzieren. Weitere Informationen zu Panels oder Gruppen Feldern finden Sie unter Übersicht über das [Panel-Steuer](panel-control-overview-windows-forms.md) Element oder Übersicht über das [GroupBox-Steuer](groupbox-control-overview-windows-forms.md)Element.  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>So gruppieren Sie RadioButton-Steuerelemente als eine Menge, die unabhängig von anderen Sätzen funktioniert  
  
1. Ziehen Sie ein-Steuerelement oder ein- <xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.Panel> Steuerelement von der Registerkarte **Windows Forms** der **Toolbox** auf das Formular.  
  
2. Zeichnen Sie <xref:System.Windows.Forms.RadioButton> Steuerelemente auf dem- <xref:System.Windows.Forms.GroupBox> oder-Steuerelement <xref:System.Windows.Forms.Panel> .  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.RadioButton>
- [Übersicht über das RadioButton-Steuerelement](radiobutton-control-overview-windows-forms.md)
- [Übersicht über das Panel-Steuerelement](panel-control-overview-windows-forms.md)
- [Übersicht über das GroupBox-Steuerelement](groupbox-control-overview-windows-forms.md)
- [Übersicht über das CheckBox-Steuerelement](checkbox-control-overview-windows-forms.md)
- [RadioButton-Steuerelement](radiobutton-control-windows-forms.md)
