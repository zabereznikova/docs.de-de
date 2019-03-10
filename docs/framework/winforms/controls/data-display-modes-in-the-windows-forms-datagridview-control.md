---
title: Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
ms.openlocfilehash: 86eda82cad778978711520bc2951a7a35d133753
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703064"
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms
Die <xref:System.Windows.Forms.DataGridView> Steuerelement kann Daten in drei verschiedenen Modi anzeigen: gebunden, aufgehoben und virtuell. Wählen Sie den am besten geeigneten Modus, die je nach Ihren Anforderungen.  
  
## <a name="unbound"></a>Ungebundene  
 Ungebundene Modus eignet sich für die Anzeige von relativ kleine Datenmengen, die Sie programmgesteuert zu verwalten. Sie fügen nicht an die <xref:System.Windows.Forms.DataGridView> Steuerelement direkt an eine Datenquelle wie gebunden-Modus. Sie müssen füllen Sie stattdessen das Steuerelement selbst in der Regel mithilfe der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> Methode.  
  
 Nicht gebundene Modus möglich besonders nützlich für statische, schreibgeschützte Daten, oder wenn Sie Ihren eigenen Code, mit der interagiert mit einem externen Datenspeicher bereitstellen möchten. Wenn Sie Ihre Benutzer für die Interaktion mit einer externen Datenquelle möchten, jedoch verwenden in der Regel gebunden-Modus Sie.  
  
 Ein Beispiel für eine schreibgeschützte ungebundene <xref:System.Windows.Forms.DataGridView>, finden Sie unter [Vorgehensweise: Erstellen eines ungebundenen Windows Forms-DataGridView-Steuerelements](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="bound"></a>Gebunden  
 Gebundene Modus eignet sich für die Verwaltung von Daten mithilfe der automatischen Interaktion mit dem Datenspeicher. Sie anfügen können die <xref:System.Windows.Forms.DataGridView> Steuerelement direkt in der Datenquelle durch Festlegen der <xref:System.Windows.Forms.DataGridView.DataSource%2A> Eigenschaft. Wenn das Steuerelement datengebunden ist, werden Datenzeilen mithilfe von Push übertragen und abgerufen werden, ohne dass explizite Verwaltung Ihrerseits erforderlich. Wenn die <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> Eigenschaft `true`, jede Spalte in der Datenquelle führt dazu, dass eine entsprechende Spalte in das Steuerelement erstellt werden. Wenn Sie Ihre eigenen Spalten erstellen möchten, können Sie diese Eigenschaft festlegen, um `false` und verwenden Sie die <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> Eigenschaft, um jede Spalte zu binden, wenn Sie es konfigurieren. Dies ist nützlich, wenn einen Spaltentyp, als die Typen zu verwenden, wird standardmäßig generiert werden, sollen. Weitere Informationen finden Sie unter [Spaltentypen im DataGridView-Steuerelement in Windows Forms](column-types-in-the-windows-forms-datagridview-control.md).  
  
 Ein Beispiel für eine Grenze <xref:System.Windows.Forms.DataGridView> steuern, finden Sie unter [Exemplarische Vorgehensweise: Überprüfen von Daten in der Windows Forms-DataGridView-Steuerelement](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
 Sie können auch ungebundene Spalten zum Hinzufügen einer <xref:System.Windows.Forms.DataGridView> Steuerelement im gebundenen Modus. Dies ist nützlich, wenn Sie eine Spalte mit Schaltflächen oder Links, mit denen Benutzern das Ausführen von Aktionen für bestimmte Zeilen anzeigen möchten. Es ist auch nützlich, um Spalten mit gebundenen Spalten berechnete Werte angezeigt werden soll. Sie können die Zellenwerte für berechnete Spalten in einem Handler für Auffüllen der <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis. Bei Verwendung einer <xref:System.Data.DataSet> oder <xref:System.Data.DataTable> als Datenquelle, jedoch möglicherweise verwenden möchten die <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType> Eigenschaft, um eine berechnete Spalte erstellen. In diesem Fall die <xref:System.Windows.Forms.DataGridView> Steuerelement behandelt die berechnete Spalte wie jede andere Spalte in der Datenquelle.  
  
 Sortieren nach ungebundenen Spalten im gebundenen Modus wird nicht unterstützt. Wenn Sie eine ungebundene Spalte im gebundenen Modus, die Benutzer bearbeitbare Werte enthält erstellen, müssen Sie implementieren virtuellen Modus befindet, um diese Werte zu erhalten, wenn das Steuerelement nach einer gebundenen Spalte sortiert wird.  
  
## <a name="virtual"></a>Virtual  
 Mit dem virtuellen Modus können Sie eigene Datenverwaltungsvorgänge implementieren. Dies ist erforderlich, um die Werte von ungebundenen Spalten im gebundenen Modus verwalten, wenn das Steuerelement gebundenen Spalten sortiert werden. Der Hauptverwendungszweck des virtuellen Modus befindet, ist jedoch zum Optimieren der Leistung bei der Interaktion mit großen Datenmengen.  
  
 Sie fügen die <xref:System.Windows.Forms.DataGridView> Steuerelement auf einen Cache, die Sie verwalten und Ihre Steuerelemente mit Code, wenn Daten mithilfe von Push übertragen und abgerufen werden. Um den Speicherbedarf gering zu halten, sollte der Cache ähnliche Größe auf die Anzahl der Zeilen angezeigt werden. Wenn der Benutzer neue Zeilen in der Ansicht einen Bildlauf durchführt, wird Ihr Code neue Daten aus dem Cache anfordert, und löscht optional alte Daten aus dem Arbeitsspeicher.  
  
 Wenn Sie virtuellen Modus implementieren, müssen Sie nachverfolgen, wenn eine neue Zeile in das Datenmodell und beim Zurücksetzen das Hinzufügen der neuen Zeile benötigt wird. Die genaue Implementierung dieser Funktionalität richtet sich nach der Implementierung des Datenmodells und der Transaktionssemantik des Datenmodells; Gibt an, ob ein Commit-Bereich auf die Zelle oder Zeile ist.  
  
 Weitere Informationen zu virtuellen Modus befindet, finden Sie unter [Virtueller Modus im DataGridView-Steuerelement von Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md). Ein Beispiel, das zeigt, wie Sie die Ereignisse des virtuellen Modus verwenden, finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus in der Windows Forms-DataGridView-Steuerelement](implementing-virtual-mode-wf-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>
- [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Spaltentypen im DataGridView-Steuerelement in Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
- [Exemplarische Vorgehensweise: Erstellen eine nicht gebundene Windows Forms-DataGridView-Steuerelement](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [Vorgehensweise: Binden von Daten an das DataGridView-Steuerelement in Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
- [Virtueller Modus im DataGridView-Steuerelement in Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
