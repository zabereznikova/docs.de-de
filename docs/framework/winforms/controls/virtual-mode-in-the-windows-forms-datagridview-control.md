---
title: Virtueller Modus im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], virtual mode
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
ms.openlocfilehash: f2ab0cc789b026a139e1421b72e9215bf52c6147
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672018"
---
# <a name="virtual-mode-in-the-windows-forms-datagridview-control"></a>Virtueller Modus im DataGridView-Steuerelement in Windows Forms
Mit virtuellen Modus befindet, können Sie verwalten, die Interaktion zwischen der <xref:System.Windows.Forms.DataGridView> Steuerelement und einer Zwischenspeicherung von benutzerdefinierten Daten. Legen Sie zum Implementieren des virtuellen Modus der <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft `true` und Behandeln eines oder mehrere der in diesem Thema beschriebenen Ereignisse. Behandeln Sie in der Regel mindestens die `CellValueNeeded` -Ereignis, das dem Steuerelement nach Werten in Datencache suchen ermöglicht.  
  
## <a name="bound-mode-and-virtual-mode"></a>Gebundene und der virtuelle Modus  
 Virtueller Modus ist erforderlich, nur, wenn Sie ergänzen oder gebundenen ersetzen möchten. In den gebundenen Modus legen Sie die <xref:System.Windows.Forms.DataGridView.DataSource%2A> -Eigenschaft und das Steuerelement automatisch lädt die Daten aus der angegebenen Quelle und sendet, ändert sich der Benutzer zu ihr zurückkehrt. Sie können steuern, welche die gebundenen Spalten angezeigt werden, und die Datenquelle selbst übernimmt in der Regel Operationen, z. B. die Sortierung.  
  
## <a name="supplementing-bound-mode"></a>Ergänzen des gebundenen Modus  
 Gebundene Modus können Sie durch Anzeigen von ungebundenen Spalten sowie die gebundenen Spalten ergänzen. Dies wird auch als "gemischten Modus" bezeichnet und eignet sich für die Anzeige von z. B. berechnete Werte oder die Benutzeroberfläche (UI) gesteuert.  
  
 Da ungebundene Spalten außerhalb der Datenquelle sind, werden sie von der Datenquelle Sortiervorgänge ignoriert. Aus diesem Grund, wenn Sie die Sortierung im gemischten Modus aktivieren, müssen Sie die ungebundenen Daten in einem lokalen Cache verwalten und Implementieren des virtuellen Modus befindet, können die <xref:System.Windows.Forms.DataGridView> Steuerelement interagieren.  
  
 Weitere Informationen zur Verwendung des virtuellen Modus zur Erhaltung der Werte in ungebundenen Spalten finden Sie unter den Beispielen in den <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType> Eigenschaft und <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> – Referenzthemen zur Klasse.  
  
## <a name="replacing-bound-mode"></a>Ersetzen des gebundenen Modus  
 Wenn gebundene-Modus nicht Ihren leistungsanforderungen erfüllt, können Sie alle Ihre Daten in einem benutzerdefinierten Cache über Ereignishandler im virtuellen Modus verwalten. Beispielsweise können virtuellen Modus zum Implementieren eines Mechanismus, der nur ruft der just-in-Time Datenladevorgangs so viele Daten aus einer Datenbank im Netzwerk wie für eine optimale Leistung erforderlich ist. Dieses Szenario ist besonders nützlich, bei der Arbeit mit großen Mengen von Daten über eine langsame Netzwerkverbindung oder mit Clientcomputer, die eine begrenzte Menge an Arbeitsspeicher oder ein Speicherplatz aufweisen.  
  
 Weitere Informationen zur Verwendung des virtuellen Modus in einem just-in-Time-Szenario finden Sie unter [Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## <a name="virtual-mode-events"></a>Ereignisse des virtuellen Modus  
 Wenn Ihre Daten nur lesen, ist die `CellValueNeeded` Ereignis möglicherweise das einzige Ereignis, das Sie behandeln müssen. Zusätzliche im virtuellen Modus Ereignisse können Sie bestimmte Funktionen wie die benutzerbearbeitungen, Zeilen und löschen und auf Zeilenebene Transaktionen zu ermöglichen.  
  
 Einige Standard <xref:System.Windows.Forms.DataGridView> Ereignisse (z. B. Ereignisse, die auftreten, wenn Benutzer hinzufügen oder Löschen von Zeilen oder Werte Wenn Zelle bearbeitet, analysiert, überprüft oder formatiert sind) im virtuellen Modus auch hilfreich sind. Sie können auch Ereignisse behandeln, mit denen Sie in der Regel nicht in einer gebundenen Datenquelle, z. B. Zelle QuickInfo-Text, Zelle und Fehlertext für die Zeile, Zelle und Zeile Verknüpfung im Menü und Höhe Zeilendaten gespeicherten Werte beibehalten.  
  
 Weitere Informationen zum Implementieren des virtuellen Modus zum Verwalten von Lese-/Schreibdaten mit einem Bereich auf Zeilenebene Commit finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus in der Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
 Ein Beispiel, mit einem auf Zellenebene Commit-Bereich des virtuellen Modus implementiert, finden Sie unter den <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Referenzthema-Eigenschaft.  
  
 Die folgenden Ereignisse treten nur bei der <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> -Eigenschaftensatz auf `true`.  
  
|event|Beschreibung|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|Vom Steuerelement verwendeten, um einen Zellenwert aus dem Datencache für die Anzeige abzurufen. Dieses Ereignis tritt nur für Zellen in ungebundenen Spalten.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|Vom Steuerelement verwendeten, Benutzereingaben für eine Zelle den Datencache zu übergeben. Dieses Ereignis tritt nur für Zellen in ungebundenen Spalten.<br /><br /> Rufen Sie die <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> Methode, wenn einen zwischengespeicherten Wert außerhalb des ändern eine <xref:System.Windows.Forms.DataGridView.CellValuePushed> -Ereignishandler, um sicherzustellen, dass der aktuelle Wert im Steuerelement angezeigt wird und alle Modi zur Größenänderung momentan anzuwenden.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|Vom Steuerelement verwendeten, um die Notwendigkeit für eine neue Zeile in Datencache anzugeben.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|Vom Steuerelement verwendeten, um zu bestimmen, ob eine Zeile nicht gespeicherte Änderungen verfügt.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|Vom Steuerelement verwendeten, um anzugeben, dass eine Zeile die zwischengespeicherten Werte zurückgesetzt werden soll.|  
  
 Die folgenden Ereignisse eignen sich im virtuellen Modus befindet, jedoch kann verwendet werden, unabhängig von der <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Einstellung der Eigenschaft.  
  
|Ereignisse|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|Vom Steuerelement verwendeten, um anzugeben, wenn Zeilen gelöscht oder hinzugefügt werden, und Sie den Datencache entsprechend aktualisieren.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|Verwendet das Steuerelement formatiert Zellenwerte für die Anzeige und zu analysieren und Überprüfen von Benutzereingaben.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|Vom Steuerelement verwendet wird, um die Zelle QuickInfo-Text abrufen bei der <xref:System.Windows.Forms.DataGridView.DataSource%2A> festgelegt wird oder die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft `true`.<br /><br /> Zellen-QuickInfos angezeigt werden nur dann, wenn die <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> Eigenschaftswert ist `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|Zum Abrufen der Zelle oder Zeile Fehlertext vom Steuerelement verwendeten bei der <xref:System.Windows.Forms.DataGridView.DataSource%2A> festgelegt wird oder die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> -Eigenschaft ist `true`.<br /><br /> Rufen Sie die <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> Methode oder der <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> Methode, wenn Sie ändern den Fehlertext Zelle oder Zeile, um sicherzustellen, dass der aktuelle Wert im Steuerelement angezeigt wird.<br /><br /> Zellen- und Zeilenoperationen Fehlersymbole werden angezeigt. wenn die <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> und <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A> Eigenschaftswerte sind `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|Zum Abrufen einer Zelle oder Zeile vom Steuerelement verwendeten <xref:System.Windows.Forms.ContextMenuStrip> bei der das Steuerelement <xref:System.Windows.Forms.DataGridView.DataSource%2A> festgelegt wird oder die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> -Eigenschaft ist `true`.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|Vom Steuerelement verwendeten, zum Abrufen oder Speichern von Informationen über die Zeilenhöhe in Datencache. Rufen Sie die <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> Methode, wenn die zwischengespeicherten Informationen über die Zeilenhöhe außerhalb von ändern eine <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> -Ereignishandler, um sicherzustellen, dass der aktuelle Wert in der Anzeige des Steuerelements verwendet wird.|  
  
## <a name="best-practices-in-virtual-mode"></a>Bewährte Methoden im virtuellen Modus befindet  
 Wenn Sie für die Arbeit effizient mit großen Mengen von Daten des virtuellen Modus implementieren, Sie sollten auch sicherstellen, dass Sie effizient mit arbeiten die <xref:System.Windows.Forms.DataGridView> selbst zu steuern. Weitere Informationen zur effizienten Verwendung von Zellstile, Größenänderung, Auswahl und Freigeben von Zeilen finden Sie unter [Best Practices für das Skalieren des DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)
- [Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
