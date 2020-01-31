---
title: Spalten Sortier Modi im DataGridView-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: d1e2f582c9759332e0ed963cb7f88ee052616c45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744196"
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Spaltenssortiermodi im DataGridView-Steuerelement von Windows Forms
<xref:System.Windows.Forms.DataGridView> Spalten haben drei Sortier Modi. Der Sortiermodus für jede Spalte wird durch die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>-Eigenschaft der Spalte angegeben, die auf einen der folgenden <xref:System.Windows.Forms.DataGridViewColumnSortMode> Enumerationswerte festgelegt werden kann.  
  
|`DataGridViewColumnSortMode`-Wert|Beschreibung|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|Standard für Text Feld Spalten. Wenn Spaltenheader nicht für die Auswahl verwendet werden, wird durch Klicken auf die Spaltenüberschrift automatisch die <xref:System.Windows.Forms.DataGridView> nach dieser Spalte sortiert und ein Symbol angezeigt, das die Sortierreihenfolge angibt.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|Standard für nicht-–-Text Feld Spalten. Sie können diese Spalte Programm gesteuert sortieren. Es ist jedoch nicht für die Sortierung vorgesehen, sodass kein Speicherplatz für das Sortier Symbol reserviert ist.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|Sie können diese Spalte Programm gesteuert sortieren, und der Speicherplatz ist für das Sortier Symbol reserviert.|  
  
 Möglicherweise möchten Sie den Sortiermodus für eine Spalte ändern, die standardmäßig <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>, wenn Sie Werte enthält, die für eine sinnvolle Sortierung verwendet werden können. Wenn Sie z. b. eine Daten Bank Spalte mit Zahlen enthalten, die Element Zustände darstellen, können Sie diese Zahlen als entsprechende Symbole anzeigen, indem Sie eine Image-Spalte an die Daten Bank Spalte binden. Sie können dann die numerischen Zellwerte in Bild Anzeigewerte in einem Handler für das <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>-Ereignis ändern. Wenn Sie die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> festlegen, können Ihre Benutzer die Spalte sortieren. Durch das automatische Sortieren können Benutzer Elemente gruppieren, die denselben Zustand aufweisen, auch wenn die Werte, die den Zahlen entsprechen, nicht über eine natürliche Sequenz verfügen. Kontrollkästchen Spalten sind ein weiteres Beispiel, in dem die automatische Sortierung zum Gruppieren von Elementen im gleichen Zustand nützlich ist.  
  
 Sie können eine <xref:System.Windows.Forms.DataGridView> Programm gesteuert nach den Werten in einer Spalte oder in mehreren Spalten sortieren, unabhängig von den <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> Einstellungen. Die programmgesteuerte Sortierung ist nützlich, wenn Sie eine eigene Benutzeroberfläche für die Sortierung bereitstellen möchten oder wenn Sie eine benutzerdefinierte Sortierung implementieren möchten. Das Bereitstellen Ihrer eigenen Sortier Benutzeroberfläche ist beispielsweise hilfreich, wenn Sie den <xref:System.Windows.Forms.DataGridView> Auswahlmodus auf Spaltenheader Auswahl aktivieren festlegen. Obwohl die Spaltenheader nicht für die Sortierung verwendet werden können, möchten Sie in den Headern weiterhin das passende Sortier Symbol anzeigen, sodass Sie die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>festlegen können.  
  
 Für Spalten, die auf den programmgesteuerten Sortiermodus festgelegt sind, wird nicht automatisch ein Sortier Symbol angezeigt. Für diese Spalten müssen Sie das Symbol Selbstanzeigen, indem Sie die <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>-Eigenschaft festlegen. Dies ist erforderlich, wenn Sie die benutzerdefinierte Sortierung flexibel gestalten möchten. Wenn Sie z. b. die <xref:System.Windows.Forms.DataGridView> nach mehreren Spalten sortieren, möchten Sie möglicherweise mehrere Sortier Symbole oder kein Sortier Symbol anzeigen.  
  
 Obwohl Sie eine <xref:System.Windows.Forms.DataGridView> Programm gesteuert nach einer beliebigen Spalte sortieren können, enthalten einige Spalten, wie z. b. Schaltflächen Spalten, möglicherweise keine Werte, die für eine sinnvolle Anordnung erforderlich sind. Für diese Spalten gibt eine <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>-Eigenschafts Einstellung <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> an, dass Sie nie für die Sortierung verwendet wird. Daher ist es nicht erforderlich, Platz in der Kopfzeile für das Sortier Symbol zu reservieren.  
  
 Wenn ein <xref:System.Windows.Forms.DataGridView> sortiert ist, können Sie die Sortier Spalte und die Sortierreihenfolge ermitteln, indem Sie die Werte der Eigenschaften <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> und <xref:System.Windows.Forms.DataGridView.SortOrder%2A> überprüfen. Diese Werte sind nach einem benutzerdefinierten Sortiervorgang nicht aussagekräftig. Weitere Informationen zur benutzerdefinierten Sortierung finden Sie im Abschnitt benutzerdefinierte Sortierung weiter unten in diesem Thema.  
  
 Wenn ein <xref:System.Windows.Forms.DataGridView>-Steuerelement, das sowohl gebundene als auch ungebundene Spalten enthält, sortiert ist, können die Werte in den ungebundenen Spalten nicht automatisch beibehalten werden. Um diese Werte beizubehalten, müssen Sie den virtuellen Modus implementieren, indem Sie die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>-Eigenschaft auf `true` festlegen und die Ereignisse <xref:System.Windows.Forms.DataGridView.CellValueNeeded> und <xref:System.Windows.Forms.DataGridView.CellValuePushed> verarbeiten. Weitere Informationen finden Sie unter Gewusst [wie: Implementieren des virtuellen Modus im Windows Forms DataGridView-Steuer](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)Element. Das Sortieren nach ungebundenen Spalten im gebundenen Modus wird nicht unterstützt.  
  
## <a name="programmatic-sorting"></a>Programmgesteuertes Sortieren  
 Sie können eine <xref:System.Windows.Forms.DataGridView> Programm gesteuert sortieren, indem Sie die <xref:System.Windows.Forms.DataGridView.Sort%2A>-Methode aufrufen.  
  
 Die `Sort(DataGridViewColumn,ListSortDirection)` Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>-Methode nimmt einen <xref:System.Windows.Forms.DataGridViewColumn> und einen <xref:System.ComponentModel.ListSortDirection> Enumerationswert als Parameter an. Diese Überladung ist nützlich, wenn Spalten mit Werten sortiert werden, die für eine sinnvolle Sortierung geeignet sind, aber nicht für die automatische Sortierung konfiguriert werden sollen. Wenn Sie diese Überladung aufrufen und eine Spalte mit dem <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>-Eigenschafts Wert <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>übergeben, werden die Eigenschaften <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> und <xref:System.Windows.Forms.DataGridView.SortOrder%2A> automatisch festgelegt, und das entsprechende Sortier Symbol wird in der Spaltenüberschrift angezeigt.  
  
> [!NOTE]
> Wenn das <xref:System.Windows.Forms.DataGridView>-Steuerelement durch Festlegen der <xref:System.Windows.Forms.DataGridView.DataSource%2A>-Eigenschaft an eine externe Datenquelle gebunden ist, kann die `Sort(DataGridViewColumn,ListSortDirection)`-Methoden Überladung nicht für ungebundene Spalten verwendet werden. Außerdem können Sie diese Überladung nur für gebundene Spalten aufrufen, wenn die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>-Eigenschaft `true`ist. Überprüfen Sie den <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A>-Eigenschafts Wert, um zu bestimmen, ob eine Spalte Daten gebunden ist. Das Sortieren von ungebundenen Spalten im gebundenen Modus wird nicht unterstützt.  
  
## <a name="custom-sorting"></a>Benutzerdefinierte Sortierung  
 Sie können <xref:System.Windows.Forms.DataGridView> anpassen, indem Sie die `Sort(IComparer)` Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>-Methode verwenden oder das <xref:System.Windows.Forms.DataGridView.SortCompare>-Ereignis behandeln.  
  
 Die `Sort(IComparer)`-Methoden Überladung nimmt eine Instanz einer Klasse an, die die <xref:System.Collections.IComparer>-Schnittstelle als Parameter implementiert. Diese Überladung ist nützlich, wenn Sie eine benutzerdefinierte Sortierung bereitstellen möchten. Dies ist beispielsweise der Fall, wenn die Werte in einer Spalte nicht über eine natürliche Sortierreihenfolge verfügen oder wenn die natürliche Sortierreihenfolge ungeeignet ist. In diesem Fall können Sie die automatische Sortierung nicht verwenden, aber Sie möchten möglicherweise dennoch, dass die Benutzer durch Klicken auf die Spaltenüberschriften sortiert werden. Sie können diese Überladung in einem Handler für das <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick>-Ereignis aufrufen, wenn Sie keine Spaltenüberschriften zur Auswahl verwenden.  
  
> [!NOTE]
> Die `Sort(IComparer)`-Methoden Überladung funktioniert nur, wenn das <xref:System.Windows.Forms.DataGridView>-Steuerelement nicht an eine externe Datenquelle gebunden ist und der <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>-Eigenschafts Wert `false`ist. Zum Anpassen der Sortierung für Spalten, die an eine externe Datenquelle gebunden sind, müssen Sie die von der Datenquelle bereitgestellten Sortiervorgänge verwenden. Im virtuellen Modus müssen Sie eigene Sortiervorgänge für ungebundene Spalten bereitstellen.  
  
 Wenn Sie die `Sort(IComparer)`-Methoden Überladung verwenden möchten, müssen Sie eine eigene Klasse erstellen, die die <xref:System.Collections.IComparer>-Schnittstelle implementiert. Diese Schnittstelle erfordert, dass Ihre Klasse die <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType>-Methode implementiert, an die der <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridViewRow> Objekte als Eingabe übergibt, wenn die `Sort(IComparer)`-Methoden Überladung aufgerufen wird. Damit können Sie die richtige Zeilen Reihenfolge basierend auf den Werten in einer beliebigen Spalte berechnen.  
  
 Die `Sort(IComparer)`-Methoden Überladung legt die Eigenschaften <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> und <xref:System.Windows.Forms.DataGridView.SortOrder%2A> nicht fest. Daher müssen Sie immer die <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>-Eigenschaft festlegen, um das Sortier Symbol anzuzeigen.  
  
 Als Alternative zur `Sort(IComparer)`-Methoden Überladung können Sie eine benutzerdefinierte Sortierung bereitstellen, indem Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.SortCompare>-Ereignis implementieren. Dieses Ereignis tritt auf, wenn Benutzer auf die Header der Spalten klicken, die für die automatische Sortierung konfiguriert wurden, oder wenn Sie die `Sort(DataGridViewColumn,ListSortDirection)` Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A> Methode aufrufen. Das-Ereignis tritt für jedes Zeilen Paar im-Steuerelement auf, sodass Sie die richtige Reihenfolge berechnen können.  
  
> [!NOTE]
> Das <xref:System.Windows.Forms.DataGridView.SortCompare>-Ereignis tritt nicht auf, wenn die <xref:System.Windows.Forms.DataGridView.DataSource%2A>-Eigenschaft festgelegt ist oder wenn der <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>-Eigenschafts Wert `true`ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>
- [Sortieren von Daten im DataGridView-Steuerelement in Windows Forms](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Festlegen der Sortierungsmodi für Spalten im DataGridView-Steuerelement in Windows Forms](set-the-sort-modes-for-columns-wf-datagridview-control.md)
- [Gewusst wie: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
