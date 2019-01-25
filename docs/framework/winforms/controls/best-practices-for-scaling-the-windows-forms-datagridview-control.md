---
title: Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
ms.openlocfilehash: 5adbcdb4aa34b3878e278d47337defe4388dd892
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710871"
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms
Die <xref:System.Windows.Forms.DataGridView> Steuerelement wurde entwickelt, um maximale Skalierbarkeit bereitzustellen. Wenn Sie große Datenmengen anzeigen müssen, sollten Sie die in diesem Thema, um zu vermeiden, verwenden große Mengen an Arbeitsspeicher, oder beschränken die Reaktionsfähigkeit der Benutzeroberfläche (UI) beschriebenen Richtlinien befolgen. In diesem Thema wird Folgendes erläutert:  
  
-   Effiziente Verwendung des Zellstile  
  
-   Effiziente Verwendung des Kontextmenüs  
  
-   Verwenden die automatische Größenänderung effizient  
  
-   Effizientes Verwenden von den ausgewählten Zellen, Zeilen und Spalten Sammlungen  
  
-   Verwenden freigegebene Zeilen  
  
-   Verhindert, dass Zeilen aufgehoben  
  
 Wenn Sie besondere leistungsanforderungen haben, können Sie virtuellen Modus implementieren, und stellen eigene Datenverwaltungsvorgänge. Weitere Informationen finden Sie unter [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-cell-styles-efficiently"></a>Effiziente Verwendung des Zellstile  
 Jede Zelle, Zeile und Spalte haben eine eigene Formatinformationen. Informationen zum Schriftschnitt befindet sich in <xref:System.Windows.Forms.DataGridViewCellStyle> Objekte. Erstellen Zelle stilobjekte für viele einzelne <xref:System.Windows.Forms.DataGridView> Elemente können ineffizient sein, insbesondere bei der Arbeit mit großen Datenmengen. Um Auswirkungen auf die Leistung zu vermeiden, verwenden Sie die folgenden Richtlinien:  
  
-   Vermeiden Sie das Festlegen von Eigenschaften für den Zellstil für einzelne <xref:System.Windows.Forms.DataGridViewCell> oder <xref:System.Windows.Forms.DataGridViewRow> Objekte. Dies schließt das Zeilenobjekt gemäß der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> Eigenschaft. Jede neue Zeile, die die Zeilenvorlage geklont wurde, erhält eine eigene Kopie der Vorlage Cell-Style-Objekt. Legen Sie für maximale Skalierbarkeit gibt die Eigenschaften für den Zellstil an die <xref:System.Windows.Forms.DataGridView> Ebene. Legen Sie z. B. die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> Eigenschaft anstelle der <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> Eigenschaft.  
  
-   Wenn einige Zellen erforderlich ist, außer der standardformatierung formatieren, verwenden Sie den gleichen <xref:System.Windows.Forms.DataGridViewCellStyle> Instanz für Gruppen von Zellen, Zeilen oder Spalten. Vermeiden des direktes Festlegen von Eigenschaften des Typs <xref:System.Windows.Forms.DataGridViewCellStyle> auf einzelne Zellen, Zeilen und Spalten. Ein Beispiel für die Zelle Stil freigeben, finden Sie unter [Vorgehensweise: Festlegen von Standardzellenformaten für das Windows-DataGridView-Steuerelement Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). Sie können außerdem Leistungseinbußen vermeiden, wenn Zellstile einzeln verarbeiten Festlegen der <xref:System.Windows.Forms.DataGridView.CellFormatting> -Ereignishandler. Ein Beispiel finden Sie unter [Gewusst wie: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
-   Wenn eine Zellenstils, verwenden Sie die <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType> Eigenschaft anstelle der <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> Eigenschaft. Zugriff auf die <xref:System.Windows.Forms.DataGridViewCell.Style%2A> Eigenschaft erstellt eine neue Instanz der dem <xref:System.Windows.Forms.DataGridViewCellStyle> Klasse, wenn die Eigenschaft noch nicht verwendet wurde. Darüber hinaus kann dieses Objekt nicht enthalten die vollständige Stilinformationen für die Zelle, wenn einige Stile, die von den Zeilen-, Spalten- oder Steuerelement geerbt werden. Weitere Informationen zur Vererbung von Zellenstilen finden Sie unter [Zellstile im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-shortcut-menus-efficiently"></a>Effiziente Verwendung des Kontextmenüs  
 Jede Zelle, Zeile und Spalte haben eine eigene im Kontextmenü. Kontextmenüs in der <xref:System.Windows.Forms.DataGridView> Steuerelement durch dargestellt <xref:System.Windows.Forms.ContextMenuStrip> Steuerelemente. Genau wie bei Stil Cell-Objekte, Erstellen von Kontextmenüs für viele einzelne <xref:System.Windows.Forms.DataGridView> Elemente wirkt sich negativ auf die Leistung. Um diese Leistungsminderung zu vermeiden, verwenden Sie die folgenden Richtlinien:  
  
-   Vermeiden Sie das Erstellen von Kontextmenüs für einzelne Zellen und Zeilen. Dies schließt die Zeilenvorlage, die zusammen mit Kontextmenü geklont wird, wenn das Steuerelement neue Zeilen hinzugefügt werden. Verwenden Sie für maximale Skalierbarkeit gibt nur des Steuerelements <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> Eigenschaft, um ein einzelnes Kontextmenü für das gesamte Steuerelement anzugeben.  
  
-   Wenn Sie mehrere Kontextmenüs für mehrere Zeilen oder Zellen benötigen, behandeln die <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> oder <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded> Ereignisse. Diese Ereignisse können Sie die Verknüpfung im Menü-Objekte zu verwalten, selbst können Sie zum Optimieren der Leistung.  
  
## <a name="using-automatic-resizing-efficiently"></a>Verwenden die automatische Größenänderung effizient  
 Zeilen, Spalten und Header können automatisch als Änderungen am Inhalt der Zelle geändert, damit der gesamte Inhalt der Zellen angezeigt werden, ohne ihn abzuschneiden. Ändern von Größenanpassungsmodi Größe kann auch Zeilen, Spalten und Header. Zum Bestimmen der richtigen Größe, die <xref:System.Windows.Forms.DataGridView> Steuerelement muss überprüfen Sie den Wert jeder Zelle, die sie berücksichtigen muss. Bei der Arbeit mit großen Datasets kann diese Analyse beeinträchtigen die Leistung des Steuerelements bei der automatischen Größenänderung erfolgt. Um Leistungseinbußen zu vermeiden, verwenden Sie die folgenden Richtlinien:  
  
-   Verwenden Sie keine automatische größenanpassung auf eine <xref:System.Windows.Forms.DataGridView> Steuerelement mit einem großen Satz von Zeilen. Wenn Sie automatische größenanpassungen, nur die Größe basierend auf der angezeigten Zeilen verwenden. Verwenden Sie nur die angezeigten Zeilen im virtuellen Modus auch ein.  
  
    -   Verwenden Sie für Zeilen und Spalten der `DisplayedCells` oder `DisplayedCellsExceptHeaders` Feld der <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>, und <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> Enumerationen.  
  
    -   Verwenden Sie für den Zeilenköpfen der <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> oder <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> Feld der <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> Enumeration.  
  
-   Deaktivieren Sie für maximale Skalierbarkeit automatische größenanpassungen und programmgesteuerten größenanpassung.  
  
 Weitere Informationen finden Sie unter [Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>Effiziente Verwendung von der ausgewählten Zellen, Zeilen und Spalten Sammlungen  
 Die <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> Sammlung führt keine effizient mit einer großen Auswahl. Die <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> und <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> Sammlungen können auch sein, ineffizient, jedoch in geringerem Maße, da es viele weniger Zeilen als Zellen in einer typischen gibt <xref:System.Windows.Forms.DataGridView> -Steuerelement, und viele weniger Spalten als Zeilen. Um Leistungseinbußen zu vermeiden, bei der Arbeit mit diesen Auflistungen, verwenden Sie die folgenden Richtlinien:  
  
-   Um zu bestimmen, ob alle Zellen in der <xref:System.Windows.Forms.DataGridView> ausgewählt wurden, bevor Sie den Zugriff der <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> -Auflistung, überprüfen den Rückgabewert des der <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> Methode. Beachten Sie jedoch, dass diese Methode Zeilen aufgehoben verursachen kann. Weitere Informationen finden Sie im nächsten Abschnitt.  
  
-   Vermeiden Sie die Verwendung der <xref:System.Collections.ICollection.Count%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType> um zu bestimmen, die Anzahl der ausgewählten Zellen. Verwenden Sie stattdessen die <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> -Methode und übergeben Sie die <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType> Wert. Auf ähnliche Weise verwenden die <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> und <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType> Methoden, um die Anzahl der ausgewählten Elemente, anstatt den Zugriff auf den ausgewählten Sammlungen von Zeilen und Spalten zu bestimmen.  
  
-   Vermeiden Sie zellenbasierte Auswahlmodi. Legen Sie stattdessen die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.  
  
## <a name="using-shared-rows"></a>Mithilfe von SAS-Zeilen  
 Effiziente Speicherverwendung erfolgt der <xref:System.Windows.Forms.DataGridView> Steuerelement über freigegebene Zeilen. Zeilen werden so viele Informationen über deren Darstellung und Verhalten wie möglich freigeben, indem Sie die Freigabe von Instanzen von der <xref:System.Windows.Forms.DataGridViewRow> Klasse.  
  
 Während der Freigabe Zeileninstanz Arbeitsspeicher speichert, können Zeilen einfach aufgehoben werden. Wenn ein Benutzer direkt mit einer Zelle interagiert, wird z. B. eine Zeile aufgehoben wird. Da dies nicht vermieden werden kann, eignen sich die Richtlinien in diesem Thema nur bei der Arbeit mit sehr großen Mengen von Daten und nur, wenn Benutzer mit einem relativ kleinen Teil der Daten jedes Mal interagieren, die Ihr Programm ausgeführt wird.  
  
 Eine Zeile kann nicht freigegeben werden in einer nicht gebundenen <xref:System.Windows.Forms.DataGridView> steuern, wenn eine der Zellen Werte enthalten. Wenn die <xref:System.Windows.Forms.DataGridView> -Steuerelement an eine externe Datenquelle gebunden ist oder wenn Sie virtuellen Modus implementieren, und geben Sie eine eigene Datenquelle, werden die Zellenwerte gespeichert, außerhalb des Steuerelements nicht im Cell-Objekte, die Zeilen, die gemeinsam genutzt werden können.  
  
 Ein Zeilenobjekt kann nur freigegeben werden, wenn der Status ihrer Zellen in den Zustand der Zeile und den Status der Spalten, die die Zellen bestimmt werden kann. Wenn Sie den Zustand einer Zelle ändern, sodass es nicht mehr vom Status der entsprechenden Zeile und Spalte abgeleitet werden kann, nicht die Zeile nicht freigegeben werden.  
  
 Beispielsweise kann keine Zeile in den folgenden Situationen freigegeben werden:  
  
-   Die Zeile enthält eine einzelne ausgewählte Zelle, die nicht in einer ausgewählten Spalte an.  
  
-   Die Zeile enthält eine Zelle mit der <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> oder <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> festgelegten Eigenschaften.  
  
-   Die Zeile enthält einen <xref:System.Windows.Forms.DataGridViewComboBoxCell> mit seiner <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> Eigenschaftensatz.  
  
 Im gebundenen Modus oder im virtuellen Modus befindet, können Sie QuickInfos und Kontextmenüs für einzelne Zellen angeben, durch Behandeln der <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> und <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> Ereignisse.  
  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement wird automatisch versuchen, auf die freigegebene Zeilen zu verwenden, wenn Zeilen hinzugefügt werden die <xref:System.Windows.Forms.DataGridViewRowCollection>. Verwenden Sie die folgenden Richtlinien, um sicherzustellen, dass Zeilen gemeinsam genutzt werden:  
  
-   Rufen Sie die `Add(Object[])` Überladung von der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> Methode und die `Insert(Object[])` Überladung der der <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> -Methode der der <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> Auflistung. Diese überladugn erstellt automatisch nicht freigegebene Zeilen.  
  
-   Stellen Sie sicher, dass der Zeile angegeben wird, der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> Eigenschaft freigegeben werden kann, in den folgenden Fällen:  
  
    -   Beim Aufrufen der `Add()` oder `Add(Int32)` Überladungen der der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> Methode oder der `Insert(Int32,Int32)` Überladung von der <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> -Methode der der <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> Auflistung.  
  
    -   Beim Erhöhen des Werts des der <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType> Eigenschaft.  
  
    -   Beim Festlegen der <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType> Eigenschaft.  
  
-   Stellen Sie sicher, dass die Zeile, angegeben durch die `indexSource` Parameter kann gemeinsam genutzt werden, beim Aufrufen der <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A>, und <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> Methoden der <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> Auflistung.  
  
-   Achten Sie darauf, dass beim Aufrufen der angegebenen Zeile oder Zeilen freigegeben werden können die `Add(DataGridViewRow)` Überladung der der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> -Methode, die <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A> -Methode, die `Insert(Int32,DataGridViewRow)` Überladung der der <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> -Methode, und die <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> Methode der <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>Auflistung.  
  
 Um zu bestimmen, ob eine Zeile freigegeben ist, verwenden Sie die <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> Methode, um das Zeilenobjekt abgerufen, und klicken Sie dann Überprüfen des Objekts <xref:System.Windows.Forms.DataGridViewBand.Index%2A> Eigenschaft. Freigegebene Zeilen verfügen immer über eine <xref:System.Windows.Forms.DataGridViewBand.Index%2A> -Eigenschaftswert von-1.  
  
## <a name="preventing-rows-from-becoming-unshared"></a>Verhindert, dass Zeilen aufgehoben  
 Freigegebene Zeilen können durch Code oder Benutzeraktionen aufgehoben werden. Um Auswirkungen auf die Leistung zu vermeiden, sollten Sie vermeiden, verursacht der Zeilen aufgehoben wird. Sie können während der Anwendungsentwicklung behandeln die <xref:System.Windows.Forms.DataGridView.RowUnshared> Ereignis, um zu bestimmen, wann der Zeilen aufgehoben wird. Dies ist hilfreich beim Debuggen von Problemen Freigeben von Zeilen.  
  
 Um zu verhindern, dass Zeilen aufgehoben, verwenden Sie die folgenden Richtlinien:  
  
-   Indizierung zu vermeiden der <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung oder durchlaufen, bis sie mit einem `foreach` Schleife. Normalerweise müssen Sie nicht direkt auf Zeilen zugreifen. <xref:System.Windows.Forms.DataGridView> Methoden, die mit Zeilen arbeiten übernehmen Zeile Instanzen, sondern die Argumente für den Zeilenindex. Darüber hinaus Empfangshandler für zeilenbezogenen Ereignisse Ereignisargumentobjekten mit Eigenschaften für die Zeile, die Sie verwenden können, um Zeilen zu ändern, ohne dass sie aufgehoben.  
  
-   Wenn Sie ein Zeilenobjekt zugreifen müssen, verwenden Sie die <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> -Methode und übergeben Sie den Index der Zeile tatsächliche. Beachten Sie jedoch, dass Ändern einer freigegebenen Zeile-Objekt, das Abrufen, der über diese Methode alle Zeilen geändert werden, die dieses Objekt gemeinsam nutzen. Die Zeile für neue Datensätze ist nicht mit anderen Zeilen hat jedoch freigegeben, damit es nicht betroffen sind, wenn Sie eine anderen Zeile ändern. Beachten Sie außerdem, dass unterschiedliche Zeilen, die durch eine freigegebene Zeile dargestellt wird, verschiedene Kontextmenüs aufweisen können. Um das Kontextmenü für die richtige Instanz einer freigegebenen Zeile abzurufen, verwenden Sie die <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> -Methode und übergeben Sie den Index der Zeile tatsächliche. Wenn Sie Zugriff auf die freigegebenen Zeile <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> Eigenschaft stattdessen verwendet der Index der freigegebenen Zeile 1 und wird nicht das richtige Kontextmenü abgerufen werden.  
  
-   Vermeiden Sie die Indizierung der <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType> Auflistung. Direkten Zugriff auf eine Zelle führt dazu, dass die übergeordneten Zeile aufgehoben und Instanziierung eines neuen <xref:System.Windows.Forms.DataGridViewRow>. Handler für Ereignisse in Zusammenhang mit Zelle erhalten Ereignisargumentobjekten mit Zelleigenschaften, die Sie verwenden können, um Zellen zu bearbeiten, ohne dass der Zeilen aufgehoben wird. Sie können auch die <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> Eigenschaft, um die Zeilen- und Spaltenindizes der aktuellen Zelle abzurufen, ohne direkt auf die Zelle.  
  
-   Vermeiden Sie zellenbasierte Auswahlmodi. Diese Modi dazu führen, dass Zeilen aufgehoben wird. Legen Sie stattdessen die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.  
  
-   Behandeln keine der <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType> oder <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType> Ereignisse. Diese Ereignisse dazu führen, dass Zeilen aufgehoben wird. Rufen Sie außerdem nicht den <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> oder <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType> Methoden, die diese Ereignisse auslösen.  
  
-   Keinen Zugriff auf die <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType> Auflistung bei der <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> Eigenschaftswert ist <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>, oder <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>. Dies bewirkt, dass alle ausgewählten Zeilen aufgehoben wird.  
  
-   Rufen Sie nicht die <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType> Methode. Diese Methode kann dazu führen, dass Zeilen aufgehoben wird.  
  
-   Rufen Sie nicht die <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType> Methode bei der <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> Eigenschaftswert ist <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>. Dies bewirkt, dass alle Zeilen aufgehoben wird.  
  
-   Legen Sie nicht die <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> oder <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> Eigenschaft einer Zelle, `false` Wenn in der Spalte die entsprechende Eigenschaft auf festgelegt ist `true`. Dies bewirkt, dass alle Zeilen aufgehoben wird.  
  
-   Keinen Zugriff auf die <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType> Eigenschaft. Dies bewirkt, dass alle Zeilen aufgehoben wird.  
  
-   Rufen Sie nicht die `Sort(IComparer)` Überladung von der <xref:System.Windows.Forms.DataGridView.Sort%2A> Methode. Sortieren mit einem benutzerdefinierten Vergleich bewirkt, dass alle Zeilen aufgehoben wird.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Virtueller Modus im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Zellstile im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Festlegen von Standardzellenformaten für das DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)
