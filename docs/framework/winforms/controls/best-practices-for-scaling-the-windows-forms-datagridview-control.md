---
title: "Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ecd629bd38e08c8d6909ee4ad771f17b1554fc80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms
Die <xref:System.Windows.Forms.DataGridView> Steuerelement wurde entwickelt, um maximale Skalierbarkeit bereitzustellen. Wenn Sie große Mengen von Daten anzeigen möchten, sollten Sie die in diesem Thema, um große Mengen an Arbeitsspeicher fest, und beeinträchtigt die Reaktionsfähigkeit der Benutzeroberfläche (UI) beschriebenen Richtlinien folgen. In diesem Thema wird Folgendes erläutert:  
  
-   Effizientes Verwenden von Zellenstile  
  
-   Effizientes Verwenden von Kontextmenüs  
  
-   Automatische Größenänderung effizient verwenden  
  
-   Effizientes Verwenden von den ausgewählten Zellen, Zeilen und Spalten Sammlungen  
  
-   Verwenden freigegebene Zeilen  
  
-   Verhindert, dass Zeilen aufgehoben  
  
 Wenn Sie spezielle leistungsanforderungen haben, können Implementieren des virtuellen Modus und eigene Datenverwaltungsvorgänge bereitzustellen. Weitere Informationen finden Sie unter [Datenanzeigemodi im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-cell-styles-efficiently"></a>Effizientes Verwenden von Zellenstile  
 Jede Zelle, Zeile und Spalte kann einen eigenen Formatinformationen haben. Formatinformationen befindet sich in <xref:System.Windows.Forms.DataGridViewCellStyle> Objekte. Erstellen Zelle Formatobjekte für viele einzelne <xref:System.Windows.Forms.DataGridView> Elemente können ineffizient sein, insbesondere bei der Arbeit mit großen Mengen von Daten. Um Leistungseinbußen zu vermeiden, verwenden Sie die folgenden Richtlinien:  
  
-   Vermeiden Sie das Festlegen von Eigenschaften für den Zellstil für einzelne <xref:System.Windows.Forms.DataGridViewCell> oder <xref:System.Windows.Forms.DataGridViewRow> Objekte. Dies schließt das Zeilenobjekt gemäß der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> Eigenschaft. Jede neue Zeile, die von der Zeilenvorlage geklont wurde, erhält eine eigene Kopie der Vorlage Zelle Formatvorlagenobjekt. Für maximale Skalierbarkeit, legen Sie Eigenschaften für den Zellstil an die <xref:System.Windows.Forms.DataGridView> Ebene. Legen Sie z. B. die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> Eigenschaft anstelle der <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> Eigenschaft.  
  
-   Wenn einige Zellen Formatieren von anderen benötigen als den Standardwert zu formatieren, verwenden Sie den gleichen <xref:System.Windows.Forms.DataGridViewCellStyle> Instanz auf Gruppen von Zellen, Zeilen oder Spalten. Vermeiden Sie direkt festlegen von Eigenschaften des Typs <xref:System.Windows.Forms.DataGridViewCellStyle> auf einzelne Zellen, Zeilen und Spalten. Beispielsweise eine Freigabe von Zellenstilen finden Sie unter [Vorgehensweise: Festlegen von standardmäßigen Zellenstilen für DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). Sie können auch eine Leistungseinbuße umgehen, der zum Einstellen Zellenstile einzeln durch Behandeln der <xref:System.Windows.Forms.DataGridView.CellFormatting> -Ereignishandler. Ein Beispiel finden Sie unter [wie: Anpassen der Datenformatierung im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
-   Wenn eine Zellenstils verwenden die <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType> Eigenschaft statt über das <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> Eigenschaft. Zugreifen auf die <xref:System.Windows.Forms.DataGridViewCell.Style%2A> Eigenschaft erstellt eine neue Instanz der dem <xref:System.Windows.Forms.DataGridViewCellStyle> Klasse, wenn die Eigenschaft noch nicht verwendet wurde. Darüber hinaus kann dieses Objekt nicht enthalten, die vollständige Stilinformationen für die Zelle Wenn Formate von der Zeilen-, Spalten- oder Steuerelement geerbt werden. Weitere Informationen zur Vererbung von Zellenstilen finden Sie unter [Zellstile im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-shortcut-menus-efficiently"></a>Effizientes Verwenden von Kontextmenüs  
 Jede Zelle, Zeile und Spalte kann ein eigenen Kontextmenü verfügen. Kontextmenüs in der <xref:System.Windows.Forms.DataGridView> Steuerelements dargestellte <xref:System.Windows.Forms.ContextMenuStrip> Steuerelemente. Wie bei Zelle Formatobjekte, Erstellen von Kontextmenüs für viele einzelne <xref:System.Windows.Forms.DataGridView> Elemente werden die Leistung negativ beeinträchtigt. Um dieser Nachteil zu vermeiden, verwenden Sie die folgenden Richtlinien:  
  
-   Vermeiden Sie das Erstellen von Kontextmenüs für einzelne Zellen, Zeilen. Dies schließt die Zeilenvorlage, die zusammen mit dem Kontextmenü geklont wird, wenn das Steuerelement neue Zeilen hinzugefügt werden. Verwenden Sie nur des Steuerelements für maximale Skalierbarkeit <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> Eigenschaft, um ein einzelnes Kontextmenü für das gesamte Steuerelement anzugeben.  
  
-   Wenn Sie mehrere Kontextmenüs für mehrere Zeilen oder Zellen benötigen, behandeln die <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> oder <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded> Ereignisse. Diese Ereignisse können Sie die Verknüpfung im Menü-Objekte zu verwalten, selbst ermöglicht Ihnen, die Leistung zu optimieren.  
  
## <a name="using-automatic-resizing-efficiently"></a>Automatische Größenänderung effizient verwenden  
 Zeilen, Spalten und Header können automatisch als Änderungen am Inhalt der Zelle einnimmt, damit der gesamte Inhalt von Zellen angezeigt werden, ohne ihn abzuschneiden. Ändern von Größenanpassungsmodi kann auch Zeilen, Spalten und Header ändern. Um die richtige Größe zu bestimmen, die <xref:System.Windows.Forms.DataGridView> Steuerelement muss untersuchen Sie den Wert jeder Zelle, die angepasst werden müssen. Bei der Arbeit mit großen Datasets kann auf Basis dieser Analyse beeinträchtigen die Leistung des Steuerelements automatische Größenänderung tritt. Um Leistungseinbußen zu vermeiden, verwenden Sie die folgenden Richtlinien:  
  
-   Vermeiden Sie die Verwendung der automatischen Größenänderung auf eine <xref:System.Windows.Forms.DataGridView> Steuerelement mit einer großen Gruppe von Zeilen. Wenn Sie automatische größenanpassung, nur die Größe, die basierend auf der angezeigten Zeilen verwenden. Verwenden Sie nur die Zeilen angezeigten, in als auch der virtuelle Modus.  
  
    -   Verwenden Sie für Zeilen und Spalten, die `DisplayedCells` oder `DisplayedCellsExceptHeaders` Feld der <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>, und <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> Enumerationen.  
  
    -   Verwenden Sie für die Zeilenkopfzeilen, die <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> oder <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> Feld der <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> Enumeration.  
  
-   Deaktivieren Sie für maximale Skalierbarkeit automatische größenanpassung und verwenden Sie programmgesteuerten größenanpassung.  
  
 Weitere Informationen finden Sie unter [Größenänderungsoptionen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>Effizientes Verwenden von der ausgewählten Zellen, Zeilen und Spalten Sammlungen  
 Die <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> Auflistung führt keine effizient mit großen Auswahl. Die <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> und <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> Sammlungen können auch ineffizient sein, auch in geringerem Maße kommen viele weniger Zeilen als Zellen in einem typischen <xref:System.Windows.Forms.DataGridView> -Steuerelement, und viele weniger Spalten als Zeilen. Um Leistungseinbußen zu vermeiden, bei der Arbeit mit diesen Auflistungen, verwenden Sie die folgenden Richtlinien:  
  
-   Um zu bestimmen, ob alle Zellen in der <xref:System.Windows.Forms.DataGridView> ausgewählt wurden, bevor Sie den Inhalt der Zugriff auf die <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> -Auflistung, überprüfen den Rückgabewert von der <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> Methode. Beachten Sie jedoch, dass diese Methode Zeilen aufgehoben verursachen kann. Weitere Informationen finden Sie im nächsten Abschnitt.  
  
-   Vermeiden Sie die Verwendung der <xref:System.Collections.ICollection.Count%2A> Eigenschaft von der <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType> bestimmt die Anzahl der ausgewählten Zellen. Verwenden Sie stattdessen die <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> Methode und übergeben der <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType> Wert. Auf ähnliche Weise mithilfe der <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> und <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType> Methoden zur Bestimmung der Anzahl der ausgewählten Elemente, anstatt den Zugriff auf den ausgewählten Sammlungen von Zeile und Spalte.  
  
-   Vermeiden Sie zellenbasierte Auswahlmodi. Legen Sie stattdessen die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.  
  
## <a name="using-shared-rows"></a>Verwenden von freigegebenen Zeilen  
 Effiziente speichernutzung erfolgt der <xref:System.Windows.Forms.DataGridView> Kontrolle über freigegebene Zeilen. Zeilen werden so viele Informationen zu ihrer Darstellung und Verhalten wie möglich freigeben, indem Sie Instanzen der Freigabe der <xref:System.Windows.Forms.DataGridViewRow> Klasse.  
  
 Freigabe Zeileninstanz Arbeitsspeicher speichert, können die Zeilen einfach aufgehoben werden. Wenn ein Benutzer direkt mit einer Zelle interagiert, wird die Zeile aufgehoben. Da dies vermieden werden kann, eignen sich die Richtlinien in diesem Thema nur bei der Arbeit mit sehr großen Mengen von Daten und nur, wenn Benutzer mit einer relativ kleinen Teil der Daten jedes Mal interagieren werden, wenn das Programm ausgeführt wird.  
  
 Eine Zeile kann nicht freigegeben werden in einer nicht gebundenen <xref:System.Windows.Forms.DataGridView> steuern, wenn eine ihrer Zellen Werte enthält. Wenn die <xref:System.Windows.Forms.DataGridView> Steuerelement an einer externen Datenquelle gebunden ist, oder wenn Sie virtuellen Modus implementieren und eine eigene Datenquelle bereitstellen, werden die Zellenwerte gespeichert, außerhalb der Kontrolle und nicht in Zelle Objekte, wodurch die Zeilen gemeinsam genutzt werden.  
  
 Ein Zeilenobjekt kann nur freigegeben werden, wenn der Status ihrer Zellen aus dem Zustand der Zeile und den Status der Spalten mit den Zellen bestimmt werden kann. Wenn Sie den Zustand einer Zelle ändern, sodass es nicht mehr aus dem Zustand ihrer Zeile und Spalte abgeleitet werden kann, kann die Zeile nicht freigegeben werden.  
  
 Beispielsweise kann keine Zeile in den folgenden Situationen freigegeben werden:  
  
-   Die Zeile enthält eine einzelne ausgewählte Zelle, die nicht in einer ausgewählten Spalte ist.  
  
-   Die Zeile enthält eine Zelle mit seiner <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> oder <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> festgelegten Eigenschaften.  
  
-   Die Zeile enthält eine <xref:System.Windows.Forms.DataGridViewComboBoxCell> mit seiner <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> Eigenschaftensatz.  
  
 Im gebundenen oder virtuellen Modus können Sie QuickInfos und Kontextmenüs für einzelne Zellen angeben, durch Behandeln der <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> und <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> Ereignisse.  
  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement versucht automatisch, freigegebene Zeilen zu verwenden, wenn Zeilen hinzugefügt werden die <xref:System.Windows.Forms.DataGridViewRowCollection>. Verwenden Sie die folgenden Richtlinien, um sicherzustellen, dass Zeilen gemeinsam genutzt werden:  
  
-   Vermeiden Sie Aufrufe der `Add(Object[])` Überladung von der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> Methode und die `Insert(Object[])` Überladung der der <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> Methode der <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> Auflistung. Diese Überladungen werden automatisch nicht freigegebene Zeilen erstellen.  
  
-   Stellen Sie sicher, dass der Zeile angegeben wird, der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> Eigenschaft in den folgenden Fällen gemeinsam genutzt werden kann:  
  
    -   Beim Aufrufen der `Add()` oder `Add(Int32)` Überladungen der der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> Methode oder die `Insert(Int32,Int32)` Überladung von der <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> Methode der <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> Auflistung.  
  
    -   Erhöhen Sie den Wert von der <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType> Eigenschaft.  
  
    -   Beim Festlegen der <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType> Eigenschaft.  
  
-   Stellen Sie sicher, dass die Zeile, angegeben durch die `indexSource` Parameter kann freigegeben werden, beim Aufrufen der <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A>, und <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> Methoden der <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> Auflistung.  
  
-   Achten Sie darauf, dass beim Aufrufen der angegebenen Zeile bzw. Zeilen freigegeben werden können die `Add(DataGridViewRow)` Überladung der der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> -Methode, die <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A> -Methode, die `Insert(Int32,DataGridViewRow)` Überladung der der <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> -Methode, und die <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> Methode von der <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>Auflistung.  
  
 Um zu bestimmen, ob eine Zeile freigegeben ist, verwenden die <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> Methode, um das Zeilenobjekt abgerufen, und überprüfen Sie des Objekts <xref:System.Windows.Forms.DataGridViewBand.Index%2A> Eigenschaft. Freigegebene Zeilen verfügen immer über ein <xref:System.Windows.Forms.DataGridViewBand.Index%2A> Eigenschaftswert von – 1.  
  
## <a name="preventing-rows-from-becoming-unshared"></a>Verhindert, dass Zeilen aufgehoben  
 Freigegebene Zeilen können als Ergebnis der Aktion "Code" oder "Benutzer aufgehoben werden. Um Leistungseinbußen zu vermeiden, sollten Sie vermeiden, sodass Zeilen aufgehoben wird. Sie können während der Anwendungsentwicklung behandeln die <xref:System.Windows.Forms.DataGridView.RowUnshared> Ereignis, um zu bestimmen, wann Zeilen aufgehoben wird. Dies ist hilfreich beim Debuggen von Problemen Freigeben von Zeilen.  
  
 Um zu verhindern, dass Zeilen aufgehoben, verwenden Sie die folgenden Richtlinien:  
  
-   Vermeiden Sie die Indizierung der <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung oder durchlaufen, bis sie mit einer `foreach` Schleife. Normalerweise müssen Sie nicht direkt auf Zeilen zugreifen. <xref:System.Windows.Forms.DataGridView>Methoden, die für Zeilen ausgeführt werden, nehmen Zeileninstanz, anstatt Argumente für den Zeilenindex. Darüber hinaus Empfangshandler für Ereignisse in Zusammenhang mit Zeile Argument Ereignisobjekten mit Eigenschaften für die Zeile, die Sie verwenden können, um Zeilen zu bearbeiten, ohne dass aufgehoben wird.  
  
-   Wenn Sie ein Zeilenobjekt zugreifen müssen, verwenden die <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> -Methode und übergeben Sie den tatsächlichen Zeilenindex. Beachten Sie jedoch, dass das Ändern von freigegebenen Zeilenobjekts abgerufen, die durch diese Methode alle Zeilen geändert werden, die dieses Objekt aufweisen. Die Zeile für neue Datensätze ist nicht mit anderen Zeilen hat jedoch freigegeben, sodass es nicht betroffen sind, wenn Sie eine anderen Zeile ändern. Beachten Sie außerdem, dass unterschiedliche Zeilen, die durch eine freigegebene Zeile dargestellten verschiedene Kontextmenüs aufweisen können. Um das richtige Kontextmenü aus einer Instanz freigegebenen Zeile abzurufen, verwenden die <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> -Methode und übergeben Sie den tatsächlichen Zeilenindex. Wenn der Zugriff auf die freigegebenen Zeile <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> Eigenschaft stattdessen die freigegebene Zeilenindex "-1" wird verwendet und wird nicht das richtige Kontextmenü abrufen.  
  
-   Vermeiden Sie die Indizierung der <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType> Auflistung. Direkten Zugriff auf eine Zelle führt dazu, dass die übergeordneten Zeile aufgehoben und Instanziierung eines neuen <xref:System.Windows.Forms.DataGridViewRow>. Empfangshandler für Ereignisse in Zusammenhang mit Zelle Argument Ereignisobjekten mit Zelleigenschaften, die Sie verwenden können, um Zellen zu bearbeiten, ohne Zeilen aufgehoben wird. Sie können auch die <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> Eigenschaft, um die Zeilen- und Spaltenindizes der aktuellen Zelle abrufen, ohne den direkten Zugriff auf die Zelle.  
  
-   Vermeiden Sie zellenbasierte Auswahlmodi. Diese Modi dazu führen, dass Zeilen aufgehoben wird. Legen Sie stattdessen die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.  
  
-   Behandeln Sie keine der <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType> oder <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType> Ereignisse. Diese Ereignisse dazu führen, dass Zeilen aufgehoben wird. Rufen Sie außerdem nicht den <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> oder <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType> Methoden, die diese Ereignisse auslösen.  
  
-   Nicht auf die <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType> Auflistung bei der <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> Eigenschaftswert ist <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>, oder <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>. Dies bewirkt, dass alle ausgewählten Zeilen aufgehoben wird.  
  
-   Rufen Sie nicht die <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType> Methode. Diese Methode kann dazu führen, dass Zeilen aufgehoben wird.  
  
-   Rufen Sie nicht die <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType> Methode bei der <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> Eigenschaftswert ist <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>. Dies bewirkt, dass alle Zeilen aufgehoben wird.  
  
-   Legen Sie nicht die <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> oder <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> Eigenschaft einer Zelle, `false` Wenn die entsprechende Eigenschaft in der Spalte auf festgelegt ist `true`. Dies bewirkt, dass alle Zeilen aufgehoben wird.  
  
-   Nicht auf die <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType> Eigenschaft. Dies bewirkt, dass alle Zeilen aufgehoben wird.  
  
-   Rufen Sie nicht die `Sort(IComparer)` Überladung von der <xref:System.Windows.Forms.DataGridView.Sort%2A> Methode. Sortieren mit einem benutzerdefinierten Vergleich bewirkt, dass alle Zeilen aufgehoben wird.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Virtueller Modus im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 [Zellstile im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Gewusst wie: Festlegen von Standardzellenformaten für das DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 [Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)
