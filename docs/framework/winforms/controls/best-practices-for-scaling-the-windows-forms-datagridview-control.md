---
title: "Empfohlene Vorgehensweisen f&#252;r das Skalieren des DataGridView-Steuerelements in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Bewährte Methoden, DataGridView-Steuerelement"
  - "Datenblätter, Bewährte Methoden"
  - "DataGridView-Steuerelement [Windows Forms], Bewährte Methoden"
  - "DataGridView-Steuerelement [Windows Forms], Freigeben von Zeilen"
  - "DataGridView-Steuerelement [Windows Forms], Skalieren"
  - "DataGridView-Steuerelement [Windows Forms], Freigegebene Zeilen"
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# Empfohlene Vorgehensweisen f&#252;r das Skalieren des DataGridView-Steuerelements in Windows Forms
Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement ist für maximale Skalierbarkeit ausgelegt.  Wenn Sie umfangreiche Datenmengen anzeigen müssen, sollten Sie die in diesem Thema beschriebenen Richtlinien befolgen, um zu verhindern, dass der Arbeitsspeicher überlastet oder die Reaktionsfähigkeit der Benutzeroberfläche beeinträchtigt wird.  In diesem Thema werden folgende Aspekte behandelt:  
  
-   Effiziente Verwendung von Zellenstilen  
  
-   Effiziente Verwendung von Kontextmenüs  
  
-   Effiziente Verwendung der automatischen Größenanpassung  
  
-   Effiziente Verwendung der Auflistungen für ausgewählte Zellen, Zeilen und Spalten  
  
-   Verwenden freigegebener Zeilen  
  
-   Verhindern, dass die Zeilenfreigabe aufgehoben wird  
  
 Bei besonderen Leistungsanforderungen können Sie den virtuellen Modus implementieren und eigene Datenverwaltungsoperationen bereitstellen.  Weitere Informationen finden Sie unter [Datenanzeigemodi im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).  
  
## Effiziente Verwendung von Zellenstilen  
 Jede Zelle, Zeile und Spalte kann eigene Formatinformationen haben.  Formatinformationen werden in <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekten gespeichert.  Das Erstellen von Zellenstilobjekten für viele einzelne <xref:System.Windows.Forms.DataGridView>\-Elemente kann sich als ineffizient erweisen, besonders bei der Bearbeitung umfangreicher Datenmengen.  Befolgen Sie die nachstehenden Richtlinien, um Leistungseinbußen zu vermeiden:  
  
-   Legen Sie keine Zellenstileigenschaften für ein einzelnes <xref:System.Windows.Forms.DataGridViewCell>\-Objekt oder <xref:System.Windows.Forms.DataGridViewRow>\-Objekt fest.  Dies schließt das von der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>\-Eigenschaft angegebene Zeilenobjekt ein.  Jeder von der Zeilenvorlage geklonten neuen Zeile wird eine eigene Kopie des Zellenstilobjekts der Vorlage zugewiesen.  Um maximale Skalierbarkeit zu erzielen, sollten Sie die Zellenstileigenschaften auf <xref:System.Windows.Forms.DataGridView>\-Ebene festlegen.  Legen Sie beispielsweise die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>\-Eigenschaft anstelle der <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>\-Eigenschaft fest.  
  
-   Falls einige Zellen eine vom Standardformat abweichende Formatierung erfordern, verwenden Sie dieselbe <xref:System.Windows.Forms.DataGridViewCellStyle>\-Instanz übergreifend für Zellen\-, Zeilen\- oder Spaltengruppen.  Vermeiden Sie es, Eigenschaften des Typs <xref:System.Windows.Forms.DataGridViewCellStyle> für einzelne Zellen, Zeilen und Spalten direkt festzulegen.  Ein Beispiel für die Freigabe von Zellenstilen finden Sie unter [Gewusst wie: Festlegen von Standardzellenformaten für das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  Sie können außerdem eine Leistungsminderung beim Festlegen individueller Zellenstile vermeiden, indem Sie den <xref:System.Windows.Forms.DataGridView.CellFormatting>\-Ereignishandler behandeln.  Ein Beispiel finden Sie unter [Gewusst wie: Anpassen der Datenformatierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
-   Verwenden Sie beim Festlegen eines Zellenstils die <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=fullName>\-Eigenschaft anstelle der <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>\-Eigenschaft.  Beim Zugriff auf die <xref:System.Windows.Forms.DataGridViewCell.Style%2A>\-Eigenschaft wird eine neue Instanz der <xref:System.Windows.Forms.DataGridViewCellStyle>\-Klasse erstellt, falls die Eigenschaft noch nicht verwendet wurde.  Außerdem enthält dieses Objekt u. U. nicht die vollständigen Formatinformation für die Zelle, wenn einige Stile von der Zeile bzw. Spalte oder dem Steuerelement geerbt wurden.  Weitere Informationen über die Vererbung von Zellenstilen finden Sie unter [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## Effiziente Verwendung von Kontextmenüs  
 Jede Zelle, Zeile und Spalte kann über ein eigenes Kontextmenü verfügen.  Kontextmenüs werden im <xref:System.Windows.Forms.DataGridView>\-Steuerelement durch <xref:System.Windows.Forms.ContextMenuStrip>\-Steuerelemente dargestellt.  Genauso wie bei Zellenstilobjekten hat das Erstellen von Kontextmenüs für viele einzelne <xref:System.Windows.Forms.DataGridView>\-Elemente negative Auswirkungen auf die Systemleistung.  Um diese Leistungsminderung zu vermeiden, beachten Sie die folgenden Richtlinien:  
  
-   Erstellen Sie keine Kontextmenüs für einzelne Zellen und Zeilen.  Dies gilt auch für die Zeilenvorlage, die zusammen mit ihrem Kontextmenü geklont wird, sobald dem Steuerelement neue Zeilen hinzugefügt werden.  Um optimale Skalierbarkeit zu gewährleisten, verwenden Sie ausschließlich die <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>\-Eigenschaft des Steuerelements, um ein einziges Kontextmenü für das gesamte Steuerelement zu erstellen.  
  
-   Wenn Sie mehrere Kontextmenüs für mehrere Zeilen oder Zellen benötigen, behandeln Sie das <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded>\-Ereignis oder das <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>\-Ereignis.  Diese Ereignisse ermöglichen es Ihnen, die Kontextmenüobjekte selbst zu verwalten und so die Leistung zu optimieren.  
  
## Effiziente Verwendung der automatischen Größenanpassung  
 Die Größe von Zeilen, Spalten und Headern kann in Anpassung an veränderte Zellinhalte automatisch geändert werden, damit der gesamte Inhalt der Zellen sichtbar ist und keine Informationen abgeschnitten werden.  Durch das Ändern von Größenanpassungsmodi kann auch die Größe von Zeilen, Spalten und Headern geändert werden.  Um die richtige Größe zu bestimmen, muss das <xref:System.Windows.Forms.DataGridView>\-Steuerelement den Wert jeder Zelle überprüfen, die es aufnehmen muss.  Bei der Arbeit mit umfangreichen Datasets kann sich diese Analyse bei einer automatischen Größenanpassung negativ auf die Steuerelementleistung auswirken.  Um Leistungsminderungen zu vermeiden, beachten Sie die folgenden Richtlinien:  
  
-   Verzichten Sie bei einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit umfangreichen Rowsets auf die automatische Größenanpassung.  Wenn Sie die automatische Größenanpassung trotzdem verwenden, führen Sie die Anpassung nur auf der Grundlage der angezeigten Zeilen aus.  Auch im virtuellen Modus sollten nur die angezeigten Zeilen verwendet werden.  
  
    -   Verwenden Sie für Zeilen und Spalten das `DisplayedCells`\-Feld oder das `DisplayedCellsExceptHeaders`\-Feld der Enumerationen <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode> und <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>.  
  
    -   Verwenden Sie für Zeilenheader das <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>\-Feld oder das <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>\-Feld der <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>\-Enumeration.  
  
-   Deaktivieren Sie die automatische Größenanpassung, und verwenden Sie die programmgesteuerte Größenanpassung, um optimale Skalierbarkeit zu erzielen.  
  
 Weitere Informationen finden Sie unter [Größenänderungsoptionen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
## Effiziente Verwendung der Auflistungen für ausgewählte Zellen, Zeilen und Spalten  
 Die <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>\-Auflistung bietet bei umfangreichen Auswahlen keine effiziente Leistung.  Auch die <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>\-Auflistung und die <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>\-Auflistung können sich ineffizient erweisen – wenn auch in einem geringeren Grad. Dies liegt daran, dass ein typisches <xref:System.Windows.Forms.DataGridView>\-Steuerelement wesentlich weniger Zeilen als Zellen und wesentlich weniger Spalten als Zeilen enthält.  Um Leistungseinbußen bei Verwendung dieser Auflistungen zu vermeiden, beachten Sie die folgenden Richtlinien:  
  
-   Um festzustellen, ob alle Zellen in <xref:System.Windows.Forms.DataGridView> ausgewählt wurden, bevor Sie auf den Inhalt der <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>\-Auflistung zugreifen, überprüfen Sie den Rückgabewert der <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>\-Methode.  Diese Methode kann jedoch bewirken, dass die Freigabe von Zeilen aufgehoben wird.  Weitere Informationen finden Sie im nächsten Abschnitt.  
  
-   Vermeiden Sie es, die <xref:System.Collections.ICollection.Count%2A>\-Eigenschaft von <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=fullName> zu verwenden, um die Anzahl ausgewählter Zellen zu ermitteln.  Verwenden Sie stattdessen die <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=fullName>\-Methode, und übergeben Sie den <xref:System.Windows.Forms.DataGridViewElementStates?displayProperty=fullName>\-Wert.  Entsprechend sollten Sie die <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=fullName>\-Methode und die <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=fullName>\-Methode verwenden, um die Anzahl ausgewählter Elemente zu ermitteln, anstatt auf die Auflistungen für ausgewählte Zeilen und Spalten zuzugreifen.  
  
-   Vermeiden Sie zellenbasierte Auswahlmodi.  Legen Sie stattdessen die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName>\-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName> oder <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName> fest.  
  
## Verwenden freigegebener Zeilen  
 Eine effiziente Speichernutzung wird im <xref:System.Windows.Forms.DataGridView>\-Steuerelement durch freigegebene Zeilen erreicht.  Dabei werden von den Zeilen möglichst viele Informationen über Zeilendarstellung und \-verhalten gemeinsam genutzt, indem Instanzen der <xref:System.Windows.Forms.DataGridViewRow>\-Klasse freigegeben werden.  
  
 Die gemeinsame Nutzung von Zeileninstanzen entlastet zwar den Arbeitsspeicher, kann aber dazu führen, dass die Freigabe von Zeilen aufgehoben wird.  Beispielsweise wird jedes Mal, wenn ein Benutzer direkt mit einer Zelle interagiert, die Freigabe der betreffenden Zeile aufgehoben.  Da dieses Verhalten nicht unterbunden werden kann, sind die Richtlinien in diesem Thema nur bei der Arbeit mit sehr großen Datenmengen hilfreich und auch nur dann, wenn Benutzer bei jeder Ausführung des Programms mit einem relativ geringen Teil der Daten interagieren.  
  
 Eine Zeile kann in einem ungebundenen <xref:System.Windows.Forms.DataGridView>\-Steuerelement nicht freigegeben werden, wenn eine ihrer Zellen Werte enthält.  Wenn das <xref:System.Windows.Forms.DataGridView>\-Steuerelement an eine externe Datenquelle gebunden ist, oder wenn Sie den virtuellen Modus implementieren und eine eigene Datenquelle bereitstellen, werden die Zellwerte außerhalb des Steuerelements und nicht in Zellobjekten gespeichert, wodurch die Zeilen freigegeben werden können.  
  
 Ein Zeilenobjekt kann nur freigegeben werden, wenn der Zustand all seiner Zellen über den Zustand der Zeile und den jeweiligen Zustand der Spalten ermittelt werden kann, in denen die Zellen enthalten sind.  Wenn Sie den Zustand einer Zelle ändern, sodass er nicht mehr vom Zustand der zugehörigen Zeile und Spalte abgeleitet werden kann, kann die Zeile nicht freigegeben werden.  
  
 Beispielsweise können Zeilen in folgenden Situationen nicht freigegeben werden:  
  
-   Die Zeile enthält eine einzelne ausgewählte Zelle, die sich nicht in einer ausgewählten Spalte befindet.  
  
-   Die Zeile enthält eine Zelle, deren <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A>\-Eigenschaft oder <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A>\-Eigenschaft festgelegt ist.  
  
-   Die Zeile enthält <xref:System.Windows.Forms.DataGridViewComboBoxCell> mit festgelegter <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A>\-Eigenschaft.  
  
 Im gebundenen oder virtuellen Modus können Sie QuickInfos und Kontextmenüs für einzelne Zellen bereitstellen, indem Sie das <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>\-Ereignis und das <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded>\-Ereignis behandeln.  
  
 Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement versucht automatisch, freigegebene Zeilen zu verwenden, sobald <xref:System.Windows.Forms.DataGridViewRowCollection> Zeilen hinzugefügt werden.  Beachten Sie die folgenden Richtlinien, um sicherzustellen, dass die Zeilenfreigabe erhalten bleibt:  
  
-   Vermeiden Sie es, die `Add(Object[])`\-Überladung der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>\-Methode und die `Insert(Object[])`\-Überladung der <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A>\-Methode aus der <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName>\-Auflistung aufzurufen.  Durch diese Überladungen wird die Freigabe von Zeilen automatisch aufgehoben.  
  
-   Stellen Sie sicher, dass die Freigabe der in der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=fullName>\-Eigenschaft angegebenen Zeile in den folgenden Fällen erhalten bleibt:  
  
    -   Beim Aufrufen der `Add()`\-Überladung oder der `Add(Int32)`\-Überladung der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>\-Methode bzw. der `Insert(Int32,Int32)`\-Überladung der <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A>\-Methode aus der <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName>\-Auflistung  
  
    -   Beim Erhöhen des Werts der <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=fullName>\-Eigenschaft  
  
    -   Beim Festlegen der <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=fullName>\-Eigenschaft  
  
-   Achten Sie darauf, dass die Freigabe der durch den `indexSource`\-Parameter angegebenen Zeile erhalten bleibt, wenn die Methoden <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A> und <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> der <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName>\-Auflistung aufgerufen werden.  
  
-   Achten Sie darauf, dass die Freigabe der angegebenen Zeile\(n\) erhalten bleibt, wenn die `Add(DataGridViewRow)`\-Überladung der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>\-Methode, die <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A>\-Methode, die `Insert(Int32,DataGridViewRow)`\-Überladung der <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A>\-Methode und die <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A>\-Methode aus der <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName>\-Auflistung aufgerufen werden.  
  
 Um festzustellen, ob eine Zeile freigegeben ist, rufen Sie das Zeilenobjekt mit der <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=fullName>\-Methode ab und überprüfen dann die <xref:System.Windows.Forms.DataGridViewBand.Index%2A>\-Eigenschaft des Objekts.  Freigegebene Zeilen verfügen immer über einen <xref:System.Windows.Forms.DataGridViewBand.Index%2A>\-Eigenschaftswert von \-1.  
  
## Verhindern, dass die Zeilenfreigabe aufgehoben wird  
 Die Freigabe von Zeilen kann durch Code oder aufgrund einer Benutzeraktion aufgehoben werden.  Um Auswirkungen auf die Systemleistung zu vermeiden, sollten Sie darauf achten, dass die Freigabe von Zeilen nicht aufgehoben wird.  Während der Anwendungsentwicklung können Sie das <xref:System.Windows.Forms.DataGridView.RowUnshared>\-Ereignis behandeln, um festzustellen, wann die Freigabe von Zeilen aufgehoben wird.  Dies ist beim Debuggen von Problemen bei der Zeilenfreigabe von Nutzen.  
  
 Um zu verhindern, dass die Freigabe von Zeilen aufgehoben wird, beachten Sie die folgenden Richtlinien:  
  
-   Vermeiden Sie es, die <xref:System.Windows.Forms.DataGridView.Rows%2A>\-Auflistung zu indizieren oder sie mit einer `foreach`\-Schleife zu durchlaufen.  In aller Regel müssen Sie nicht direkt auf Zeilen zugreifen.  <xref:System.Windows.Forms.DataGridView>\-Methoden, die für Zeilen verwendet werden, verwenden anstelle von Zeileninstanzen die Argumente für den Zeilenindex.  Darüber hinaus empfangen Handler für zeilenbezogene Ereignisse Ereignisargumentobjekte mit Zeileneigenschaften, die Sie zum Bearbeiten von Zeilen verwenden können, ohne dass dabei die Zeilenfreigabe aufgehoben wird.  
  
-   Verwenden Sie die <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=fullName>\-Methode, und übergeben Sie den tatsächlichen Index der Zeile, um auf ein Zeilenobjekt zuzugreifen.  Beachten Sie jedoch, dass durch das Ändern eines freigegebenen Zeilenobjekts, das über diese Methode abgerufen wird, alle Zeilen geändert werden, die dieses Objekt gemeinsam nutzen.  Die Zeile für neue Datensätze wird jedoch nicht mit anderen Zeilen freigegeben, sodass das Ändern anderer Zeilen sich nicht auf diese Zeile auswirkt.  Beachten Sie auch, dass verschiedene, durch eine freigegebene Zeile dargestellte Zeilen über unterschiedliche Kontextmenüs verfügen können.  Um das korrekte Kontextmenü von der Instanz einer freigegebenen Zeile abzurufen, verwenden Sie die <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A>\-Methode und übergeben den tatsächlichen Index der Zeile.  Falls Sie stattdessen auf die <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A>\-Eigenschaft der freigegebenen Zeile zugreifen, wird der Index \-1 der freigegebenen Zeile verwendet und das falsche Kontextmenü abgerufen.  
  
-   Vermeiden Sie es, die <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=fullName>\-Auflistung zu indizieren.  Durch den direkten Zugriff auf eine Zelle wird die Freigabe der übergeordneten Zeile aufgehoben und eine neue <xref:System.Windows.Forms.DataGridViewRow> instanziiert.  Handler für zellenbezogene Ereignisse empfangen Ereignisargumentobjekte mit Zelleigenschaften, die Sie zum Bearbeiten von Zellen verwenden können, ohne dass dabei Zeilenfreigaben aufgehoben werden.  Sie können auch mithilfe der <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A>\-Eigenschaft die Zeilen\- und Spaltenindizes der aktuellen Zelle abrufen, ohne direkt auf die Zelle zuzugreifen.  
  
-   Vermeiden Sie zellenbasierte Auswahlmodi.  Diese Modi bewirken, dass Zeilenfreigaben aufgehoben werden.  Legen Sie stattdessen die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName>\-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName> oder <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName> fest.  
  
-   Das <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=fullName>\-Ereignis oder das <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=fullName>\-Ereignis sollte nicht behandelt werden.  Diese Ereignisse bewirken, dass Zeilenfreigaben aufgehoben werden.  Vermeiden Sie es auch, die <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=fullName>\-Methode oder die <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=fullName>\-Methode aufzurufen, durch die diese Ereignisse ausgelöst werden.  
  
-   Greifen Sie nicht auf die <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=fullName>\-Auflistung zu, wenn der Wert der <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName>\-Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode>, <xref:System.Windows.Forms.DataGridViewSelectionMode>, <xref:System.Windows.Forms.DataGridViewSelectionMode> oder <xref:System.Windows.Forms.DataGridViewSelectionMode> lautet.  Dadurch wird die Freigabe aller ausgewählten Zeilen aufgehoben.  
  
-   Rufen Sie nicht die <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=fullName>\-Methode auf.  Diese Methode kann bewirken, dass Zeilenfreigaben aufgehoben werden.  
  
-   Vermeiden Sie es, die <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=fullName>\-Methode aufzurufen, wenn der Wert der <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName>\-Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode> lautet.  Dadurch wird die Freigabe aller Zeilen aufgehoben.  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A>\-Eigenschaft oder <xref:System.Windows.Forms.DataGridViewCell.Selected%2A>\-Eigenschaft einer Zelle nicht auf `false` fest, wenn die entsprechende Eigenschaft in der zugehörigen Spalte auf `true` festgelegt ist.  Dadurch wird die Freigabe aller Zeilen aufgehoben.  
  
-   Greifen Sie nicht auf die <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=fullName>\-Eigenschaft zu.  Dadurch wird die Freigabe aller Zeilen aufgehoben.  
  
-   Rufen Sie nicht die `Sort(IComparer)`\-Überladung der <xref:System.Windows.Forms.DataGridView.Sort%2A>\-Methode auf.  Sortierungen mit einem benutzerdefinierten Vergleich führen dazu, dass die Freigabe sämtlicher Zeilen aufgehoben wird.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 [Leistungsoptimierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Virtueller Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)   
 [Datenanzeigemodi im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)   
 [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Festlegen von Standardzellenformaten für das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)   
 [Größenänderungsoptionen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)