---
title: "Virtueller Modus im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DataGridView-Steuerelement [Windows Forms], Virtueller Modus"
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Virtueller Modus im DataGridView-Steuerelement in Windows Forms
Mit dem virtuellen Modus können Sie die Interaktion zwischen dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement und einem benutzerdefinierten Datencache verwalten.  Um den virtuellen Modus zu implementieren, legen Sie die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>\-Eigenschaft auf `true` fest, und behandeln Sie eines oder mehrere der Ereignisse, die weiter unten in diesem Thema beschrieben werden.  Für gewöhnlich behandeln Sie zumindest das `CellValueNeeded`\-Ereignis, das es dem Steuerelement ermöglicht, Werte im Datencache zu suchen.  
  
## Gebundener Modus und virtueller Modus  
 Der virtuelle Modus ist nur erforderlich, wenn Sie den gebundenen Modus ergänzen oder ersetzen müssen.  Im gebundenen Modus legen Sie die <xref:System.Windows.Forms.DataGridView.DataSource%2A>\-Eigenschaft fest, sodass das Steuerelement die Daten automatisch aus der angegebenen Quelle lädt und Änderungen des Benutzers an diese zurücksendet.  Sie können steuern, welche der gebundenen Spalten angezeigt werden. Die Datenquelle selbst behandelt für gewöhnlich Operationen, z. B. Sortiervorgänge.  
  
## Ergänzen des gebundenen Modus  
 Sie können den gebundenen Modus ergänzen, indem Sie ungebundene Spalten zusammen mit den gebundenen Spalten anzeigen.  Dies wird manchmal als "gemischter Modus" bezeichnet und eignet sich beispielsweise zum Anzeigen von berechneten Werten oder UI\-Steuerelementen.  
  
 Da ungebundene Spalten sich außerhalb der Datenquelle befinden, werden sie von den Sortiervorgängen der Datenquelle ignoriert.  Wenn Sie das Sortieren im gemischten Modus aktivieren, müssen Sie daher die ungebundenen Daten in einem lokalen Cache verwalten und den virtuellen Modus implementieren, damit das <xref:System.Windows.Forms.DataGridView>\-Steuerelement damit interagiert.  
  
 Weitere Informationen über die Verwendung des virtuellen Modus zur Erhaltung der Werte in ungebundenen Spalten finden Sie in den Beispielen in der <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=fullName>\-Eigenschaft und den Referenzthemen zur <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=fullName>\-Klasse.  
  
## Ersetzen des gebundenen Modus  
 Wenn der gebundene Modus Ihre Leistungsanforderungen nicht erfüllt, können Sie sämtliche Daten in einem benutzerdefinierten Cache mithilfe von Ereignishandlern des virtuellen Modus verwalten.  Beispielsweise können Sie den virtuellen Modus verwenden, um das Just\-In\-Time\-Laden von Daten zu implementieren, wodurch nur so viele Daten aus einer Netzwerkdatenbank abgerufen werden, wie zur Erhaltung der optimalen Leistung möglich sind.  Dieses Szenario eignet sich insbesondere bei der Arbeit mit großen Datenmengen, die über eine langsame Netzwerkverbindung übertragen werden, oder mit Clientrechnern, die über eine begrenzte Menge an Arbeitsspeicher oder Speicherplatz verfügen.  
  
 Weitere Informationen über die Verwendung des virtuellen Modus in einem Just\-In\-Time\-Szenario finden Sie unter [Implementieren des virtuellen Modus mit Just\-In\-Time\-Laden von Daten in das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## Ereignisse im virtuellen Modus  
 Wenn Sie nur lesend auf die Daten zugreifen, müssen Sie unter Umständen nur das `CellValueNeeded`\-Ereignis behandeln.  Andere Ereignisse im virtuellen Modus ermöglichen es Ihnen, bestimmte Funktionen zu aktivieren, z. B. Bearbeitungen durch den Benutzer, das Hinzufügen und Löschen von Zeilen und Transaktionen auf Zeilenebene.  
  
 Einige standardmäßige <xref:System.Windows.Forms.DataGridView>\-Ereignisse \(z. B. Ereignisse, die auftreten, wenn Benutzer Zeilen hinzufügen oder löschen oder wenn Zellenwerte bearbeitet, analysiert, überprüft oder formatiert werden\) sind im virtuellen Modus ebenfalls hilfreich.  Sie können auch Ereignisse behandeln, mit denen Sie Werte erhalten können, die normalerweise nicht in einer gebundenen Datenquelle gespeichert sind, z. B. QuickInfo\-Zellentext, Zellen\- und Zeilenfehlertext, Zellen\- und Zeilenkontextmenüdaten und Zeilenhöhendaten.  
  
 Weitere Informationen über das Implementieren des virtuellen Modus zur Verwaltung von Lese\-\/Schreibdaten mit einem Commit\-Bereich auf Zeilenebene finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
 Ein Beispiel zur Implementierung des virtuellen Modus mit einem Commit\-Bereich auf Zellenebene finden Sie im Referenzthema zur <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>\-Eigenschaft.  
  
 Die folgenden Ereignisse treten nur auf, wenn die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>\-Eigenschaft auf `true` festgelegt ist.  
  
|Ereignis|Beschreibung|  
|--------------|------------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|Wird vom Steuerelement verwendet, um einen Zellenwert zur Anzeige aus dem Datencache abzurufen.  Dieses Ereignis tritt nur für Zellen in ungebundenen Spalten auf.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|Wird vom Steuerelement verwendet, um Benutzereingaben für eine Zelle an den Datencache zu übergeben.  Dieses Ereignis tritt nur für Zellen in ungebundenen Spalten auf.<br /><br /> Rufen Sie die <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A>\-Methode auf, wenn Sie einen zwischengespeicherten Wert außerhalb eines <xref:System.Windows.Forms.DataGridView.CellValuePushed>\-Ereignishandlers ändern, um sicherzustellen, dass der aktuelle Wert im Steuerelement angezeigt wird und einen automatischen Größenanpassungsmodus anzuwenden.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|Wird vom Steuerelement verwendet, um darauf hinzuweisen, dass im Datencache eine neue Zeile benötigt wird.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|Wird vom Steuerelement verwendet, um zu bestimmen, ob eine Zeile über nicht gespeicherte Änderungen verfügt.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|Wird vom Steuerelement verwendet, um anzugeben, dass die zwischengespeicherten Werte einer Zeile wiederhergestellt werden sollten.|  
  
 Die folgenden Ereignisse sind im virtuellen Modus hilfreich, können aber unabhängig von der Einstellung der <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>\-Eigenschaft verwendet werden.  
  
|Ereignisse|Beschreibung|  
|----------------|------------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|Wird vom Steuerelement verwendet, um anzugeben, wann Zeilen gelöscht oder hinzugefügt werden, und um den Datencache entsprechend zu aktualisieren.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|Wird vom Steuerelement verwendet, um Zellenwerte für die Anzeige zu formatieren und Benutzereingaben zu analysieren und zu überprüfen.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|Wird vom Steuerelement verwendet, um QuickInfo\-Zellentext abzurufen, wenn die <xref:System.Windows.Forms.DataGridView.DataSource%2A>\-Eigenschaft festgelegt ist oder die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>\-Eigenschaft `true` lautet.<br /><br /> Zellen\-QuickInfos werden nur angezeigt, wenn der <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A>\-Eigenschaftswert `true` lautet.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|Wird vom Steuerelement verwendet, um Zellen\- oder Zeilenfehlertext abzurufen, wenn die <xref:System.Windows.Forms.DataGridView.DataSource%2A>\-Eigenschaft festgelegt ist oder die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>\-Eigenschaft `true` lautet.<br /><br /> Rufen Sie die <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A>\-Methode oder die <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A>\-Methode auf, wenn Sie den Zellen\- oder Zeilenfehlertext ändern, um sicherzustellen, dass der aktuelle Wert im Steuerelement angezeigt wird.<br /><br /> Zellen\- und Zeilenfehlersymbole werden angezeigt, wenn der <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A>\-Eigenschaftswert und der <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A>\-Eigenschaftswert `true` lauten.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|Wird vom Steuerelement verwendet, um ein <xref:System.Windows.Forms.ContextMenuStrip> für eine Zelle oder Zeile abzurufen, wenn die <xref:System.Windows.Forms.DataGridView.DataSource%2A>\-Eigenschaft des Steuerelements festgelegt ist oder die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>\-Eigenschaft `true` lautet.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|Wird vom Steuerelement verwendet, um Zeilenhöheninformationen im Datencache abzurufen oder zu speichern.  Rufen Sie die <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A>\-Methode auf, wenn Sie die zwischengespeicherten Zeilenhöheninformationen außerhalb eines <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>\-Ereignishandlers ändern, um sicherzustellen, dass der aktuelle Wert im Steuerelement angezeigt wird.|  
  
## Empfohlene Vorgehensweisen im virtuellen Modus  
 Wenn Sie den virtuellen Modus implementieren, um effektiv mit großen Datenmengen zu arbeiten, sollten Sie außerdem sicherstellen, dass Sie auch mit dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement effektiv arbeiten.  Weitere Informationen über die effektive Verwendung von Zellenstilen, automatischer Größenanpassung, Auswahlmöglichkeiten und Zeilenfreigabe finden Sie unter [Empfohlene Vorgehensweisen für das Skalieren des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>   
 [Leistungsoptimierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Empfohlene Vorgehensweisen für das Skalieren des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)   
 [Implementieren des virtuellen Modus mit Just\-In\-Time\-Laden von Daten in das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)