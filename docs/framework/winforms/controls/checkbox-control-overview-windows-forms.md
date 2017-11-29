---
title: "Übersicht über das CheckBox-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a154a3f639102e3f3e2acd62626379e12bbd1344
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="checkbox-control-overview-windows-forms"></a>Übersicht über das CheckBox-Steuerelement (Windows Forms)
Das Windows Forms-Steuerelement <xref:System.Windows.Forms.CheckBox> zeigt an, ob eine bestimmte Bedingung aktiviert oder deaktiviert ist. Es wird häufig verwendet, um dem Benutzer eine Ja/Nein- oder Wahr/Falsch-Auswahl zu präsentieren. Sie können Kontrollkästchen-Steuerelemente in Gruppen verwenden, um mehrere Optionen anzuzeigen, unter denen der Benutzer eine oder mehrere auswählen kann.  
  
 Das Kontrollkästchensteuerelement ähnelt das Optionsfeld-Steuerelement jeder verwendet wird, eine Auswahl an, die vom Benutzer stammt. Sie unterscheiden sich in, denen nur ein Optionsfeld in einer Gruppe zu einem Zeitpunkt ausgewählt werden kann. Mit dem Kontrollkästchen-Steuerelement kann jedoch eine beliebige Anzahl von Kontrollkästchen ausgewählt werden.  
  
 Ein Kontrollkästchen kann mit Elementen in einer Datenbank mit der einfachen Datenbindung verbunden sein. Mehrere Kontrollkästchen können gruppiert werden, mithilfe der <xref:System.Windows.Forms.GroupBox> Steuerelement. Dies eignet sich für die visuelle Darstellung und auch für den Entwurf der Benutzeroberfläche, da im Formular-Designer zusammen gruppierte Steuerelemente verschoben werden können. Weitere Informationen finden Sie unter [Windows Forms-Datenbindung](../../../../docs/framework/winforms/windows-forms-data-binding.md) und [GroupBox-Steuerelement](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).  
  
 Die <xref:System.Windows.Forms.CheckBox> Steuerelement verfügt über zwei wichtige Eigenschaften <xref:System.Windows.Forms.CheckBox.Checked%2A> und <xref:System.Windows.Forms.CheckBox.CheckState%2A>. Die <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft gibt entweder `true` oder `false`. Die <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft gibt entweder <xref:System.Windows.Forms.CheckState.Checked> oder <xref:System.Windows.Forms.CheckState.Unchecked>; oder, wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A> -Eigenschaftensatz auf `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> können zurückgeben <xref:System.Windows.Forms.CheckState.Indeterminate>. In den unbestimmten Zustand befindet wird das Dialogfeld angezeigt, abgeblendet, um anzugeben, dass die Option nicht verfügbar ist.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.CheckBox>  
 [Gewusst wie: Festlegen von Optionen mit CheckBox-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [Gewusst wie: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [CheckBox-Steuerelement](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
