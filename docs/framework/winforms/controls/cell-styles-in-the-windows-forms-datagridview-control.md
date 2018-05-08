---
title: Zellstile im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: 463fbbffe1e88991934f08fbe7e7445b2e233081
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Zellstile im DataGridView-Steuerelement in Windows Forms
Jede Zelle innerhalb der <xref:System.Windows.Forms.DataGridView> Steuerelement kann über einen eigenen Stil, z. B. Textformat, Hintergrundfarbe, Vordergrundfarbe und Schriftart verfügen. In der Regel werden jedoch mehrere Zellen Stilmerkmale.  
  
 Gruppen von Zellen, die Stile freigeben können alle Zellen innerhalb bestimmter Zeilen oder Spalten, alle, die bestimmte Werte enthalten, oder alle Zellen im Steuerelement enthalten. Da diese Gruppen überschneiden, kann jede Zelle ihre Stilinformationen von mehr als einem zentralen Ort abrufen. Sie können z. B. jede Zelle einer <xref:System.Windows.Forms.DataGridView> Steuerelement in den gleichen Schriftart, aber nur Zellen in den Currency-Spalten das Währungsformat und nur Währungszellen mit negativen Zahlen zu verwenden, um eine rote Vordergrundfarbe verwenden.  
  
## <a name="the-datagridviewcellstyle-class"></a>Die DataGridViewCellStyle-Klasse  
 Die <xref:System.Windows.Forms.DataGridViewCellStyle> Klasse enthält die folgenden Eigenschaften im Zusammenhang mit den visuellen Stil:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Diese Klasse enthält auch die folgenden Eigenschaften im Zusammenhang mit der Formatierung:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Weitere Informationen für diese und andere Zellstil Eigenschaften finden Sie unter der <xref:System.Windows.Forms.DataGridViewCellStyle> Referenz-Dokumentation und in den Themen auch finden Sie unten im Abschnitt aufgeführt.  
  
## <a name="using-datagridviewcellstyle-objects"></a>Verwenden von DataGridViewCellStyle-Objekten  
 Können Sie abrufen <xref:System.Windows.Forms.DataGridViewCellStyle> von verschiedenen Eigenschaften der Objekte die <xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>, und <xref:System.Windows.Forms.DataGridViewCell> Klassen und deren abgeleiteten Klassen. Wenn eine dieser Eigenschaften noch nicht festgelegt wurde, der Wert abgerufen wird erstellen Sie ein neues <xref:System.Windows.Forms.DataGridViewCellStyle> Objekt. Eigene instanziieren <xref:System.Windows.Forms.DataGridViewCellStyle> -Objekte und weisen Sie sie auf diese Eigenschaften.  
  
 Sie können unnötige Verdoppelungen von Formatinformationen vermeiden, indem Sie die Freigabe <xref:System.Windows.Forms.DataGridViewCellStyle> für mehrere Objekte <xref:System.Windows.Forms.DataGridView> Elemente. Da die Stile auf das Steuerelement, Spalte und Ebenen Zeilenfilter nach unten bis auf Zellenebene festgelegt, können Sie auch Zellebene vermeiden, indem Sie nur die Stileigenschaften auf jeder Ebene, die von den höheren Ebenen unterscheiden. Dies wird ausführlicher im Abschnitt Stil Vererbung folgenden beschrieben.  
  
 Die folgende Tabelle enthält die primären Eigenschaften, die abzurufenden oder festzulegenden <xref:System.Windows.Forms.DataGridViewCellStyle> Objekte.  
  
|Eigenschaft|Klassen|Beschreibung|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>, und die abgeleiteten Klassen|Ruft ab, oder legt ihn fest Standardstile verwendet, die für alle Zellen in das gesamte Steuerelement (einschließlich der Headerzellen) in einer Spalte oder in einer Zeile.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Abrufen oder Festlegen von standardmäßigen Zellenstilen verwendet, die für alle Zeilen im Steuerelement. Dies schließt nicht die Kopfzeilenzellen.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Abrufen oder Festlegen von standardmäßigen Zellenstilen von abwechselnden Zeilen im Steuerelement verwendet. Dient zum Erstellen von eines Ledger-ähnlichen Effekts.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Abrufen oder Festlegen von standardmäßigen Zellenstilen von Zeilenheader für das Steuerelement verwendet. Durch das aktuelle Design überschrieben, wenn visuelle Stile aktiviert sind.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Abrufen oder Festlegen von standardmäßigen Zellenstilen von Spaltenüberschriften für das Steuerelement verwendet. Durch das aktuelle Design überschrieben, wenn visuelle Stile aktiviert sind.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> und abgeleitete Klassen|Ruft ab, oder legt ihn fest Formatvorlagen auf Zellenebene angegeben. Diese Stile überschreiben von höheren Ebenen geerbte.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewRow>, <xref:System.Windows.Forms.DataGridViewColumn>, und die abgeleiteten Klassen|Ruft die Stile, die derzeit auf die Zelle, Zeile oder Spalte, einschließlich von höheren Ebenen geerbte Stile angewendet.|  
  
 Wie bereits erwähnt, Abrufen des Werts der Style-Eigenschaft automatisch eine neue instanziiert <xref:System.Windows.Forms.DataGridViewCellStyle> Objekt, wenn die Eigenschaft nicht zuvor festgelegt wurde. Um zu vermeiden, diese Objekte nicht unnötig erstellt, die Zeilen- und Klassen verfügen über eine <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> -Eigenschaft, die Sie überprüfen können, um zu bestimmen, ob die <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> Eigenschaft festgelegt wurde. Auf ähnliche Weise die Zellenklassen verfügen über eine <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> Eigenschaft, die angibt, ob die <xref:System.Windows.Forms.DataGridViewCell.Style%2A> Eigenschaft festgelegt wurde.  
  
 Jede der Stileigenschaften verfügt über ein entsprechendes *PropertyName* `Changed` Ereignis auf der <xref:System.Windows.Forms.DataGridView> Steuerelement. Für Zeilen-, Spalten- und Zelleigenschaften, der der Namen des Ereignisses beginnt mit "`Row`","`Column`", oder "`Cell`" (z. B. <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>). Jedes dieser Ereignisse tritt auf, wenn die entsprechende Style-Eigenschaft, auf einen anderen festgelegt ist <xref:System.Windows.Forms.DataGridViewCellStyle> Objekt. Diese Ereignisse treten nicht beim Abrufen einer <xref:System.Windows.Forms.DataGridViewCellStyle> -Objekt aus einem Style-Eigenschaft und ihre Eigenschaftswerte ändern. Um Änderungen an die Zelle stilobjekte selbst zu behandeln, behandeln die <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged> Ereignis.  
  
## <a name="style-inheritance"></a>Stil-Vererbung  
 Jede <xref:System.Windows.Forms.DataGridViewCell> ruft seine Darstellung von dessen <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> Eigenschaft. Die <xref:System.Windows.Forms.DataGridViewCellStyle> von dieser Eigenschaft zurückgegebene Objekt erbt die Werte aus einer Hierarchie der Eigenschaften des Typs <xref:System.Windows.Forms.DataGridViewCellStyle>. Diese Eigenschaften sind unten aufgeführt, in der Reihenfolge, in der die <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> für nicht-Headerzellen seine Werte abruft.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (nur für Zellen in Zeilen mit ungerader Indexnummern)  
  
4.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Für Zeilen- und Headerzellen der <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> Eigenschaft wird angegeben, nach Werten in der folgenden Liste von Datenquelleneigenschaften in der angegebenen Reihenfolge.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> oder <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Das folgende Diagramm veranschaulicht diesen Prozess.  
  
 ![Eigenschaften des DataGridViewCellStyle-Typs](../../../../docs/framework/winforms/controls/media/datagridviewcells1.gif "DataGridViewCells1")  
  
 Sie können auch die Stile, die von bestimmten Zeilen und Spalten geerbt zugreifen. Die Spalte <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> -Eigenschaft erbt seine Werte aus den folgenden Eigenschaften.  
  
1.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Die Zeile <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> -Eigenschaft erbt seine Werte aus den folgenden Eigenschaften.  
  
1.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (nur für Zellen in Zeilen mit ungerader Indexnummern)  
  
3.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Für jede Eigenschaft in ein <xref:System.Windows.Forms.DataGridViewCellStyle> zurückgegebenes Objekt ein `InheritedStyle` -Eigenschaft den Wert der Eigenschaft wird abgerufen, vom ersten Zellstil in der entsprechenden Liste aus, die die entsprechende Eigenschaft nicht auf einen Wert festgelegt wurde der <xref:System.Windows.Forms.DataGridViewCellStyle> -Klasse Standardwerte.  
  
 Die folgende Tabelle verdeutlicht, wie die <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> Eigenschaftswert für eine Beispielzelle wird von der enthaltenden Spalte vererbt.  
  
|Eigenschaft vom Typ `DataGridViewCellStyle`|Beispiel `ForeColor` Wert für das abgerufene Objekt|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 In diesem Fall die <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> Wert aus der Zeile der Zelle wird der erste reale Wert in der Liste. Dies ist die <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> Eigenschaftswert, der der Zelle <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>.  
  
 Im folgende Diagramm wird veranschaulicht, wie mit verschiedenen <xref:System.Windows.Forms.DataGridViewCellStyle> Eigenschaften können ihre Werte aus verschiedenen Quellen erben.  
  
 ![DataGridView-Eigenschaft&#45;Wert Vererbung](../../../../docs/framework/winforms/controls/media/datagridviewcells2.gif "DataGridViewCells2")  
  
 Durch nutzen die Vererbung von Stilen, können Sie die entsprechenden Stile für das gesamte Steuerelement bereitstellen, ohne die gleiche Informationen an mehreren Orten angeben zu müssen.  
  
 Obwohl Headerzellen an der Stil Vererbung teilnehmen möchten, wie beschrieben, die Objekte zurückgegeben, durch die <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> und <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> Eigenschaften der <xref:System.Windows.Forms.DataGridView> Kontrolle haben die anfänglichen Eigenschaftenwerte, die die Eigenschaftswerte des Objekts zurückgegeben wird, durch Überschreiben die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> Eigenschaft. Wenn Sie die Eigenschaften für das zurückgegebene Objekt festgelegt werden soll die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> Eigenschaft zuweisen von Zeilen- und Spaltenüberschriften, müssen Sie die entsprechenden Eigenschaften des vom zurückgegebenen Objekte Festlegen der <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> und <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> Eigenschaften auf die Standardwerte angegeben für die <xref:System.Windows.Forms.DataGridViewCellStyle> Klasse.  
  
> [!NOTE]
>  Wenn visuelle Stile aktiviert sind, die Zeilen- und Spaltenüberschriften (mit Ausnahme der <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) automatisch durch das aktuelle Design, überschreiben alle diese Eigenschaften gemäß Formatvorlagen formatiert sind.  
  
 Die <xref:System.Windows.Forms.DataGridViewButtonColumn>, <xref:System.Windows.Forms.DataGridViewImageColumn>, und <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> -Typen initialisieren auch einige Werte des Objekts, das von der Spalte zurückgegeben <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> Eigenschaft. Weitere Informationen finden Sie in der Referenzdokumentation für diese Typen.  
  
## <a name="setting-styles-dynamically"></a>Dynamisches Festlegen von Stilen  
 Implementieren Sie zum Anpassen der Stile eines Zellen mit bestimmten Werten einen Handler für das <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> Ereignis. Handler für dieses Ereignis empfängt ein Argument der <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> Typ. Dieses Objekt enthält Eigenschaften, mit denen Sie den Wert des zusammen mit ihrem Speicherort im formatierten Zelle bestimmen die <xref:System.Windows.Forms.DataGridView> Steuerelement. Dieses Objekt enthält auch eine <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> -Eigenschaft, die auf den Wert des initialisiert wird die <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> -Eigenschaft der Zelle formatiert wird. Sie können die Eigenschaften für den Zellstil zum Angeben von Formatinformationen für den Wert der Zelle und den Speicherort ändern.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.DataGridView.RowPrePaint> und <xref:System.Windows.Forms.DataGridView.RowPostPaint> empfangen von Ereignissen auch eine <xref:System.Windows.Forms.DataGridViewCellStyle> Objektdaten im Ereignis allerdings in Großschreibung, handelt es sich, eine Kopie der Zeile <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> Eigenschaft für Lesezwecke und Änderungen an sie wirken sich nicht auf das Steuerelement.  
  
 Sie können auch dynamisch die Formatvorlagen der einzelnen Zellen als Antwort auf Ereignisse ändern, wie z. B. die <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> und <xref:System.Windows.Forms.DataGridView.CellMouseLeave> Ereignisse. Z. B. in einen Handler für das <xref:System.Windows.Forms.DataGridView.CellMouseEnter> -Ereignis können Sie den aktuellen Wert der Hintergrundfarbe der Zelle speichern (über der Zelle abgerufen <xref:System.Windows.Forms.DataGridViewCell.Style%2A> Eigenschaft), legen Sie sie dann auf eine neue Farbe, die die Zelle hervorgehoben wird, wenn der Mauszeiger darüber bewegt wird. In einem Ereignishandler für das <xref:System.Windows.Forms.DataGridView.CellMouseLeave> -Ereignis können Sie die Farbe des Hintergrunds klicken Sie dann auf den ursprünglichen Wert wiederherstellen.  
  
> [!NOTE]
>  In der Zelle gespeicherten Werte zwischenspeichern <xref:System.Windows.Forms.DataGridViewCell.Style%2A> Eigenschaft ist wichtig, unabhängig davon, ob ein bestimmter Stilwert festgelegt wird. Wenn Sie vorübergehend eine stileinstellung ersetzen, stellt sicher in den Originalzustand "nicht konfiguriert" wiederhergestellt wird, dass die Zelle zurückzukehren erben von der Einstellung von einer höheren Ebene. Wenn Sie bestimmen die Formatvorlage für eine Zelle, unabhängig davon, ob der Stil geerbt wird, verwenden Sie der Zelle <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>  
 [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [Gewusst wie: Festlegen von Standardzellenformaten für das DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 [Datenformatierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)
