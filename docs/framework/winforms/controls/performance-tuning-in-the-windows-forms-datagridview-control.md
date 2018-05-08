---
title: Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: 97bf6f36ce029f879c3524fa92df08a483c2cb77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms
Bei der Arbeit mit großen Mengen von Daten, die `DataGridView` Steuerelement nutzen kann eine große Menge an Arbeitsspeicher in Mehraufwand, es sei denn, Sie sorgfältig verwenden. Auf Clients mit begrenzten Arbeitsspeicher können Sie vermeiden einige dieser Aufwand durch das Vermeiden der Funktionen, die über eine hohe Arbeitsspeicher Kosten. Darüber hinaus können Sie einige oder alle der Datenwartung verwalten und Aufgaben auf Abruf selbst unter Verwendung des virtuellen Modus vorzunehmen, um die Auslastung des Speichers für Ihr Szenario anzupassen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 Beschreibt, wie die `DataGridView` -Steuerelement in einer Weise, die nicht benötigte Arbeitsspeicher nutzungs- und Leistungsdaten Sanktionen wird vermieden, bei der Arbeit mit großen Mengen von Daten.  
  
 [Virtueller Modus im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 Beschreibt, wie der virtuelle Modus ergänzen oder ersetzen den Standardmechanismus für die Datenbindung.  
  
 [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 Beschreibt, wie Ereignishandler für mehrere Ereignisse des virtuellen Modus implementieren. Außerdem veranschaulicht, wie auf Zeilenebene Rollback und Commit für die benutzerbearbeitungen implementiert.  
  
 [Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 Beschreibt, wie Daten bei Bedarf zu laden, was nützlich ist, wenn weitere Daten, die angezeigt wird, als der verfügbaren Clientnamen-Speicher gespeichert werden kann.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Windows.Forms.DataGridView>  
 Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch  
 [DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
