---
title: Spaltenssortiermodi im DataGridView-Steuerelement von Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a98e57d325fc7fd9413babb45d235cbb353a0c86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Spaltenssortiermodi im DataGridView-Steuerelement von Windows Forms
<xref:System.Windows.Forms.DataGridView>Spalten verfügen über drei Sortiermodi. Der Sortiermodus für jede Spalte wird angegeben, über die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> -Eigenschaft der Spalte, die auf eine der folgenden festgelegt werden kann <xref:System.Windows.Forms.DataGridViewColumnSortMode> Enumerationswerte.  
  
|`DataGridViewColumnSortMode`-Wert|Beschreibung|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|Die Standardeinstellung für Spalten von Text im Feld. Wenn die Spaltenheader für die Auswahl verwendet werden, automatisch Sie auf die Spaltenüberschrift sortiert die <xref:System.Windows.Forms.DataGridView> nach dieser Spalte und zeigt ein Symbol, der die Sortierreihenfolge angibt.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|Die Standardeinstellung für Spalten nicht – Textfeld. Sie können diese Spalte programmgesteuert sortieren. Allerdings sind sie nicht für die Sortierung, vorgesehen, sodass kein Speicherplatz für das Sortiersymbol reserviert ist.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|Sie können diese Spalte programmgesteuert sortieren, und Platz für das Sortiersymbol reserviert ist.|  
  
 Möglicherweise möchten Sie den Sortiermodus für eine Spalte zu ändern, die standardmäßig <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> Werte enthalten, die sinnvoll sortiert werden können. Beispielsweise haben eine Datenbankspalte mit Zahlen, die Elementzustände darstellen, können Sie diese Zahlen als entsprechende Symbole anzeigen, indem binden eine Image-Spalte in der Datenbankspalte. Anschließend können Sie die numerischen Zellenwerte ändern, in der Image-Anzeigewerte in einem Ereignishandler für das <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> Ereignis. In diesem Fall Festlegen der <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> Eigenschaft <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> können die Benutzer auf die Spalte zu sortieren. Automatische Sortierung können Ihre Benutzer die Gruppierung der Elemente, die den gleichen Status aufweisen, selbst wenn die Zahlen entsprechenden Zustände keine natürliche Abfolge. Kontrollkästchenspalten sind ein weiteres Beispiel, in denen eignet sich automatische Sortierung zum Gruppieren von Elementen im gleichen Zustand.  
  
 Sie sortieren können ein <xref:System.Windows.Forms.DataGridView> programmgesteuert durch die Werte in einer beliebigen Spalte oder in mehreren Spalten, unabhängig von der <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> Einstellungen. Programmgesteuertes Sortieren ist hilfreich, wenn Sie eine eigene Benutzeroberfläche (UI) für die Sortierung bieten möchten oder wenn Sie benutzerdefinierte Sortierung implementieren möchten. Die Bereitstellung eine eigenen Benutzeroberfläche Sortierung nützlich ist, z. B. beim Festlegen der <xref:System.Windows.Forms.DataGridView> Auswahlmodus Spaltenheaderauswahl aktivieren. In diesem Fall Obwohl Spaltenheader für die Sortierung verwendet werden können, dennoch sollten Sie der Header an die entsprechende Sortiersymbol angezeigt würde die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> Eigenschaft <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>.  
  
 Legen Sie auf den programmatischen Sortiermodus Spalten werden nicht automatisch ein Sortiersymbol angezeigt. Für diese Spalten, Sie müssen das Symbol selbst anzeigen durch Festlegen der <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> Eigenschaft. Dies ist erforderlich, wenn Sie Flexibilität in benutzerdefinierten sortieren möchten. Wenn Sie sortieren, z. B. die <xref:System.Windows.Forms.DataGridView> nach mehreren Spalten möchten Sie möglicherweise mehrere Sortiersymbole oder gar kein Sortiersymbol anzuzeigen.  
  
 Obwohl Sie programmgesteuert sortieren können ein <xref:System.Windows.Forms.DataGridView> nach einer beliebigen Spalte einige Spalten, z. B. Schaltflächenspalten, möglicherweise keine Werte, die sinnvoll sortiert werden können. Für diese Spalten ein <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> eigenschaftseinstellung <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> gibt an, dass es nie für die Sortierung, verwendet werden, daher keine Notwendigkeit zum Reservieren von Speicherplatz in der Kopfzeile für das Sortiersymbol besteht.  
  
 Wenn eine <xref:System.Windows.Forms.DataGridView> ist sortiert, können Sie bestimmen die Sortierspalte und die Sortierreihenfolge Überprüfung von Werten der <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> und <xref:System.Windows.Forms.DataGridView.SortOrder%2A> Eigenschaften. Diese Werte sind nach einem benutzerdefinierten Sortiervorgang ohne Bedeutung. Weitere Informationen zum benutzerdefinierten Sortieren finden Sie unter benutzerdefinierte Sortierung im Abschnitt weiter unten in diesem Thema.  
  
 Wenn ein <xref:System.Windows.Forms.DataGridView> Steuerelement mit gebundene und ungebundene Spalten sortiert wird, die Werte in den ungebundenen Spalten nicht automatisch beibehalten werden. Um diese Werte zu gewährleisten, müssen Sie den virtuellen Modus implementieren, durch Festlegen der <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft `true` und Behandeln von der <xref:System.Windows.Forms.DataGridView.CellValueNeeded> und <xref:System.Windows.Forms.DataGridView.CellValuePushed> Ereignisse. Weitere Informationen finden Sie unter [wie: Implementieren des virtuellen Modus im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md). Sortieren nach ungebundenen Spalten im gebundenen Modus wird nicht unterstützt.  
  
## <a name="programmatic-sorting"></a>Programmgesteuertes Sortieren  
 Sie sortieren können ein <xref:System.Windows.Forms.DataGridView> programmgesteuert durch Aufrufen seiner <xref:System.Windows.Forms.DataGridView.Sort%2A> Methode.  
  
 Die `Sort(DataGridViewColumn,ListSortDirection)` Überladung von der <xref:System.Windows.Forms.DataGridView.Sort%2A> -Methode übernimmt ein <xref:System.Windows.Forms.DataGridViewColumn> und ein <xref:System.ComponentModel.ListSortDirection> -Enumerationswert als Parameter. Diese Überladung ist hilfreich beim Sortieren nach Spalten mit Werten, die sinnvoll sortiert werden können, die aber nicht möchten, konfigurieren Sie für die automatische Sortierung. Wenn Sie diese Überladung aufrufen, und übergeben Sie eine Spalte mit einer <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> Eigenschaftswert <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>, die <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> und <xref:System.Windows.Forms.DataGridView.SortOrder%2A> Eigenschaften werden automatisch festgelegt und das entsprechende Sortiersymbol wird in der Kopfzeile der Spalte angezeigt.  
  
> [!NOTE]
>  Wenn die <xref:System.Windows.Forms.DataGridView> Steuerelement an eine externe Datenquelle gebunden ist, durch Festlegen der <xref:System.Windows.Forms.DataGridView.DataSource%2A> -Eigenschaft, die `Sort(DataGridViewColumn,ListSortDirection)` methodenüberladung funktioniert nicht für ungebundene Spalten. Darüber hinaus, wenn die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft `true`, rufen Sie diese Überladung nur bei gebundenen Spalten. Um zu bestimmen, ob eine Spalte datengebunden ist, überprüfen Sie die <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A> Eigenschaftswert. Sortieren von ungebundenen Spalten im gebundenen Modus wird nicht unterstützt.  
  
## <a name="custom-sorting"></a>Benutzerdefinierte Sortierung  
 Sie können anpassen, <xref:System.Windows.Forms.DataGridView> mithilfe der `Sort(IComparer)` Überladung von der <xref:System.Windows.Forms.DataGridView.Sort%2A> Methode oder durch das Behandeln der <xref:System.Windows.Forms.DataGridView.SortCompare> Ereignis.  
  
 Die `Sort(IComparer)` methodenüberladung akzeptiert eine Instanz einer Klasse, die implementiert die <xref:System.Collections.IComparer> -Schnittstelle als Parameter. Diese Überladung ist hilfreich, wenn Sie benutzerdefinierte Sortierung bereitstellen möchten; Wenn die Werte in einer Spalte nicht keine natürliche Sortierreihenfolge verfügen oder wenn die natürliche Sortierreihenfolge ist beispielsweise nicht geeignet. In diesem Fall können Sie keine automatische Sortierung, allerdings sollten Sie immer noch die Benutzer durch Klicken auf die Spaltenüberschriften sortieren. Sie können diese Überladung aufrufen, in einen Handler für das <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> -Ereignis, wenn Sie keine Spaltenheader zur Auswahl verwenden.  
  
> [!NOTE]
>  Die `Sort(IComparer)` methodenüberladung funktioniert nur, wenn die <xref:System.Windows.Forms.DataGridView> Steuerung nicht an eine externe Datenquelle gebunden ist und die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaftswert ist `false`. Zum Anpassen der Sortierung für Spalten, die an eine externe Datenquelle gebunden ist, müssen Sie die von der Datenquelle bereitgestellten Sortiervorgänge verwenden. Im virtuellen Modus müssen Sie eigene Sortieroperationen für ungebundene Spalten angeben.  
  
 Verwenden der `Sort(IComparer)` methodenüberladung, müssen Sie eine eigene Klasse, die implementiert erstellen die <xref:System.Collections.IComparer> Schnittstelle. Für diese Schnittstelle muss Ihre Klasse implementiert die <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType> Methode, zu dem die <xref:System.Windows.Forms.DataGridView> übergibt <xref:System.Windows.Forms.DataGridViewRow> Objekte als Eingabe, wenn die `Sort(IComparer)` -methodenüberladung aufgerufen wird. Mit dieser Option können Sie berechnen, die richtige Zeile Reihenfolge basierend auf den Werten in einer beliebigen Spalte.  
  
 Die `Sort(IComparer)` methodenüberladung wird nicht festgelegt. die <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> und <xref:System.Windows.Forms.DataGridView.SortOrder%2A> Eigenschaften, sodass immer festgelegt werden muss die <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> Eigenschaft, um das Sortiersymbol anzuzeigen.  
  
 Als Alternative zu der `Sort(IComparer)` methodenüberladung, bieten, da Sie benutzerdefinierte Sortierung durch die Implementierung eines Handlers für das <xref:System.Windows.Forms.DataGridView.SortCompare> Ereignis. Dieses Ereignis tritt auf, wenn Benutzer auf die Header der Spalten, die für die automatische Sortierung oder beim Aufrufen konfiguriert die `Sort(DataGridViewColumn,ListSortDirection)` Überladung von der <xref:System.Windows.Forms.DataGridView.Sort%2A> Methode. Das Ereignis tritt auf, für jedes Paar von Zeilen im Steuerelement, sodass Sie die richtige Reihenfolge berechnen.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.DataGridView.SortCompare> Ereignis tritt nicht auf bei der <xref:System.Windows.Forms.DataGridView.DataSource%2A> festgelegt wird oder wenn die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaftswert ist `true`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>  
 [Sortieren von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 [Vorgehensweise: Festlegen der Sortierungsmodi für Spalten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)  
 [Gewusst wie: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
