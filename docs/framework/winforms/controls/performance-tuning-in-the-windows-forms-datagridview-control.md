---
title: Leistungsoptimierung im DataGridView-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: 77ad86c4cd606bcf074473c97371ec27bcc5605b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744273"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms
Beim Arbeiten mit großen Datenmengen kann das `DataGridView`-Steuerelement eine große Menge an Arbeitsspeicher beanspruchen, es sei denn, Sie verwenden es sorgfältig. Auf Clients mit eingeschränktem Arbeitsspeicher können Sie einen Teil dieses Aufwands vermeiden, indem Sie Features vermeiden, die hohe Arbeitsspeicher Kosten haben. Sie können auch einige oder alle Aufgaben zur Daten Wartung und-Abruf selbst verwalten, indem Sie den virtuellen Modus verwenden, um die Speicherauslastung für Ihr Szenario anzupassen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 Beschreibt, wie Sie das `DataGridView`-Steuerelement auf eine Weise verwenden können, die unnötige Speicherauslastung und Leistungseinbußen bei der Arbeit mit großen Datenmengen vermeidet.  
  
 [Virtueller Modus im DataGridView-Steuerelement in Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 Beschreibt, wie Sie den virtuellen Modus verwenden, um den standardmäßigen Daten Bindungs Mechanismus zu ergänzen oder zu ersetzen.  
  
 [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)  
 Beschreibt das Implementieren von Handlern für mehrere Ereignisse im virtuellen Modus. Außerdem wird veranschaulicht, wie ein Rollback auf Zeilenebene implementiert und ein Commit für Benutzer bearbeitvorgänge ausgeführt wird.  
  
 [Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 Beschreibt, wie Daten bei Bedarf geladen werden. Dies ist nützlich, wenn Sie mehr Daten anzeigen müssen, als der verfügbare Client Speicher speichern kann.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Windows.Forms.DataGridView>  
 Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 Enthält die Referenz Dokumentation für die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>-Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch

- [DataGridView-Steuerelement](datagridview-control-windows-forms.md)
- [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
