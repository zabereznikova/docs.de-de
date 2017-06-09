---
title: "Spaltenssortiermodi im DataGridView-Steuerelement von Windows Forms | Microsoft Docs"
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
  - "Datenblätter, Sortiermodi"
  - "DataGridView-Steuerelement [Windows Forms], Sortiermodus"
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Spaltenssortiermodi im DataGridView-Steuerelement von Windows Forms
<xref:System.Windows.Forms.DataGridView>\-Spalten verfügen über drei Sortiermodi.  Der Sortiermodus für die jeweiligen Spalten wird durch die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>\-Eigenschaft der Spalte bestimmt, die auf einen der folgenden Werte für die <xref:System.Windows.Forms.DataGridViewColumnSortMode>\-Enumeration festgelegt werden kann.  
  
|`DataGridViewColumnSortMode`\-Wert|Beschreibung|  
|----------------------------------------|------------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode>|Die Vorgabe für Textfeldspalten.  Sofern keine Spaltenheader zur Auswahl verwendet werden, wird durch Klicken auf den Spaltenheader die <xref:System.Windows.Forms.DataGridView> automatisch nach dieser Spalte sortiert und die Sortierreihenfolge durch ein Symbol angezeigt.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode>|Die Vorgabe für Nicht\-Textfeldspalten.  Sie können diese Spalte zwar programmgesteuert sortieren, da sie jedoch nicht zum Sortieren vorgesehen ist, ist kein Platz für das Sortiersymbol reserviert.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode>|Sie können diese Spalte programmgesteuert sortieren, wobei Platz für das Sortiersymbol reserviert ist.|  
  
 Möglicherweise möchten Sie den Sortiermodus für eine Spalte ändern, die standardmäßig auf <xref:System.Windows.Forms.DataGridViewColumnSortMode> festgelegt ist, wenn diese Spalte Werte enthält, die sinnvoll sortiert werden können.  Wenn Sie beispielsweise über eine Datenbankspalte mit Zahlen verfügen, die den Elementzustand darstellen, können Sie diese Zahlen als entsprechende Symbole anzeigen, indem Sie eine Bildspalte an die Datenbankspalte binden.  Anschließend können Sie die numerischen Zellenwerte in Bildanzeigewerte in einem Handler für das <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName>\-Ereignis ändern.  In diesem Fall können die Benutzer die Spalte sortieren, wenn Sie die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewColumnSortMode> festlegen.  Durch das automatische Sortieren können die Benutzer Elemente mit demselben Zustand gruppieren, auch wenn die den Zahlen entsprechenden Zustände keine natürliche Abfolge aufweisen.  Ein weiteres Beispiel, bei dem das automatische Sortieren zum Gruppieren von Elementen mit demselben Zustand hilfreich ist, sind Kontrollkästchenspalten.  
  
 Sie können eine <xref:System.Windows.Forms.DataGridView> programmgesteuert anhand der Werte in einer oder mehreren Spalten sortieren, unabhängig davon, welcher <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> eingestellt ist.  Das programmgesteuerte Sortieren bietet sich an, wenn Sie Ihre eigene Benutzeroberfläche \(UI\) zum Sortieren bereitstellen oder benutzerdefiniertes Sortieren implementieren möchten.  Eine eigene Sortierbenutzeroberfläche ist beispielsweise hilfreich, wenn Sie über den <xref:System.Windows.Forms.DataGridView>\-Auswahlmodus die Spaltenheaderauswahl aktivieren.  Auch wenn die Spaltenheader nicht zum Sortieren verwendet werden können, soll in den Headern dennoch das entsprechende Sortiersymbol angezeigt werden. In diesem Fall würden Sie die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewColumnSortMode> festlegen.  
  
 In Spalten, für die ein programmgesteuerter Sortiermodus festgelegt ist, wird nicht automatisch ein Sortiersymbol angezeigt.  Für diese Spalten müssen Sie das Symbol selbst anzeigen, indem Sie die <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=fullName>\-Eigenschaft festlegen.  Dies ist erforderlich, wenn Sie die benutzerdefinierte Sortierung flexibel anpassen möchten.  Wenn Sie beispielsweise die <xref:System.Windows.Forms.DataGridView> nach mehreren Spalten sortieren möchten, ist es unter Umständen angebracht, mehrere Sortiersymbole oder gar kein Sortiersymbol anzuzeigen.  
  
 Auch wenn Sie eine <xref:System.Windows.Forms.DataGridView> programmgesteuert nach jeder beliebigen Spalte sortieren können, enthalten einige Spalten, z. B. Schaltflächenspalten, möglicherweise keine Werte, die sinnvoll sortiert werden können.  Bei diesen Spalten wird durch die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>\-Eigenschafteneinstellung <xref:System.Windows.Forms.DataGridViewColumnSortMode> angegeben, dass sie grundsätzlich nicht zum Sortieren verwendet werden, d. h., im Header muss kein Platz für das Sortiersymbol reserviert werden.  
  
 Wenn ein <xref:System.Windows.Forms.DataGridView> sortiert wird, können Sie sowohl die Sortierspalte als auch die Sortierreihenfolge bestimmen, indem Sie die Werte der <xref:System.Windows.Forms.DataGridView.SortedColumn%2A>\-Eigenschaft und der <xref:System.Windows.Forms.DataGridView.SortOrder%2A>\-Eigenschaft festlegen.  Diese Werte sind nach einem benutzerdefinierten Sortiervorgang nicht mehr von Bedeutung.  Weitere Informationen über benutzerdefiniertes Sortieren finden Sie weiter unten in diesem Thema unter "Benutzerdefiniertes Sortieren".  
  
 Wenn ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement, das sowohl gebundene als auch ungebundene Spalten enthält, sortiert wird, bleiben die Werte in den ungebundenen Spalten nicht automatisch erhalten.  Um diese Werte zu erhalten, müssen Sie den virtuellen Modus implementieren, indem Sie die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>\-Eigenschaft auf `true` festlegen und das <xref:System.Windows.Forms.DataGridView.CellValueNeeded>\-Ereignis und das <xref:System.Windows.Forms.DataGridView.CellValuePushed>\-Ereignis behandeln.  Weitere Informationen finden Sie unter [Gewusst wie: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  Das Sortieren nach ungebundenen Spalten im Gebunden\-Modus wird nicht unterstützt.  
  
## Programmgesteuertes Sortieren  
 Sie können eine <xref:System.Windows.Forms.DataGridView> programmgesteuert sortieren, indem Sie ihre <xref:System.Windows.Forms.DataGridView.Sort%2A>\-Methode aufrufen.  
  
 Die `Sort(DataGridViewColumn,ListSortDirection)`\-Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>\-Methode verwendet einen <xref:System.Windows.Forms.DataGridViewColumn>\-Enumerationswert und einen <xref:System.ComponentModel.ListSortDirection>\-Enumerationswert als Parameter.  Diese Überladung ist hilfreich, wenn Sie nach Spalten mit Werten sortieren, die sinnvoll sortiert werden können, die Sie jedoch nicht für das automatische Sortieren konfigurieren möchten.  Wenn Sie diese Überladung aufrufen und in einer Spalte mit dem <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>\-Eigenschaftswert <xref:System.Windows.Forms.DataGridViewColumnSortMode?displayProperty=fullName> übergeben, werden die <xref:System.Windows.Forms.DataGridView.SortedColumn%2A>\-Eigenschaft und die <xref:System.Windows.Forms.DataGridView.SortOrder%2A>\-Eigenschaft automatisch festgelegt, und das entsprechende Sortiersymbol wird im Spaltenheader angezeigt.  
  
> [!NOTE]
>  Wenn das <xref:System.Windows.Forms.DataGridView>\-Steuerelement durch Festlegen der <xref:System.Windows.Forms.DataGridView.DataSource%2A>\-Eigenschaft an eine externe Datenquelle gebunden ist, kann die überladene `Sort(DataGridViewColumn,ListSortDirection)`\-Methode nicht für ungebundene Spalten verwendet werden.  Wenn die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>\-Eigenschaft auf `true` festgelegt ist, können Sie diese Überladung außerdem nur für gebundene Spalten aufrufen.  Um zu bestimmen, ob eine Spalte datengebunden ist, überprüfen Sie den <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A>\-Eigenschaftswert.  Das Sortieren von ungebundenen Spalten im gebundenen Modus wird nicht unterstützt.  
  
## Benutzerdefiniertes Sortieren  
 Sie können <xref:System.Windows.Forms.DataGridView> anpassen, indem Sie die `Sort(IComparer)`\-Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>\-Methode verwenden oder das <xref:System.Windows.Forms.DataGridView.SortCompare>\-Ereignis behandeln.  
  
 Die überladene `Sort(IComparer)`\-Methode verwendet eine Instanz einer Klasse, die die <xref:System.Collections.IComparer>\-Schnittstelle als Parameter implementiert.  Diese Überladung ist hilfreich, wenn Sie benutzerdefiniertes Sortieren bereitstellen, z. B. wenn die Werte in einer Spalte keine natürliche Sortierreihenfolge aufweisen oder die natürliche Sortierreihenfolge ungeeignet ist.  In diesem Fall können Sie keine automatische Sortierung verwenden, möchten es den Benutzern aber möglicherweise trotzdem ermöglichen, durch Klicken auf die Spaltenheader zu sortieren.  Sie können diese Überladung in einem Handler für das <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick>\-Ereignis aufrufen, wenn Sie keine Spaltenheader zur Auswahl verwenden.  
  
> [!NOTE]
>  Die überladene `Sort(IComparer)`\-Methode funktioniert nur, wenn das <xref:System.Windows.Forms.DataGridView>\-Steuerelement nicht an eine externe Datenquelle gebunden ist und der <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>\-Eigenschaftswert `false` lautet.  Zum Anpassen der Sortierung für Spalten, die an eine externe Datenquelle gebunden sind, müssen Sie die von der Datenquelle bereitgestellten Sortiervorgänge verwenden.  Im virtuellen Modus müssen Sie Ihre eigenen Sortiervorgänge für ungebundene Spalten bereitstellen.  
  
 Zur Verwendung der überladenen `Sort(IComparer)`\-Methode müssen Sie Ihre eigene Klasse erstellen, die die <xref:System.Collections.IComparer>\-Schnittstelle implementiert.  Für diese Schnittstelle ist es erforderlich, dass Sie die <xref:System.Collections.IComparer.Compare%2A?displayProperty=fullName>\-Methode implementieren, an die <xref:System.Windows.Forms.DataGridViewRow>\-Objekte von der <xref:System.Windows.Forms.DataGridView> als Eingabe übergeben werden, wenn die überladene `Sort(IComparer)`\-Methode aufgerufen wird.  Dadurch können Sie die richtige Zeilensortierung anhand der Werte in den Spalten berechnen.  
  
 Die überladene `Sort(IComparer)`\-Methode legt die <xref:System.Windows.Forms.DataGridView.SortedColumn%2A>\-Eigenschaft und die <xref:System.Windows.Forms.DataGridView.SortOrder%2A>\-Eigenschaft nicht fest. Daher müssen Sie stets die <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=fullName>\-Eigenschaft festlegen, damit das Sortiersymbol angezeigt wird.  
  
 Alternativ zur überladenen `Sort(IComparer)`\-Methode können Sie benutzerdefiniertes Sortieren bereitstellen, indem Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.SortCompare>\-Ereignis implementieren.  Dieses Ereignis tritt ein, wenn Benutzer auf die Header von Spalten klicken, die für automatisches Sortieren konfiguriert wurden, oder wenn Sie die `Sort(DataGridViewColumn,ListSortDirection)`\-Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>\-Methode aufrufen.  Da das Ereignis für jedes Zeilenpaar im Steuerelement auftritt, können Sie die richtige Reihenfolge berechnen.  
  
> [!NOTE]
>  Das <xref:System.Windows.Forms.DataGridView.SortCompare>\-Ereignis tritt nicht ein, wenn die <xref:System.Windows.Forms.DataGridView.DataSource%2A>\-Eigenschaft festgelegt ist oder der <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>\-Eigenschaftswert `true` lautet.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=fullName>   
 [Sortieren von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Festlegen der Sortierungsmodi für Spalten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)   
 [Gewusst wie: Anpassen der Sortierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)