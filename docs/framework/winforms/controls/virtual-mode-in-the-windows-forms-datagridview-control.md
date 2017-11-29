---
title: Virtueller Modus im DataGridView-Steuerelement in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: DataGridView control [Windows Forms], virtual mode
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10c6afbcde22a82e6227ce1d95d57749bee1a88c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="virtual-mode-in-the-windows-forms-datagridview-control"></a>Virtueller Modus im DataGridView-Steuerelement in Windows Forms
Mit dem virtuellen Modus können Sie verwalten die Interaktion zwischen der <xref:System.Windows.Forms.DataGridView> -Steuerelement und einen benutzerdefinierten Datencache. Zum Implementieren des virtuellen Modus legen die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft `true` und eine oder mehrere der in diesem Thema beschriebenen Ereignisse zu behandeln. Behandeln Sie in der Regel mindestens die `CellValueNeeded` Ereignis, das Werte im Datencache Steuerelement suchen kann.  
  
## <a name="bound-mode-and-virtual-mode"></a>Gebundene und virtueller Modus  
 Virtueller Modus ist erforderlich, lediglich bei Bedarf zu ergänzen oder Ersetzen von gebundenen Modus. In den gebundenen Modus legen Sie die <xref:System.Windows.Forms.DataGridView.DataSource%2A> Eigenschaft und das Steuerelement automatisch lädt die Daten aus der angegebenen Quelle und sendet Benutzer ändert, zurück an. Sie können steuern, welche die gebundenen Spalten angezeigt werden, und die Datenquelle selbst behandelt normalerweise Vorgänge wie das Sortieren.  
  
## <a name="supplementing-bound-mode"></a>Ergänzen von gebundenen Modus  
 Gebundene Modus können Sie durch Anzeigen von ungebundenen Spalten zusammen mit gebundenen Spalten ergänzen. Dies wird manchmal als "gemischt" bezeichnet und eignet sich zum Anzeigen von z. B. berechnete Werte oder die Benutzeroberfläche (UI) gesteuert.  
  
 Da ungebundene Spalten außerhalb der Datenquelle sind, werden sie von der Datenquelle Sortieroperationen ignoriert. Deshalb beim Sortieren im gemischten Modus aktivieren, müssen Sie die ungebundenen Daten in einem lokalen Cache verwalten und virtuellen Modus implementieren, können die <xref:System.Windows.Forms.DataGridView> Steuerelement interagieren.  
  
 Weitere Informationen zur Verwendung des virtuellen Modus zur Erhaltung der Werte in ungebundenen Spalten finden Sie unter den Beispielen in der <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType> Eigenschaft und <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> – Referenzthemen zur Klasse.  
  
## <a name="replacing-bound-mode"></a>Ersetzen des gebundenen Modus  
 Wenn gebundene Modus Ihren leistungsanforderungen müssen nicht erfüllt, können Sie alle Ihre Daten in einem benutzerdefinierten Cache über Virtueller Modus Ereignishandler verwalten. Beispielsweise können virtuellen Modus implementieren eine just-in-Time Datenladevorgangs-Mechanismus, der nur Ruft Daten aus einer Datenbank im Netzwerk für eine optimale Leistung erforderlich ist. Dieses Szenario ist besonders nützlich, bei der Arbeit mit großen Mengen von Daten über eine langsame Netzwerkverbindung oder Clientcomputer, auf denen eine begrenzte Menge an Arbeitsspeicher oder Speicherplatz.  
  
 Weitere Informationen zur Verwendung des virtuellen Modus in einem Just-in-Time-Szenario finden Sie unter [Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## <a name="virtual-mode-events"></a>Ereignisse des virtuellen Modus  
 Wenn Ihre Daten nur lesen, ist die `CellValueNeeded` Ereignis möglicherweise das einzige Ereignis, das Sie behandeln müssen. Virtueller Modus Ereignisse können Sie bestimmte Funktionen wie die benutzerbearbeitungen, Zeile hinzufügen und löschen und Transaktionen auf Zeilenebene zu ermöglichen.  
  
 Einige Standard <xref:System.Windows.Forms.DataGridView> Ereignisse (z. B. Ereignisse, die auftreten, wenn Benutzer hinzufügen oder Löschen von Zeilen oder wenn Zellenwerte bearbeitet, analysiert, überprüft oder formatiert werden) im virtuellen Modus auch hilfreich sind. Sie können auch Ereignisse behandeln, mit denen Sie in der Regel nicht in einer gebundenen Datenquelle, wie Zelle QuickInfo-Text, Zelle und Zeilenfehlertext Zelle und Zeilendaten Verknüpfung-Menü und Höhe Zeilendaten gespeicherten Werte beibehalten.  
  
 Weitere Informationen zum Implementieren des virtuellen Modus zum Verwalten von Lese-Schreib-Daten mit einem Bereich auf Zeilenebene Commit finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
 Ein Beispiel für die Implementierung des virtuellen Modus mit einem Bereich auf Zellenebene Commit, finden Sie unter der <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Referenzthemen.  
  
 Die folgenden Ereignisse treten nur bei der <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> -Eigenschaftensatz auf `true`.  
  
|Ereignis|Beschreibung|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|Vom Steuerelement verwendeten, um einen Zellenwert aus dem Datencache für die Anzeige abzurufen. Dieses Ereignis tritt nur für Zellen in ungebundenen Spalten.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|Vom Steuerelement verwendeten, um Benutzereingaben für eine Zelle für den Datencache zu übernehmen. Dieses Ereignis tritt nur für Zellen in ungebundenen Spalten.<br /><br /> Rufen Sie die <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> Methode, wenn einen zwischengespeicherten Wert außerhalb des ändern eine <xref:System.Windows.Forms.DataGridView.CellValuePushed> Ereignishandler, um sicherzustellen, dass der aktuelle Wert im Steuerelement angezeigt wird und alle aktuell aktiven Größenänderung Modi anzuwenden.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|Vom Steuerelement verwendeten, um die Notwendigkeit für eine neue Zeile im Datencache anzugeben.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|Vom Steuerelement verwendeten, um festzustellen, ob eine Zeile nicht gespeicherte Änderungen verfügt.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|Vom Steuerelement verwendeten, um anzugeben, dass eine Zeile die zwischengespeicherten Werte zurückgesetzt werden soll.|  
  
 Die folgenden Ereignisse eignen sich in der virtuelle Modus, jedoch kann verwendet werden, unabhängig von der <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Einstellung der Eigenschaft.  
  
|Ereignisse|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|Vom Steuerelement verwendeten, um anzugeben, wenn Zeilen gelöscht oder hinzugefügt werden, und Sie den Datencache entsprechend aktualisieren.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|Vom Steuerelement formatiert Zellenwerte verwendeten für die Anzeige und zu analysieren und Validieren von Benutzereingaben.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|Zum Abrufen der Zelle QuickInfo-Text vom Steuerelement verwendeten bei der <xref:System.Windows.Forms.DataGridView.DataSource%2A> Eigenschaft festgelegt ist oder die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft ist `true`.<br /><br /> Zelle QuickInfos angezeigt werden nur, wenn die <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> Eigenschaftswert ist `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|Zum Abrufen der Zelle oder Zeile Fehlertext vom Steuerelement verwendeten bei der <xref:System.Windows.Forms.DataGridView.DataSource%2A> Eigenschaft festgelegt ist oder die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft ist `true`.<br /><br /> Rufen Sie die <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> Methode oder die <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> Methode, wenn Sie ändern den Fehlertext Zelle oder Zeile, um sicherzustellen, dass der aktuelle Wert im Steuerelement angezeigt wird.<br /><br /> Zellen- und Fehlersymbole angezeigt werden bei der <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> und <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A> Eigenschaftswerte sind `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|Zum Abrufen einer Zelle oder Zeile vom Steuerelement verwendeten <xref:System.Windows.Forms.ContextMenuStrip> Wenn das Steuerelement <xref:System.Windows.Forms.DataGridView.DataSource%2A> Eigenschaft festgelegt ist oder die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft ist `true`.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|Vom Steuerelement verwendeten, zum Abrufen oder Speichern von Informationen über die Zeilenhöhe im Datencache. Rufen Sie die <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> Methode, wenn die zwischengespeicherten Informationen über die Zeilenhöhe außerhalb von Ändern einer <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> -Ereignishandler, um sicherzustellen, dass der aktuelle Wert in der Anzeige des Steuerelements verwendet wird.|  
  
## <a name="best-practices-in-virtual-mode"></a>Empfohlene Vorgehensweisen in Virtueller Modus  
 Wenn Sie damit die effiziente Zusammenarbeit mit großen Mengen von Daten des virtuellen Modus implementieren, sollten Sie auch Stellen Sie sicher, dass Sie effizient arbeiten die <xref:System.Windows.Forms.DataGridView> selbst zu steuern. Weitere Informationen über die effiziente Verwendung von Zellenstilen, Größenänderung, Auswahl und Freigeben von Zeilen finden Sie unter [Best Practices zum Skalieren des DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 [Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
