---
title: Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: d425488adb8569a48333de4f8c0312143029fbe0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703163"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms
Bei der Arbeit mit großen Mengen von Daten, die `DataGridView` Steuerelement kann eine große Menge an Arbeitsspeicher, Aufwand, nutzen, es sei denn, Sie es mit Vorsicht verwenden. Auf Clients mit eingeschränktem Arbeitsspeicher können Sie vermeiden einige von diesen zusätzlichen Aufwand durch Funktionen, die eine hohe Arbeitsspeicher, Kosten zu vermeiden. Sie können auch verwalten, einige oder alle der Wartung von Daten aus, und Abrufen von Aufgaben selbst unter Verwendung des virtuellen Modus vorzunehmen, um die Auslastung des Speichers für Ihr Szenario anzupassen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 Beschreibt, wie die `DataGridView` -Steuerelement in einer Weise, die Strafen für nicht benötigte Arbeitsspeicher nutzungs- und Leistungsdaten vermeidet, bei der Arbeit mit großen Datenmengen.  
  
 [Virtueller Modus im DataGridView-Steuerelement in Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 Beschreibt, wie virtuelle Modus zum ergänzen oder ersetzen den Standardmechanismus für die Datenbindung verwenden.  
  
 [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)  
 Beschreibt, wie Handler für mehrere Ereignisse des virtuellen Modus implementieren. Außerdem veranschaulicht, wie auf Zeilenebene Rollback und Commit für die benutzerbearbeitungen implementiert.  
  
 [Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 Beschreibt, wie zum Laden von Daten bei Bedarf, was nützlich ist, wenn weitere Daten angezeigt werden, als der verfügbare Client-Speicher gespeichert werden kann.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Windows.Forms.DataGridView>  
 Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch
- [DataGridView-Steuerelement](datagridview-control-windows-forms.md)
- [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
