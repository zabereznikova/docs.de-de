---
title: Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
ms.openlocfilehash: f97576218df651553ed1ac5f681d1ec0b4ab5ef3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms
Die <xref:System.Windows.Forms.DataGridView> -Steuerelement kann Daten in drei verschiedenen Modi anzeigen: gebunden, ungebunden und virtuellen. Wählen Sie die je nach Ihren Anforderungen am besten geeigneten Modus.  
  
## <a name="unbound"></a>Nicht gebundene  
 Ungebunden-Modus eignet sich zum Anzeigen von relativ kleine Datenmengen, die Sie programmgesteuert zu verwalten. Verbinden Sie keinesfalls die <xref:System.Windows.Forms.DataGridView> Steuerelement direkt an eine Datenquelle wie gebundenen Modus. Stattdessen, Sie müssen füllen Sie das Steuerelement selbst, in der Regel mithilfe der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> Methode.  
  
 Ungebunden-Modus kann besonders hilfreich für statische, schreibgeschützte Daten oder wenn Sie Ihren eigenen Code, der Interaktion mit einem externen Datenspeicher bereitstellen möchten. Wenn Sie Ihre Benutzer für die Interaktion mit einer externen Datenquelle möchten, jedoch verwenden in der Regel gebunden-Modus Sie.  
  
 Ein Beispiel für eine schreibgeschützte ungebundene <xref:System.Windows.Forms.DataGridView>, finden Sie unter [Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="bound"></a>gebunden  
 Gebundene Modus eignet sich für die Verwaltung von Daten mithilfe der automatischen Interaktion mit dem Datenspeicher. Sie können Anfügen der <xref:System.Windows.Forms.DataGridView> Steuerelement direkt an die Datenquelle durch Festlegen der <xref:System.Windows.Forms.DataGridView.DataSource%2A> Eigenschaft. Wenn das Steuerelement gebunden ist, werden Datenzeilen abgelegt und ohne die Notwendigkeit der expliziten Verwaltung ihrerseits abgerufen. Wenn die <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> Eigenschaft `true`, jede Spalte in der Datenquelle führt dazu, dass eine entsprechende Spalte im Steuerelement erstellt werden. Wenn Sie Ihre eigenen Spalten erstellen möchten, können Sie diese Eigenschaft festlegen, um `false` und verwenden Sie die <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> Eigenschaft jede Spalte zu binden, wenn Sie ihn konfigurieren. Dies ist hilfreich, wenn einen Spaltentyp, als die Typen verwenden, die in der Standardeinstellung generiert werden sollen. Weitere Informationen finden Sie unter [Spaltentypen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).  
  
 Ein Beispiel für die ein gebundenes <xref:System.Windows.Forms.DataGridView> steuern, finden Sie unter [Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
 Sie können auch ungebundene Spalten zum Hinzufügen einer <xref:System.Windows.Forms.DataGridView> Steuerelement im gebundenen Modus. Dies ist hilfreich, wenn eine Spalte mit Schaltflächen oder Links, mit denen Benutzer zum Ausführen von Aktionen für bestimmte Zeilen angezeigt werden soll. Es ist auch hilfreich, wenn Spalten mit Werten von gebundenen Spalten berechnet. Sie können die Zellenwerte für berechnete Spalten in einem Ereignishandler für Auffüllen der <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis. Bei Verwendung einer <xref:System.Data.DataSet> oder <xref:System.Data.DataTable> als die Datenquelle jedoch möglicherweise möchten Sie verwenden die <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType> Eigenschaft, um stattdessen eine berechnete Spalte erstellen. In diesem Fall die <xref:System.Windows.Forms.DataGridView> Steuerelement berechnete Spalte wie jede andere Spalte in der Datenquelle behandelt.  
  
 Sortieren nach ungebundenen Spalten im gebundenen Modus wird nicht unterstützt. Wenn Sie eine ungebundene Spalte im gebunden-Modus, die Benutzer bearbeitbare Werte enthält erstellen, müssen Sie implementieren virtuellen Modus, um diese Werte zu erhalten, wenn das Steuerelement nach einer gebundenen Spalte sortiert wird.  
  
## <a name="virtual"></a>Virtuelle  
 Mit dem virtuellen Modus können Sie eigene Datenverwaltungsvorgänge implementieren. Dies ist erforderlich, um die Werte von ungebundenen Spalten im gebundenen Modus beizubehalten, wenn das Steuerelement nach gebundenen Spalten sortiert ist. Der Hauptverwendungszweck des virtuellen Modus wird jedoch zum Optimieren der Leistung bei der Interaktion mit großer Datenmengen.  
  
 Sie fügen die <xref:System.Windows.Forms.DataGridView> -Steuerelement in einen Cache, die Sie verwalten und die Code-Steuerelemente, wenn Datenzeilen abgelegt und abgerufen werden. Um den Speicherbedarf gering zu halten, sollte der Cache etwa dieselbe Größe auf die Anzahl der Zeilen angezeigt werden. Wenn der Benutzer neue Zeilen in der Ansicht einen Bildlauf durchführt, wird Code neue Daten aus dem Cache anfordert und löscht optional alte Daten aus dem Arbeitsspeicher.  
  
 Bei der Implementierung des virtuellen Modus, müssen Sie verfolgen, wann eine neue Zeile in das Datenmodell und beim, ein Rollback für das Hinzufügen der neuen Zeile benötigt wird. Die genaue Implementierung dieser Funktion wird die Implementierung des Datenmodells und der Transaktionssemantik des Datenmodells abhängig; Gibt an, ob Commit-Bereich auf die Zelle oder Zeile Ebene ist.  
  
 Weitere Informationen zum virtuellen Modus finden Sie unter [Virtueller Modus im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md). Ein Beispiel, das veranschaulicht, wie Ereignisse des virtuellen Modus verwenden, finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>  
 [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Spaltentypen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 [Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 [Gewusst wie: Binden von Daten an das DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 [Virtueller Modus im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)
