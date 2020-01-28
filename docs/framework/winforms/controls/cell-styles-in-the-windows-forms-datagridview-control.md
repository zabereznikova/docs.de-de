---
title: Zellstile im DataGridView-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: fe56033a5adbe7719c64695c8f9ebc4f3644fc65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746152"
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Zellstile im DataGridView-Steuerelement in Windows Forms
Jede Zelle im <xref:System.Windows.Forms.DataGridView> Steuerelement kann über einen eigenen Stil verfügen, z. b. Textformat, Hintergrundfarbe, Vordergrundfarbe und Schriftart. In der Regel verwenden mehrere Zellen jedoch bestimmte Stilmerkmale.  
  
 Gruppen von Zellen, die Stile gemeinsam verwenden, können alle Zellen in bestimmten Zeilen oder Spalten, alle Zellen, die bestimmte Werte enthalten, oder alle Zellen im Steuerelement enthalten. Da sich diese Gruppen überschneiden, kann jede Zelle ihre Formatierungsinformationen von mehr als einem Ort erhalten. Angenommen, Sie möchten, dass jede Zelle in einem <xref:System.Windows.Forms.DataGridView>-Steuerelement dieselbe Schriftart verwendet, aber nur Zellen in Währungs Spalten, um das Währungs Format zu verwenden, und nur Währungs Zellen mit negativen Zahlen, um eine rote Vordergrundfarbe zu verwenden.  
  
## <a name="the-datagridviewcellstyle-class"></a>Die DataGridViewCellStyle-Klasse  
 Die <xref:System.Windows.Forms.DataGridViewCellStyle>-Klasse enthält die folgenden Eigenschaften, die sich auf den visuellen Stil beziehen:  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Diese Klasse enthält auch die folgenden Eigenschaften im Zusammenhang mit der Formatierung:  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Weitere Informationen zu diesen Eigenschaften und anderen Eigenschaften im Zellstil finden Sie in der <xref:System.Windows.Forms.DataGridViewCellStyle> Referenz Dokumentation und in den Themen, die im Abschnitt Siehe auch unten aufgeführt sind.  
  
## <a name="using-datagridviewcellstyle-objects"></a>Verwenden von DataGridViewCellStyle-Objekten  
 Sie können <xref:System.Windows.Forms.DataGridViewCellStyle> Objekte aus verschiedenen Eigenschaften der Klassen "<xref:System.Windows.Forms.DataGridView>", "<xref:System.Windows.Forms.DataGridViewColumn>", "<xref:System.Windows.Forms.DataGridViewRow>" und "<xref:System.Windows.Forms.DataGridViewCell>" und deren abgeleiteter Klassen abrufen. Wenn eine dieser Eigenschaften noch nicht festgelegt wurde, wird durch das Abrufen ihres Werts ein neues <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekt erstellt. Sie können auch Ihre eigenen <xref:System.Windows.Forms.DataGridViewCellStyle> Objekte instanziieren und diesen Eigenschaften zuweisen.  
  
 Sie können unnötige Duplizierung von Formatinformationen vermeiden, indem Sie <xref:System.Windows.Forms.DataGridViewCellStyle> Objekte für mehrere <xref:System.Windows.Forms.DataGridView> Elemente freigeben. Da die auf der Steuerelement-, Spalten-und Zeilenebene festgelegten Stile durch die einzelnen Ebenen auf die Zellen Ebene gefiltert werden, können Sie auch eine duplikatduplizierung vermeiden, indem Sie nur die Stileigenschaften auf jeder Ebene festlegen, die von den oben genannten Ebenen abweicht. Dies wird im folgenden Abschnitt im Abschnitt Format Vererbung ausführlicher beschrieben.  
  
 In der folgenden Tabelle werden die primären Eigenschaften aufgelistet, die <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekte erhalten oder festgelegt werden.  
  
|Die Eigenschaften-|Klassen|Beschreibung|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>-, <xref:System.Windows.Forms.DataGridViewColumn>-, <xref:System.Windows.Forms.DataGridViewRow>-und abgeleitete Klassen|Ruft Standardformate ab, die von allen Zellen im gesamten Steuerelement (einschließlich der Header Zellen), in einer Spalte oder in einer Zeile verwendet werden, oder legt diese fest.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ruft Standard Zellstile ab, die von allen Zeilen im-Steuerelement verwendet werden, oder legt diese Dies schließt keine Header Zellen ein.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ruft die Standardzellen Formate ab, die von wechselnden Zeilen im-Steuerelement verwendet werden. Wird verwendet, um einen Ledger-ähnlichen Effekt zu erstellen.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ruft die Standardzellen Stile ab, die von den Zeilen Headern des Steuer Elements verwendet werden Wird vom aktuellen Design überschrieben, wenn visuelle Stile aktiviert sind.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ruft die Standardzellen Formate ab, die von den Spalten Headern des Steuer Elements verwendet werden. Wird vom aktuellen Design überschrieben, wenn visuelle Stile aktiviert sind.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> und abgeleitete Klassen|Ruft die auf Zellen Ebene angegebenen Stile ab oder legt Sie fest. Diese Stile überschreiben diejenigen, die von höheren Ebenen geerbt wurden.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>-, <xref:System.Windows.Forms.DataGridViewRow>-, <xref:System.Windows.Forms.DataGridViewColumn>-und abgeleitete Klassen|Ruft alle Formate ab, die derzeit auf die Zelle, Zeile oder Spalte angewendet werden, einschließlich der aus höheren Ebenen geerbten Stile.|  
  
 Wie bereits erwähnt, instanziiert der Wert einer Style-Eigenschaft automatisch ein neues <xref:System.Windows.Forms.DataGridViewCellStyle> Objekt, wenn die Eigenschaft nicht zuvor festgelegt wurde. Um zu vermeiden, dass diese Objekte unnötig erstellt werden, verfügen die Zeilen-und Spalten Klassen über eine <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A>-Eigenschaft, die Sie überprüfen können, um zu bestimmen, ob die <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> Eigenschaft festgelegt Ebenso verfügen die Zell Klassen über eine <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A>-Eigenschaft, die angibt, ob die <xref:System.Windows.Forms.DataGridViewCell.Style%2A>-Eigenschaft festgelegt wurde.  
  
 Jede der Stileigenschaften verfügt über ein entsprechendes *propertyName* -`Changed` Ereignis für das <xref:System.Windows.Forms.DataGridView>-Steuerelement. Für Zeilen-, Spalten-und Zell Eigenschaften beginnt der Name des Ereignisses mit "`Row`", "`Column`" oder "`Cell`" (z. b. <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>). Jedes dieser Ereignisse tritt auf, wenn die entsprechende Style-Eigenschaft auf ein anderes <xref:System.Windows.Forms.DataGridViewCellStyle> Objekt festgelegt ist. Diese Ereignisse treten nicht auf, wenn Sie ein <xref:System.Windows.Forms.DataGridViewCellStyle> Objekt aus einer Stil Eigenschaft abrufen und deren Eigenschaftswerte ändern. Um auf Änderungen an den Zellen Stil Objekten zu reagieren, behandeln Sie das <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged>-Ereignis.  
  
## <a name="style-inheritance"></a>Stilvererbung  
 Jedes <xref:System.Windows.Forms.DataGridViewCell> erhält seine Darstellung aus seiner <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>-Eigenschaft. Das von dieser Eigenschaft zurückgegebene <xref:System.Windows.Forms.DataGridViewCellStyle> Objekt erbt seine Werte aus einer Hierarchie von Eigenschaften vom Typ <xref:System.Windows.Forms.DataGridViewCellStyle>. Diese Eigenschaften sind unten in der Reihenfolge aufgelistet, in der der <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> für nicht-Header Zellen seine Werte erhält.  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (nur für Zellen in Zeilen mit ungeraden Indexnummern)  
  
4. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Für Zeilen-und Spaltenheader Zellen wird die <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>-Eigenschaft durch Werte aus der folgenden Liste von Quell Eigenschaften in der angegebenen Reihenfolge aufgefüllt.  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> oder <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Dieser Prozess wird anhand des folgenden Diagramms veranschaulicht.  
  
 ![Eigenschaften des DataGridViewCellStyle-Datentyps](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-inheritance-diagram.gif "DataGridViewCells-Vererbungs Diagramm")  
  
 Sie können auch auf die Stile zugreifen, die von bestimmten Zeilen und Spalten geerbt wurden. Die Spalte <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A>-Eigenschaft erbt ihre Werte von den folgenden Eigenschaften.  
  
1. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Die Zeile <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A>-Eigenschaft erbt ihre Werte von den folgenden Eigenschaften.  
  
1. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (nur für Zellen in Zeilen mit ungeraden Indexnummern)  
  
3. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Für jede Eigenschaft in einem <xref:System.Windows.Forms.DataGridViewCellStyle> Objekt, das von einer `InheritedStyle`-Eigenschaft zurückgegeben wird, wird der Eigenschafts Wert aus dem ersten Zellstil in der entsprechenden Liste abgerufen, bei dem die entsprechende-Eigenschaft auf einen anderen Wert als die Standardwerte der <xref:System.Windows.Forms.DataGridViewCellStyle>-Klasse festgelegt ist.  
  
 In der folgenden Tabelle wird veranschaulicht, wie der <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>-Eigenschafts Wert für eine Beispiel Zelle von der enthaltenden Spalte geerbt wird.  
  
|Eigenschaft vom Typ `DataGridViewCellStyle`|Beispiel `ForeColor` Wert für abgerufene Objekte|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 In diesem Fall ist der <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> Wert aus der Zeile der Zelle der erste reale Wert in der Liste. Dies wird der <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>-Eigenschafts Wert des <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>der Zelle.  
  
 Im folgenden Diagramm wird veranschaulicht, wie verschiedene <xref:System.Windows.Forms.DataGridViewCellStyle> Eigenschaften ihre Werte von unterschiedlichen Stellen erben können.  
  
 ![Vererbung von DataGridView-Eigenschafts&#45;Werten](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-value-inheritance-diagram.gif "Vererbungs Diagramm für dataGridViewCells-Werte")  
  
 Durch die Nutzung der Stil Vererbung können Sie geeignete Stile für das gesamte Steuerelement bereitstellen, ohne die gleichen Informationen an mehreren Stellen angeben zu müssen.  
  
 Obwohl Header Zellen wie beschrieben an der Stil Vererbung beteiligt sind, verfügen die Objekte, die von den Eigenschaften <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> und <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> der <xref:System.Windows.Forms.DataGridView> Steuerelemente zurückgegeben werden, über anfängliche Eigenschaftswerte, die die Eigenschaftswerte des Objekts überschreiben, das von der <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>-Eigenschaft Wenn Sie möchten, dass die Eigenschaften für das Objekt, das von der <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>-Eigenschaft zurückgegeben wird, auf Zeilen-und Spaltenüberschriften angewendet werden, müssen Sie die entsprechenden Eigenschaften der Objekte, die von den <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> und <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> Eigenschaften zurückgegeben werden, auf die für die <xref:System.Windows.Forms.DataGridViewCellStyle> Klasse festgelegten Standardwerte  
  
> [!NOTE]
> Wenn visuelle Stile aktiviert sind, werden die Zeilen-und Spaltenüberschriften (außer dem <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) automatisch durch das aktuelle Design formatiert, wobei alle von diesen Eigenschaften angegebenen Stile überschrieben werden.  
  
 Die Typen <xref:System.Windows.Forms.DataGridViewButtonColumn>, <xref:System.Windows.Forms.DataGridViewImageColumn>und <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> initialisieren auch einige Werte des Objekts, das von der Spalte <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>-Eigenschaft zurückgegeben wird. Weitere Informationen finden Sie in der Referenz Dokumentation für diese Typen.  
  
## <a name="setting-styles-dynamically"></a>Dynamisches Festlegen von Stilen  
 Implementieren Sie zum Anpassen der Stile von Zellen mit bestimmten Werten einen Handler für das <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>-Ereignis. Handler für dieses Ereignis empfangen ein Argument des <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> Typs. Dieses Objekt enthält Eigenschaften, mit denen Sie den Wert der zu formatierenden Zelle sowie deren Position im <xref:System.Windows.Forms.DataGridView> Steuerelement bestimmen können. Dieses Objekt enthält auch eine <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> Eigenschaft, die mit dem Wert der <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>-Eigenschaft der zu formatierenden Zelle initialisiert wird. Sie können die Eigenschaften des Zellstils ändern, um Stil Informationen anzugeben, die für den Zellwert und den Speicherort geeignet sind.  
  
> [!NOTE]
> Das <xref:System.Windows.Forms.DataGridView.RowPrePaint>-Ereignis und das <xref:System.Windows.Forms.DataGridView.RowPostPaint>-Ereignis erhalten ebenfalls ein <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekt in den Ereignisdaten, aber in diesem Fall ist es eine Kopie der Zeilen <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A>-Eigenschaft für schreibgeschützte Zwecke, und Änderungen an der-Methode wirken sich nicht auf das-Steuerelement aus.  
  
 Sie können auch die Stile einzelner Zellen dynamisch ändern, als Reaktion auf Ereignisse wie z. b. das <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType>-Ereignis und das <xref:System.Windows.Forms.DataGridView.CellMouseLeave>-Ereignis. Beispielsweise könnten Sie in einem Handler für das <xref:System.Windows.Forms.DataGridView.CellMouseEnter>-Ereignis den aktuellen Wert der Zellen Hintergrundfarbe (abgerufen durch die <xref:System.Windows.Forms.DataGridViewCell.Style%2A>-Eigenschaft der Zelle) speichern und dann eine neue Farbe festlegen, die die Zelle hervorhebt, wenn der Mauszeiger darüber bewegt wird. In einem Handler für das <xref:System.Windows.Forms.DataGridView.CellMouseLeave>-Ereignis können Sie dann die Hintergrundfarbe für den ursprünglichen Wert wiederherstellen.  
  
> [!NOTE]
> Das Zwischenspeichern der in der <xref:System.Windows.Forms.DataGridViewCell.Style%2A>-Eigenschaft der Zelle gespeicherten Werte ist wichtig, unabhängig davon, ob ein bestimmter Stilwert festgelegt ist. Wenn Sie eine Formatvorlage temporär ersetzen, wird durch die Wiederherstellung in den ursprünglichen Zustand "nicht festgelegt" sichergestellt, dass die Zelle zurück wechselt, um die Stil Einstellung von einer höheren Ebene zu erben. Wenn Sie den tatsächlichen Stil für eine Zelle ermitteln müssen, unabhängig davon, ob der Stil geerbt wird, verwenden Sie die <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>-Eigenschaft der Zelle.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Gewusst wie: Festlegen von Standardzellenformaten für das DataGridView-Steuerelement in Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Datenformatierung im DataGridView-Steuerelement in Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
