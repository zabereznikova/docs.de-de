---
title: Datenanzeige Modi im DataGridView-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
ms.openlocfilehash: ad6be647e3a36904b055fd6771f539df28938fab
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744007"
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms
Das <xref:System.Windows.Forms.DataGridView> Steuerelement kann Daten in drei unterschiedlichen Modi anzeigen: gebunden, ungebunden und virtuell. Wählen Sie den am besten geeigneten Modus basierend auf Ihren Anforderungen aus.  
  
## <a name="unbound"></a>Ungebundenen  
 Der ungebundene Modus eignet sich für die Anzeige relativ kleiner Datenmengen, die Sie Programm gesteuert verwalten. Sie fügen das <xref:System.Windows.Forms.DataGridView>-Steuerelement nicht direkt an eine Datenquelle an, wie im gebundenen Modus. Stattdessen müssen Sie das Steuerelement selbst auffüllen, in der Regel mit der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType>-Methode.  
  
 Der ungebundene Modus kann für statische, schreibgeschützte Daten besonders nützlich sein, oder Sie möchten Ihren eigenen Code bereitstellen, der mit einem externen Datenspeicher interagiert. Wenn Sie möchten, dass Ihre Benutzer mit einer externen Datenquelle interagieren, verwenden Sie jedoch in der Regel den gebundenen Modus.  
  
 Ein Beispiel, das eine schreibgeschützte, nicht gebundene <xref:System.Windows.Forms.DataGridView>verwendet, finden Sie unter Gewusst [wie: Erstellen eines ungebundenen Windows Forms DataGridView-Steuer](how-to-create-an-unbound-windows-forms-datagridview-control.md)Elements.  
  
## <a name="bound"></a>Gebunden  
 Der gebundene Modus eignet sich für die Datenverwaltung mithilfe der automatischen Interaktion mit dem Datenspeicher. Sie können das <xref:System.Windows.Forms.DataGridView>-Steuerelement direkt an seine Datenquelle anfügen, indem Sie die <xref:System.Windows.Forms.DataGridView.DataSource%2A>-Eigenschaft festlegen. Wenn das Steuerelement Daten gebunden ist, werden Daten Zeilen per pushübertragung übertragen und abgerufen, ohne dass eine explizite Verwaltung erforderlich ist. Wenn die <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A>-Eigenschaft `true`ist, bewirkt jede Spalte in der Datenquelle, dass eine entsprechende Spalte im-Steuerelement erstellt wird. Wenn Sie Ihre eigenen Spalten erstellen möchten, können Sie diese Eigenschaft auf `false` festlegen und die <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A>-Eigenschaft verwenden, um die einzelnen Spalten zu binden, wenn Sie Sie konfigurieren. Dies ist hilfreich, wenn Sie einen anderen Spaltentyp als die standardmäßig generierten Typen verwenden möchten. Weitere Informationen finden Sie unter [Spaltentypen im Windows Forms DataGridView-Steuer](column-types-in-the-windows-forms-datagridview-control.md)Element.  
  
 Ein Beispiel, das ein gebundenes <xref:System.Windows.Forms.DataGridView> Steuerelement verwendet, finden Sie unter Exemplarische Vorgehensweise [: Validieren von Daten im Windows Forms DataGridView-Steuer](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)Element.  
  
 Sie können auch ungebundene Spalten zu einem <xref:System.Windows.Forms.DataGridView>-Steuerelement im gebundenen Modus hinzufügen. Dies ist hilfreich, wenn Sie eine Spalte mit Schaltflächen oder Links anzeigen möchten, die es Benutzern ermöglichen, Aktionen für bestimmte Zeilen auszuführen. Es ist auch hilfreich, Spalten mit Werten anzuzeigen, die aus gebundenen Spalten berechnet werden. Sie können die Zellwerte für berechnete Spalten in einem Handler für das <xref:System.Windows.Forms.DataGridView.CellFormatting>-Ereignis auffüllen. Wenn Sie jedoch eine <xref:System.Data.DataSet> oder <xref:System.Data.DataTable> als Datenquelle verwenden, sollten Sie stattdessen die <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>-Eigenschaft verwenden, um stattdessen eine berechnete Spalte zu erstellen. In diesem Fall behandelt das <xref:System.Windows.Forms.DataGridView>-Steuerelement die berechnete Spalte wie jede andere Spalte in der Datenquelle.  
  
 Das Sortieren nach ungebundenen Spalten im gebundenen Modus wird nicht unterstützt. Wenn Sie eine ungebundene Spalte im gebundenen Modus erstellen, die vom Benutzer bearbeitbare Werte enthält, müssen Sie den virtuellen Modus implementieren, um diese Werte beizubehalten, wenn das Steuerelement nach einer gebundenen Spalte sortiert wird.  
  
## <a name="virtual"></a>Virtual  
 Mit dem virtuellen Modus können Sie eigene Daten Verwaltungsvorgänge implementieren. Dies ist erforderlich, um die Werte ungebundener Spalten im gebundenen Modus beizubehalten, wenn das Steuerelement nach gebundenen Spalten sortiert wird. Der primäre Einsatz des virtuellen Modus ist jedoch die Optimierung der Leistung bei der Interaktion mit großen Datenmengen.  
  
 Sie fügen das <xref:System.Windows.Forms.DataGridView>-Steuerelement an einen von Ihnen verwalteten Cache an, und der Code steuert, wann Daten Zeilen per pushübertragung und-Pull abgerufen werden. Um den Speicherbedarf gering zu halten, sollte der Cache der Größe entsprechend der Anzahl der derzeit angezeigten Zeilen entsprechen. Wenn der Benutzer einen Bildlauf in neue Zeilen durchführt, fordert der Code neue Daten aus dem Cache an und leert optional alte Daten aus dem Arbeitsspeicher.  
  
 Wenn Sie den virtuellen Modus implementieren, müssen Sie nachverfolgen, wann eine neue Zeile im Datenmodell benötigt wird und wann das Hinzufügen der neuen Zeile rückgängig wird. Die genaue Implementierung dieser Funktionalität hängt von der Implementierung des Datenmodells und der Transaktions Semantik des Datenmodells ab. Gibt an, ob der Commit-Bereich auf Zellen-oder Zeilenebene erfolgt.  
  
 Weitere Informationen zum virtuellen Modus finden Sie [im Windows Forms DataGridView-Steuerelement im virtuellen Modus](virtual-mode-in-the-windows-forms-datagridview-control.md). Ein Beispiel für die Verwendung von Ereignissen im virtuellen Modus finden Sie unter Exemplarische [Vorgehensweise: Implementieren des virtuellen Modus im Windows Forms DataGridView-Steuer](implementing-virtual-mode-wf-datagridview-control.md)Element.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>
- [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Spaltentypen im DataGridView-Steuerelement in Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
- [Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [Gewusst wie: Binden von Daten an das DataGridView-Steuerelement in Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
- [Virtueller Modus im DataGridView-Steuerelement in Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
