---
title: Spaltenssortiermodi im DataGridView-Steuerelement von Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: b8f6048946d367dd79b1ce0d23d84446ffdb1115
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106665"
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Spaltenssortiermodi im DataGridView-Steuerelement von Windows Forms
<xref:System.Windows.Forms.DataGridView> Spalten weisen drei Sortierungsmodi. Der Sortiermodus für jede Spalte wird angegeben, über die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> -Eigenschaft der Spalte, die auf eine der folgenden festgelegt werden, kann <xref:System.Windows.Forms.DataGridViewColumnSortMode> -Enumerationswerte fest.  
  
|`DataGridViewColumnSortMode` -Wert|Beschreibung|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|Standardwert für Textspalten-Feld. Wenn Spaltenheader für die Auswahl verwendet werden, automatisch auf die Spaltenüberschrift sortiert die <xref:System.Windows.Forms.DataGridView> nach dieser Spalte und zeigt ein Symbol, der die Sortierreihenfolge angibt.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|Standard für nicht-Text-Feld-Spalten. Sie können programmgesteuert in dieser Spalte sortieren. Allerdings ist es nicht zum Sortieren, vorgesehen, damit kein Speicherplatz für das Sortiersymbol reserviert ist.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|Sie können programmgesteuert in dieser Spalte sortieren, und das Sortiersymbol Platz reserviert ist.|  
  
 Möglicherweise möchten Sie den Sortiermodus für eine Spalte zu ändern, die standardmäßig <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> Werte enthalten, die sinnvoll sortiert werden können. Z. B. Wenn Sie eine Datenbankspalte mit Zahlen, die Element-Zustände darstellen haben, können Sie diese Zahlen als entsprechende Symbole anzeigen durch die Bindung einer Image-Spalte in der Datenbankspalte. Anschließend können Sie die numerischen Zellenwerte ändern, in dem Image-Display-Werte in einem Handler für die <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> Ereignis. In diesem Fall Festlegen der <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> Eigenschaft <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> können die Benutzer auf die Spalte zu sortieren. Automatische Sortierung ermöglicht Benutzern die Gruppierung der Elemente, die den gleichen Zustand aufweisen, selbst wenn die Zustände für die Zahlen nicht über eine natürliche Folge verfügen. Kontrollkästchen-Spalten sind ein weiteres Beispiel, in denen eignet sich automatische Sortierung zum Gruppieren von Elementen in den gleichen Zustand.  
  
 Sie sortieren können ein <xref:System.Windows.Forms.DataGridView> programmgesteuert durch die Werte in einer Spalte oder in mehreren Spalten, unabhängig von der <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> Einstellungen. Programmgesteuertes Sortieren ist nützlich, wenn Sie eine eigene Benutzeroberfläche (UI) für die Sortierung bereitstellen möchten, oder wenn benutzerdefinierte Sortierung implementiert werden sollen. Bietet eine eigene Sortierung Benutzeroberfläche nützlich ist, z. B. beim Festlegen der <xref:System.Windows.Forms.DataGridView> Auswahlmodus zu aktivieren. In diesem Fall auch die Spaltenüberschriften für die Sortierung verwendet werden können, trotzdem die Headern, die das entsprechende Sortiersymbol angezeigt werden soll, und Sie festlegen, würde die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> Eigenschaft <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>.  
  
 Spalten in den Modus der programmgesteuerten Sortierung festgelegt, werden nicht automatisch ein Sortiersymbol angezeigt. Für diese Spalten, Sie müssen das Symbol selbst anzeigen durch Festlegen der <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> Eigenschaft. Dies ist erforderlich, wenn Sie Flexibilität in benutzerdefinierten sortieren möchten. Wenn Sie sortieren, z. B. die <xref:System.Windows.Forms.DataGridView> nach mehreren Spalten, Sie möchten mehrere Sortiersymbole oder keine Sortiersymbol anzuzeigen.  
  
 Obwohl Sie programmgesteuert sortieren können ein <xref:System.Windows.Forms.DataGridView> nach einer beliebigen Spalte, einige Spalten, z. B. Schaltflächenspalten, möglicherweise keine Werte, die sinnvoll sortiert werden können. Für diese Spalten ein <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> eigenschaftseinstellung <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> gibt an, dass es nie zum Sortieren, verwendet wird, daher keine Notwendigkeit zum Reservieren von Speicherplatz in der Kopfzeile für das Sortieren-Symbol besteht.  
  
 Wenn eine <xref:System.Windows.Forms.DataGridView> ist sortiert, können Sie bestimmen sowohl die Sortierspalte und die Sortierreihenfolge Überprüfen der Werte von der <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> und <xref:System.Windows.Forms.DataGridView.SortOrder%2A> Eigenschaften. Diese Werte sind nach einem benutzerdefinierten Sortiervorgang ohne Bedeutung. Weitere Informationen zum benutzerdefinierten Sortieren finden Sie im Abschnitt benutzerdefinierte Sortierung weiter unten in diesem Thema.  
  
 Wenn eine <xref:System.Windows.Forms.DataGridView> Steuerelement mit gebundene und ungebundene Spalten sortiert wird, nicht automatisch die Werte in den ungebundenen Spalten beibehalten werden. Um diese Werte zu erhalten, müssen Sie den virtuellen Modus implementieren, durch Festlegen der <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft `true` und behandeln die <xref:System.Windows.Forms.DataGridView.CellValueNeeded> und <xref:System.Windows.Forms.DataGridView.CellValuePushed> Ereignisse. Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren des virtuellen Modus in der Windows Forms-DataGridView-Steuerelement](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md). Sortieren nach ungebundenen Spalten im gebundenen Modus wird nicht unterstützt.  
  
## <a name="programmatic-sorting"></a>Programmgesteuertes Sortieren  
 Sie sortieren können ein <xref:System.Windows.Forms.DataGridView> programmgesteuert durch Aufrufen der <xref:System.Windows.Forms.DataGridView.Sort%2A> Methode.  
  
 Die `Sort(DataGridViewColumn,ListSortDirection)` Überladung von der <xref:System.Windows.Forms.DataGridView.Sort%2A> -Methode übernimmt eine <xref:System.Windows.Forms.DataGridViewColumn> und <xref:System.ComponentModel.ListSortDirection> Enumerationswert als Parameter. Diese Überladung ist nützlich, beim Sortieren nach Spalten mit Werten, die sinnvoll sortiert werden können, die aber nicht möchten, konfigurieren Sie für die automatische Sortierung. Wenn Sie diese Überladung aufrufen, und übergeben Sie eine Spalte mit einer <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> Eigenschaftswert <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> und <xref:System.Windows.Forms.DataGridView.SortOrder%2A> Eigenschaften automatisch festgelegt, und das entsprechende Sortiersymbol wird in der Kopfzeile der Spalte angezeigt.  
  
> [!NOTE]
>  Wenn die <xref:System.Windows.Forms.DataGridView> -Steuerelement an eine externe Datenquelle gebunden ist, durch Festlegen der <xref:System.Windows.Forms.DataGridView.DataSource%2A> -Eigenschaft, die `Sort(DataGridViewColumn,ListSortDirection)` methodenüberladung funktioniert nicht für ungebundene Spalten. Darüber hinaus, wenn die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft `true`, rufen diese Überladung können Sie nur für gebundene Spalten. Um zu bestimmen, ob eine Spalte datengebunden ist, überprüfen Sie die <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A> -Eigenschaftswert. Sortieren von ungebundenen Spalten im gebundenen Modus wird nicht unterstützt.  
  
## <a name="custom-sorting"></a>Benutzerdefinierte Sortierung  
 Sie können anpassen, <xref:System.Windows.Forms.DataGridView> mithilfe der `Sort(IComparer)` Überladung von der <xref:System.Windows.Forms.DataGridView.Sort%2A> Methode oder durch das Behandeln der <xref:System.Windows.Forms.DataGridView.SortCompare> Ereignis.  
  
 Die `Sort(IComparer)` Überladung nimmt eine Instanz einer Klasse, die implementiert die <xref:System.Collections.IComparer> -Schnittstelle als Parameter. Diese Überladung ist nützlich, wenn Sie benutzerdefiniertes Sortieren bereitstellen möchten; Wenn die Werte in einer Spalte keine natürliche Sortierreihenfolge haben oder wenn die natürliche Sortierreihenfolge ist beispielsweise nicht geeignet. In diesem Fall können Sie keine automatische Sortierung, aber Sie sollten immer noch die Benutzer durch Klicken auf die Spaltenüberschriften sortieren. Sie können diese Überladung aufrufen, in einem Handler für die <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> Ereignis, wenn Sie keine Spaltenüberschriften zur Auswahl verwenden.  
  
> [!NOTE]
>  Die `Sort(IComparer)` methodenüberladung funktioniert nur, wenn die <xref:System.Windows.Forms.DataGridView> -Steuerelement nicht an eine externe Datenquelle gebunden ist und die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaftswert ist `false`. Zum Anpassen der Sortierung, die für Spalten, die an eine externe Datenquelle gebunden ist, müssen Sie die Sortiervorgänge bereitgestellt, die von der Datenquelle verwenden. Im virtuellen Modus befindet müssen Sie Ihre eigenen Sortieroperationen für ungebundene Spalten angeben.  
  
 Verwenden der `Sort(IComparer)` methodenüberladung, müssen Sie eine eigene Klasse, die implementiert erstellen die <xref:System.Collections.IComparer> Schnittstelle. Für diese Schnittstelle muss die Klasse zum Implementieren der <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType> Methode, an die die <xref:System.Windows.Forms.DataGridView> übergibt <xref:System.Windows.Forms.DataGridViewRow> Objekte als Eingabe, wenn die `Sort(IComparer)` methodenüberladung wird aufgerufen. Mit dieser Option können Sie berechnen, die richtige Zeile Reihenfolge basierend auf den Werten in einer beliebigen Spalte.  
  
 Die `Sort(IComparer)` methodenüberladung wird nicht festgelegt. die <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> und <xref:System.Windows.Forms.DataGridView.SortOrder%2A> Eigenschaften, sodass immer festgelegt werden muss die <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> Eigenschaft, um das Sortiersymbol anzuzeigen.  
  
 Als Alternative zu den `Sort(IComparer)` methodenüberladung bieten, da Sie durch die Implementierung eines Handlers für eine benutzerdefinierte Sortierung der <xref:System.Windows.Forms.DataGridView.SortCompare> Ereignis. Dieses Ereignis tritt auf, wenn Benutzer auf die Header der Spalten, die so konfiguriert, für die automatische Sortierung oder beim Aufrufen der `Sort(DataGridViewColumn,ListSortDirection)` Überladung von der <xref:System.Windows.Forms.DataGridView.Sort%2A> Methode. Das Ereignis tritt auf, für jedes Paar Zeilen im Steuerelement, sodass Sie die richtige Reihenfolge berechnen.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.DataGridView.SortCompare> Ereignis tritt nicht auf Wenn die <xref:System.Windows.Forms.DataGridView.DataSource%2A> festgelegt wird oder wenn die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaftswert ist `true`.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>
- [Sortieren von Daten im DataGridView-Steuerelement in Windows Forms](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Festlegen der Sortierungsmodi für Spalten im DataGridView-Steuerelement in Windows Forms](set-the-sort-modes-for-columns-wf-datagridview-control.md)
- [Vorgehensweise: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
