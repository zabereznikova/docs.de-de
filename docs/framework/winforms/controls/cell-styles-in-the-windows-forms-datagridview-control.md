---
title: "Zellstile im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Zellen, Formate"
  - "Datenblätter, Zellenstile"
  - "DataGridView-Steuerelement [Windows Forms], Zellenstile"
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Zellstile im DataGridView-Steuerelement in Windows Forms
Jede Zelle im <xref:System.Windows.Forms.DataGridView>\-Steuerelement kann über ihren eigenen Stil verfügen, z. B. Textformat, Hintergrundfarbe, Vordergrundfarbe und Schriftart.  In der Regel weisen jedoch mehrere Zellen die gleichen Stilmerkmale auf.  
  
 Zellengruppen mit gemeinsamen Stilen können alle Zellen in bestimmten Zeilen oder Spalten, alle Zellen mit bestimmten Werten oder alle Zellen im Steuerelement umfassen.  Da sich diese Gruppen überschneiden, kann jede Zelle ihre Stilinformationen von mehreren Stellen abrufen.  Beispielsweise möchten Sie, dass jede Zelle in einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement dieselbe Schriftart verwendet, aber nur Zellen in Währungsspalten das Währungsformat und nur Währungszellen mit negativen Zahlen eine rote Vordergrundfarbe verwenden sollen.  
  
## Die DataGridViewCellStyle\-Klasse  
 Die <xref:System.Windows.Forms.DataGridViewCellStyle>\-Klasse enthält die folgenden Eigenschaften für den visuellen Stil:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Diese Klasse enthält außerdem die folgenden Eigenschaften für die Formatierung:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Weitere Informationen über diese Eigenschaften und andere Zellstileigenschaften finden Sie in der <xref:System.Windows.Forms.DataGridViewCellStyle>\-Referenzdokumentation und den unter Siehe auch aufgeführten Themen.  
  
## Verwenden von DataGridViewCellStyle\-Objekten  
 Sie können <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekte von verschiedenen Eigenschaften der <xref:System.Windows.Forms.DataGridView>\-, <xref:System.Windows.Forms.DataGridViewColumn>\-, <xref:System.Windows.Forms.DataGridViewRow>\- und <xref:System.Windows.Forms.DataGridViewCell>\-Klassen und deren abgeleiteten Klassen abrufen.  Wenn eine dieser Eigenschaften noch nicht festgelegt wurde, wird durch Abrufen ihres Werts ein neues <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekt erstellt.  Sie können auch Ihre eigenen <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekte instanziieren und sie diesen Eigenschaften zuordnen.  
  
 Sie können unnötige Duplizierungen von Stilinformationen vermeiden, indem Sie <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekte für mehrere <xref:System.Windows.Forms.DataGridView>\-Elemente freigeben.  Da die auf Steuerelement\-, Spalten\- und Zeilenebene festgelegten Stile bis auf Zellebene filtern, können Sie außerdem doppelte Stile vermeiden, indem Sie auf jeder Ebene nur die Stileigenschaften festlegen, die sich von den höheren Ebenen unterscheiden.  Dies wird ausführlicher im Abschnitt Stilvererbung weiter unten beschrieben.  
  
 In der folgenden Tabelle werden die primären Eigenschaften aufgelistet, die die <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekte abrufen oder festlegen.  
  
|Property|Klassen|Beschreibung|  
|--------------|-------------|------------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow> und abgeleitete Klassen|Ruft Standardstile ab bzw. legt Standardstile fest, die von allen Zellen im gesamten Steuerelement \(einschließlich Headerzellen\), in einer Spalte oder in einer Zeile verwendet werden.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ruft Standardstile ab bzw. legt Standardstile fest, die von allen Zeilen im Steuerelement verwendet werden.  Dies umfasst keine Headerzellen.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ruft Standardstile ab bzw. legt Standardstile fest, die von abwechselnden Zeilen im Steuerelement verwendet werden.  Wird verwendet, um einen Effekt wie in einem Ledger zu erstellen.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ruft Standardzellstile ab bzw. legt Standardzellstile fest, die von den Zeilenheadern des Steuerelements verwendet werden.  Wird vom aktuellen Design überschrieben, wenn visuelle Stile aktiviert sind.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ruft Standardzellstile ab bzw. legt Standardzellstile fest, die von den Spaltenheadern des Steuerelements verwendet werden.  Wird vom aktuellen Design überschrieben, wenn visuelle Stile aktiviert sind.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> und abgeleitete Klassen|Ruft Stile ab bzw. legt Stile fest, die auf Zellenebene festgelegt wurden.  Diese Stile überschreiben diejenigen, die von höheren Ebenen geerbt wurden.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewRow>, <xref:System.Windows.Forms.DataGridViewColumn> und abgeleitete Klassen|Ruft alle Stile ab, die derzeit auf die Zelle, Zeile oder Spalte angewendet werden, einschließlich von höheren Ebenen geerbte Stile.|  
  
 Wie bereits erwähnt, wird durch das Abrufen des Werts einer Stileigenschaft automatisch ein neues <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekt instanziiert, wenn die Eigenschaft nicht zuvor festgelegt wurde.  Damit diese Objekte nicht unnötig erstellt werden, verfügen die Zeilen\- und Spaltenklassen über eine <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A>\-Eigenschaft, anhand derer Sie überprüfen können, ob die <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A>\-Eigenschaft festgelegt wurde.  Ebenso verfügen die Zellenklassen über eine <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A>\-Eigenschaft, die angibt, ob die <xref:System.Windows.Forms.DataGridViewCell.Style%2A>\-Eigenschaft festgelegt wurde.  
  
 Jede der Stileigenschaften verfügt über ein entsprechendes *PropertyName*`Changed`\-Ereignis auf dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement.  Für Zeilen\-, Spalten\- und Zelleneigenschaften fängt der Name des Ereignisses mit "`Row`", "`Column`" oder "`Cell`" an \(z. B. <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>\).  Jedes dieser Ereignisse tritt auf, wenn die entsprechende Stileigenschaft auf ein anderes <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekt festgelegt ist.  Diese Ereignisse treten nicht auf, wenn Sie ein <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekt von einer Stileigenschaft abrufen und seine Eigenschaftswerte ändern.  Um auf Änderungen an den Zellstilobjekten selbst zu reagieren, behandeln Sie das <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged>\-Ereignis.  
  
## Stilvererbung  
 Jede <xref:System.Windows.Forms.DataGridViewCell> ruft ihre Darstellung von der zugehörigen <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>\-Eigenschaft ab.  Das von dieser Eigenschaft zurückgegebene <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekt erbt seine Werte von einer Eigenschaftenhierarchie des Typs <xref:System.Windows.Forms.DataGridViewCellStyle>.  Diese Eigenschaften werden unten in der Reihenfolge aufgelistet, in der der <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> für Nicht\-Headerzellen seine Werte abruft.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=fullName>  
  
3.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName> \(nur für Zellen in Zeilen mit ungeraden Indexnummern\)  
  
4.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>  
  
5.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>  
  
6.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 Für Zeilen\- und Spaltenheaderzellen wird die <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>\-Eigenschaft mit Werten aus der folgenden Liste mit Quelleigenschaften in der angegebenen Reihenfolge gefüllt.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=fullName> oder <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=fullName>  
  
3.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 Dieser Prozess wird anhand des folgenden Diagramms veranschaulicht.  
  
 ![Eigenschaften des DataGridViewCellStyle&#45;Typs](../../../../docs/framework/winforms/controls/media/datagridviewcells1.png "DataGridViewCells1")  
  
 Sie können auch auf die Stile zugreifen, die von bestimmten Zeilen und Spalten geerbt wurden.  Die <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A>\-Spalteneigenschaft erbt die Werte von den folgenden Eigenschaften.  
  
1.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 Die <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A>\-Zeileneigenschaft erbt die Werte von den folgenden Eigenschaften.  
  
1.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName> \(nur für Zellen in Zeilen mit ungeraden Indexnummern\)  
  
3.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>  
  
4.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 Für jede Eigenschaft in einem <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekt, das von einer `InheritedStyle`\-Eigenschaft zurückgegeben wird, wird der Eigenschaftswert vom ersten Zellstil in der entsprechenden Liste abgerufen, deren Eigenschaft auf einen anderen Wert als die Standardwerte der <xref:System.Windows.Forms.DataGridViewCellStyle>\-Klasse festgelegt ist.  
  
 Die folgende Tabelle zeigt, wie der <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>\-Eigenschaftswert für eine Beispielzelle von der Spalte geerbt wird, in der er enthalten ist.  
  
|Eigenschaft vom Typ `DataGridViewCellStyle`|`ForeColor`\-Beispielwert für abgerufenes Objekt|  
|-------------------------------------------------|------------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Empty?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Red%2A?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Empty?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Empty?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Black%2A?displayProperty=fullName>|  
  
 In diesem Fall ist der <xref:System.Drawing.Color.Red%2A?displayProperty=fullName>\-Wert aus der Zeile der Zelle der erste reale Wert in der Liste.  Dieser wird zum <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>\-Eigenschaftswert des <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> der Zelle.  
  
 Im folgenden Diagramm wird gezeigt, wie verschiedene <xref:System.Windows.Forms.DataGridViewCellStyle>\-Eigenschaften ihre Werte von verschiedenen Stellen erben können.  
  
 ![Vererbung von DataGridView&#45;Eigenschaftswerten](../../../../docs/framework/winforms/controls/media/datagridviewcells2.png "DataGridViewCells2")  
  
 Mithilfe der Stilvererbung können Sie geeignete Stile für das gesamte Steuerelement bereitstellen, ohne dieselben Informationen an mehreren Stellen angeben zu müssen.  
  
 Obwohl Headerzellen bei der Stilvererbung wie beschrieben mitwirken, verfügen die von der <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>\-Eigenschaft und der <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>\-Eigenschaft des <xref:System.Windows.Forms.DataGridView>\-Steuerelements zurückgegebenen Objekte anfänglich über Eigenschaftswerte, die die Eigenschaftswerte des von der <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>\-Eigenschaft zurückgegebenen Objekts überschreiben.  Wenn die Eigenschaften, die für das von der <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>\-Eigenschaft zurückgegebene Objekt festgelegt sind, auf Zeilen\- und Spaltenheader angewendet werden sollen, müssen Sie die entsprechenden Eigenschaften der Objekte, die von der <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>\-Eigenschaft und der <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>\-Eigenschaft zurückgegeben werden, auf die für die <xref:System.Windows.Forms.DataGridViewCellStyle>\-Klasse angegebenen Standardwerte festlegen.  
  
> [!NOTE]
>  Wenn visuelle Stile aktiviert sind, wird auf die Zeilen\- und Spaltenheader \(mit Ausnahme der <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>\) automatisch das aktuelle Design angewendet, das alle Stile überschreibt, die von diesen Eigenschaften festgelegt wurden.  
  
 Die <xref:System.Windows.Forms.DataGridViewButtonColumn>\-, <xref:System.Windows.Forms.DataGridViewImageColumn>\- und <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>\-Typen initialisieren auch einige Werte des Objekts, das von der <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>\-Spalteneigenschaft zurückgegeben wird.  Weitere Informationen finden Sie in der Referenzdokumentation für diese Typen.  
  
## Dynamisches Festlegen von Stilen  
 Um die Stile der Zellen mit bestimmten Werten anzupassen, implementieren Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName>\-Ereignis.  Handler für dieses Ereignis empfangen ein Argument des <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>\-Typs.  Dieses Objekt enthält Eigenschaften, mit denen Sie den Wert der formatierten Zelle sowie ihre Position im <xref:System.Windows.Forms.DataGridView>\-Steuerelement bestimmen können.  Dieses Objekt enthält außerdem eine <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A>\-Eigenschaft, die auf den Wert der <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>\-Eigenschaft der formatierten Zelle initialisiert wird.  Sie können die Zellstileigenschaften ändern, um für den Wert und die Position der Zelle geeignete Stilinformationen anzugeben.  
  
> [!NOTE]
>  Das <xref:System.Windows.Forms.DataGridView.RowPrePaint>\-Ereignis und das <xref:System.Windows.Forms.DataGridView.RowPostPaint>\-Ereignis empfangen ebenfalls ein <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekt in den Ereignisdaten. In ihrem Fall handelt es sich aber um eine schreibgeschützte Kopie der <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A>\-Zeileneigenschaft, deren Änderungen sich nicht auf das Steuerelement auswirken.  
  
 Sie können auch die Stile einzelner Zellen als Reaktion auf Ereignisse wie das <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=fullName>\-Ereignis und das <xref:System.Windows.Forms.DataGridView.CellMouseLeave>\-Ereignis dynamisch bearbeiten.  Beispielsweise könnten Sie in einem Handler für das <xref:System.Windows.Forms.DataGridView.CellMouseEnter>\-Ereignis den aktuellen Wert für die Hintergrundfarbe der Zelle speichern \(der durch die <xref:System.Windows.Forms.DataGridViewCell.Style%2A>\-Eigenschaft der Zelle abgerufen wird\) und ihn anschließend auf eine neue Farbe festlegen, mit der die Zelle hervorgehoben wird, wenn mit der Maus darauf gezeigt wird.  In einem Handler für das <xref:System.Windows.Forms.DataGridView.CellMouseLeave>\-Ereignis können Sie dann die Hintergrundfarbe auf den ursprünglichen Wert zurücksetzen.  
  
> [!NOTE]
>  Unabhängig davon, ob ein bestimmter Stilwert festgelegt wurde, ist es wichtig, die in der <xref:System.Windows.Forms.DataGridViewCell.Style%2A>\-Eigenschaft der Zelle gespeicherten Werte zwischenzuspeichern.  Wenn Sie eine Stileinstellung vorübergehend ersetzen, wird durch das Wiederherstellen des ursprünglichen, nicht festgelegten Zustands sichergestellt, dass die Zelle die Stileinstellung wieder von einer höheren Ebene erbt.  Wenn Sie den tatsächlichen Stil einer Zelle unabhängig davon bestimmen müssen, ob der Stil geerbt wird, verwenden Sie die <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>\-Eigenschaft der Zelle.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=fullName>   
 [Grundlegende Formatierungen und Formate im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Festlegen von Standardzellenformaten für das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)   
 [Datenformatierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)