---
title: Zellstile im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: 41794c5ecadbcdc0b38c7c73afc7c010a4ea6989
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300020"
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Zellstile im DataGridView-Steuerelement in Windows Forms
Jede Zelle innerhalb der <xref:System.Windows.Forms.DataGridView> Steuerelement kann seinen eigenen Stil, wie z. B. Text-Format, Hintergrundfarbe, Vordergrundfarbe und Schriftart haben. In der Regel werden jedoch mehrere Zellen Stilmerkmale.  
  
 Gruppen von Zellen, die Stile freigeben, können alle Zellen innerhalb bestimmter Zeilen oder Spalten, alle Zellen mit bestimmten Werten oder alle Zellen im Steuerelement enthalten. Da diese Gruppen überlappen, kann jede Zelle ihre Stilinformationen aus mehr als einem Ort abrufen. Sie können beispielsweise jede Zelle einer <xref:System.Windows.Forms.DataGridView> Steuerelement, das die Schriftart, aber nur Zellen in Währungsspalten das Währungsformat aus, und nur Währungszellen mit negativen Zahlen zu verwenden, um eine rote Vordergrundfarbe verwenden.  
  
## <a name="the-datagridviewcellstyle-class"></a>Die DataGridViewCellStyle-Klasse  
 Die <xref:System.Windows.Forms.DataGridViewCellStyle> -Klasse enthält die folgenden Eigenschaften für den visuellen Stil:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Diese Klasse enthält auch die folgenden Eigenschaften im Zusammenhang mit der Formatierung:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Weitere Informationen über diese Eigenschaften und andere Zellstil Eigenschaften finden Sie unter den <xref:System.Windows.Forms.DataGridViewCellStyle> Referenzdokumentation und in den Themen aufgeführt, klicken Sie im Abschnitt Siehe auch weiter unten.  
  
## <a name="using-datagridviewcellstyle-objects"></a>Verwenden von DataGridViewCellStyle-Objekten  
 Können Sie abrufen <xref:System.Windows.Forms.DataGridViewCellStyle> Objekte aus verschiedenen Eigenschaften der <xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>, und <xref:System.Windows.Forms.DataGridViewCell> Klassen und ihrer abgeleiteten Klassen. Wenn eine dieser Eigenschaften noch nicht festgelegt wurde, der Wert abgerufen wird erstellt ein neues <xref:System.Windows.Forms.DataGridViewCellStyle> Objekt. Sie können auch instanziieren eigene <xref:System.Windows.Forms.DataGridViewCellStyle> -Objekte und weisen sie diese Eigenschaften.  
  
 Sie können unnötige Verdoppelungen von Formatinformationen vermeiden, indem Sie die Freigabe <xref:System.Windows.Forms.DataGridViewCellStyle> auf mehrere Objekte <xref:System.Windows.Forms.DataGridView> Elemente. Da die Stile auf das Steuerelement, Spalte und Ebenen Zeilenfilter nach unten durch die einzelnen auf die Zellenebene festgelegt wird, können Sie auch Zellebene vermeiden, durch Festlegen der nur die Style-Eigenschaften auf jeder Ebene, die von den oben genannten Ebenen unterscheiden. Dies wird ausführlicher im Abschnitt Stilvererbung beschrieben, die folgt.  
  
 Die folgende Tabelle enthält die primären Eigenschaften, die abgerufen oder festgelegt <xref:System.Windows.Forms.DataGridViewCellStyle> Objekte.  
  
|Eigenschaft|Klassen|Beschreibung|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>, und abgeleitete Klassen|Übernimmt oder bestimmt die Standardstile, die von der alle Zellen in das gesamte Steuerelement (einschließlich der Headerzellen) in einer Spalte oder in einer Zeile verwendet.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Übernimmt oder bestimmt die standardmäßigen Zellenstilen, die von der alle Zeilen im Steuerelement verwendet. Dies schließt nicht die Headerzellen.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Übernimmt oder bestimmt die standardmäßigen Zellenstilen von abwechselnden Zeilen im Steuerelement verwendet. Verwendet, um einen Ledger-ähnlichen Effekt zu erstellen.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Übernimmt oder bestimmt die standardmäßigen Zellenstilen von Zeilenheader des Steuerelements verwendet. Durch das aktuelle Design überschrieben, wenn visuelle Stile aktiviert sind.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Übernimmt oder bestimmt die standardmäßigen Zellenstilen von Spaltenüberschriften des Steuerelements verwendet. Durch das aktuelle Design überschrieben, wenn visuelle Stile aktiviert sind.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> und die abgeleiteten Klassen|Übernimmt oder bestimmt die Stile, die auf Zellenebene. Diese Formate haben Vorrang von höheren Bereichsebenen geerbt.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewRow>, <xref:System.Windows.Forms.DataGridViewColumn>, und abgeleitete Klassen|Ruft alle derzeit auf die Zelle, Zeile oder Spalte an, einschließlich Stile, die von höheren Bereichsebenen geerbt angewendeten Stile ab.|  
  
 Wie bereits erwähnt, Abrufen des Werts einer Stileigenschaft automatisch instanziiert ein neues <xref:System.Windows.Forms.DataGridViewCellStyle> Objekt, wenn die Eigenschaft nicht zuvor festgelegt wurde. Um zu vermeiden, diese Objekte nicht unnötig erstellt, die Zeilen- und Klassen verfügen über eine <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> -Eigenschaft, die Sie überprüfen können, um zu bestimmen, ob die <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> -Eigenschaft festgelegt wurde. Auf ähnliche Weise die Zellenklassen verfügen über eine <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> Eigenschaft, die angibt, ob die <xref:System.Windows.Forms.DataGridViewCell.Style%2A> -Eigenschaft festgelegt wurde.  
  
 Jede der Eigenschaften der verfügt über eine entsprechende *PropertyName* `Changed` Ereignis auf der <xref:System.Windows.Forms.DataGridView> Steuerelement. Für die Zeilen-, Spalten- und Zelleigenschaften, der der Namen des Ereignisses beginnt mit "`Row`","`Column`", oder "`Cell`" (z. B. <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>). Jedes dieser Ereignisse tritt auf, wenn die entsprechende Style-Eigenschaft, auf einen anderen festgelegt ist <xref:System.Windows.Forms.DataGridViewCellStyle> Objekt. Diese Ereignisse treten nicht beim Abrufen einer <xref:System.Windows.Forms.DataGridViewCellStyle> -Objekt aus einem Style-Eigenschaft, und ändern Sie die Eigenschaftswerte. Um auf Änderungen an den die Zelle stilobjekte selbst zu reagieren, behandeln die <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged> Ereignis.  
  
## <a name="style-inheritance"></a>Stilvererbung  
 Jede <xref:System.Windows.Forms.DataGridViewCell> ruft seine Darstellung von dessen <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> Eigenschaft. Die <xref:System.Windows.Forms.DataGridViewCellStyle> von dieser Eigenschaft zurückgegebene Objekt erbt die Werte aus einer Hierarchie von Eigenschaften des Typs <xref:System.Windows.Forms.DataGridViewCellStyle>. Diese Eigenschaften sind unten aufgeführt, in der Reihenfolge, in dem die <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> für nicht-Headerzellen erhält seine Werte.  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (nur für Zellen in Zeilen mit einer ungeraden Anzahl von Index)  
  
4. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Für Zeilen- und Spaltenheaderzellen der <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> Eigenschaft wird durch die Werte in der folgenden Liste von Datenquelleneigenschaften in der angegebenen Reihenfolge aufgefüllt.  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> oder <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Das folgende Diagramm veranschaulicht diesen Prozess.  
  
 ![Eigenschaften des DataGridViewCellStyle-Typs](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-inheritance-diagram.gif "DataGridViewCells-Diagramm für Vererbung")  
  
 Sie können auch die Stile, die von bestimmten Zeilen und Spalten geerbt zugreifen. Die Spalte <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> -Eigenschaft erbt seine Werte aus den folgenden Eigenschaften.  
  
1. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Die Zeile <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> -Eigenschaft erbt seine Werte aus den folgenden Eigenschaften.  
  
1. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (nur für Zellen in Zeilen mit einer ungeraden Anzahl von Index)  
  
3. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Für jede Eigenschaft in eine <xref:System.Windows.Forms.DataGridViewCellStyle> zurückgegebenes Objekt ein `InheritedStyle` -Eigenschaft den Wert der Eigenschaft aus einer ersten Zellstil in der entsprechenden Liste aus, die die entsprechende Eigenschaft auf einen Wert festgelegt als die <xref:System.Windows.Forms.DataGridViewCellStyle> -Klasse automatisch.  
  
 In der folgende Tabelle wird veranschaulicht, wie die <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> Eigenschaftswert für eine Beispielzelle wird von der enthaltenden Spalte geerbt.  
  
|Eigenschaft des Typs `DataGridViewCellStyle`|Beispiel `ForeColor` Wert für das abgerufene Objekt|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 In diesem Fall die <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> Wert aus der Zeile ist der erste echten Wert in der Liste. Dies ist die <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> -Eigenschaftswert der Zelle <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>.  
  
 Im folgende Diagramm wird veranschaulicht, wie verschiedene <xref:System.Windows.Forms.DataGridViewCellStyle> Eigenschaften ihre Werte aus unterschiedlichen Quellen erben können.  
  
 ![DataGridView-Eigenschaft&#45;Wert Vererbung](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-value-inheritance-diagram.gif "DataGridViewCells-Wert-Diagramm für Vererbung")  
  
 Durch nutzen die Vererbung von Stilen, können Sie die entsprechenden Stile für das gesamte Steuerelement bereitstellen, ohne die gleiche Informationen an mehreren Orten angeben zu müssen.  
  
 Obwohl Headerzellen an der stilvererbung beteiligt, wie beschrieben, die Objekte zurückgegeben, durch die <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> und <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> Eigenschaften der <xref:System.Windows.Forms.DataGridView> Kontrolle haben die anfänglichen Eigenschaftswerte, die die Eigenschaftswerte des Objekts zurückgegeben, die durch Überschreiben die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> Eigenschaft. Wenn Sie die Eigenschaften für das zurückgegebene Objekt festgelegt werden soll die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> Eigenschaft zuweisen, Zeilen- und Spaltenüberschriften, müssen Sie die entsprechenden Eigenschaften der Objekte zurückgegeben werden, durch Festlegen der <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> und <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> Eigenschaften auf die Standardwerte angegeben für die <xref:System.Windows.Forms.DataGridViewCellStyle> Klasse.  
  
> [!NOTE]
>  Wenn visuelle Stile aktiviert sind, die Zeilen- und Spaltenüberschriften (mit Ausnahme der <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) werden automatisch angewendet, das das aktuelle Design, alle Formatvorlagen, die anhand dieser Eigenschaften angegeben.  
  
 Die <xref:System.Windows.Forms.DataGridViewButtonColumn>, <xref:System.Windows.Forms.DataGridViewImageColumn>, und <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> Typen initialisieren auch einige Werte des Objekts zurückgegeben, die von der Spalte <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> Eigenschaft. Weitere Informationen finden Sie in der Referenzdokumentation für diese Typen.  
  
## <a name="setting-styles-dynamically"></a>Dynamisches Festlegen von Stilen  
 Implementieren Sie zum Anpassen der Stile eines Zellen mit bestimmten Werten ein Handlers für die <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> Ereignis. Handler für dieses Ereignis empfängt ein Argument der <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> Typ. Dieses Objekt enthält Eigenschaften, mit denen Sie den Wert des zusammen mit seiner Position im formatierten Zelle bestimmen die <xref:System.Windows.Forms.DataGridView> Steuerelement. Dieses Objekt enthält auch eine <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> -Eigenschaft, die auf den Wert der initialisiert wird die <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> -Eigenschaft der Zelle, der formatiert wird. Sie können die Eigenschaften für den Zellstil zum Angeben von Informationen zum Schriftschnitt für den Wert der Zelle und den Speicherort ändern.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.DataGridView.RowPrePaint> und <xref:System.Windows.Forms.DataGridView.RowPostPaint> empfangen von Ereignissen auch eine <xref:System.Windows.Forms.DataGridViewCellStyle> Objektdaten in der ereignismeldung in Großschreibung, es ist allerdings eine Kopie der Zeile <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> -Eigenschaft für nur-Lese Zwecke und es bei Änderungen wirken sich nicht auf das Steuerelement.  
  
 Sie können auch dynamisch die Formatvorlagen der einzelnen Zellen in Reaktion auf Ereignisse ändern, wie z. B. die <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> und <xref:System.Windows.Forms.DataGridView.CellMouseLeave> Ereignisse. Z. B. in einem Handler für die <xref:System.Windows.Forms.DataGridView.CellMouseEnter> Ereignis können Sie den aktuellen Wert der Hintergrundfarbe der Zelle speichern (abrufen, der über der Zelle <xref:System.Windows.Forms.DataGridViewCell.Style%2A> Eigenschaft), legen Sie sie dann auf eine neue Farbe, die die Zelle hervorgehoben wird, wenn die Maus darüber bewegt wird. In einem Handler für die <xref:System.Windows.Forms.DataGridView.CellMouseLeave> Ereignis können Sie die Farbe des Hintergrunds klicken Sie dann auf den ursprünglichen Wert wiederherstellen.  
  
> [!NOTE]
>  In der Zelle gespeicherten Werte zwischenspeichern <xref:System.Windows.Forms.DataGridViewCell.Style%2A> Eigenschaft ist wichtig, unabhängig davon, ob ein bestimmter Stilwert festgelegt wird. Wenn Sie vorübergehend eine stileinstellung ersetzen, stellt sicher wiederhergestellt wird, auf den ursprünglichen Zustand von "nicht festgelegt", dass die Zelle zurückgesendet wird, erben die Style-Einstellung von einer höheren Ebene. Bei Bedarf, um zu bestimmen, das tatsächliche Format für eine Zelle, unabhängig davon, ob der Stil geerbt wird, verwenden Sie die Zelle <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> Eigenschaft.  
  
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
- [Vorgehensweise: Festlegen von Standardzellenformaten für das DataGridView-Steuerelement in Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Datenformatierung im DataGridView-Steuerelement in Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
