---
title: "Gr&#246;&#223;en&#228;nderungsoptionen im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Datenblätter, Größenanpassung von Spalten"
  - "Datenblätter, Größenanpassung von Zeilen"
  - "Datenblätter, Größenanpassungsoptionen"
  - "DataGridView-Steuerelement [Windows Forms], Größenanpassung von Spalten"
  - "DataGridView-Steuerelement [Windows Forms], Größenanpassung von Zeilen"
  - "DataGridView-Steuerelement [Windows Forms], Größenanpassungsoptionen"
ms.assetid: a5620a9c-0d06-41e3-8934-c25ddb16c9e6
caps.latest.revision: 29
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Gr&#246;&#223;en&#228;nderungsoptionen im DataGridView-Steuerelement in Windows Forms
Die Zeilen, Spalten und Header von <xref:System.Windows.Forms.DataGridView> können aus zahlreichen Gründen ihre Größe ändern.  In der folgenden Tabelle sind die Ursachen für eine Größenänderung zusammengefasst.  
  
|Ursache|Beschreibung|  
|-------------|------------------|  
|Größenänderung durch Benutzer|Benutzer können Größenanpassungen vornehmen, indem sie den Unterteiler einer Zeile, einer Spalte oder eines Headers ziehen oder darauf doppelklicken.|  
|Größenänderungen bei Steuerelementen|Im Spaltenfüllmodus ändert sich die Spaltenbreite parallel zur Breite des Steuerelements, beispielsweise, wenn das Steuerelement an das übergeordnete Formular angedockt ist und der Benutzer die Formulargröße ändert.|  
|Änderung von Zellenwerten|In inhaltsbasierten automatischen Größenanpassungsmodi ändert sich die Größe in Anpassung an neue display\-Werte.|  
|Methodenaufruf|Bei der programmgesteuerten inhaltsbasierten Größenänderung können Sie die Größe bequem auf der Grundlage der während des Methodenaufrufs aktuellen Zellenwerte anpassen.|  
|Eigenschafteneinstellung|Sie können auch bestimmte Werte für Höhe und Breite festlegen.|  
  
 Standardeinstellungen: Die Größenänderung durch den Benutzer ist aktiviert, die automatische Größenanpassung deaktiviert, und Zellenwerte, die über die Spaltenbreite hinausgehen, werden abgeschnitten.  
  
 Die folgende Tabelle enthält Szenarien, die Sie zum Anpassen des Standardverhaltens oder zur Verwendung bestimmter Größenänderungsoptionen einsetzen können, um bestimmte Effekte zu erzielen.  
  
|Szenario|Implementierung|  
|--------------|---------------------|  
|Verwenden des Spaltenfüllmodus zur Anzeige von Daten mit ähnlichem Umfang in einer relativ kleinen Anzahl von Spalten, die sich über die gesamte Breite des Steuerelements erstrecken, ohne dass die vertikale Schiebeleiste eingeblendet wird.|Legen Sie die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode> fest.|  
|Verwenden des Spaltenfüllmodus mit display\-Werten unterschiedlicher Größe|Legen Sie die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode> fest.  Initialisieren Sie relative Spaltenbreiten, indem Sie die <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>\-Eigenschaften der Spalte festlegen oder die <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>\-Methode des Steuerelements aufrufen, nachdem das Steuerelement mit Daten gefüllt wurde.|  
|Verwenden des Spaltenfüllmodus mit Werten unterschiedlicher Wichtigkeit|Legen Sie die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode> fest.  Legen Sie hohe <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>\-Werte für Spalten fest, in denen immer einige Daten angezeigt werden müssen, oder verwenden Sie für bestimmte Spalten eine andere Größenänderungsoption als den Füllmodus.|  
|Verwenden des Spaltenfüllmodus, um zu vermeiden, dass der Steuerelementhintergrund angezeigt wird|Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>\-Eigenschaft der letzten Spalte auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> fest, und verwenden Sie für die übrigen Spalten andere Größenänderungsoptionen.  Wenn die übrigen Spalten zu viel Platz in Anspruch nehmen, legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>\-Eigenschaft der letzten Spalte fest.|  
|Anzeigen einer Spalte mit fester Breite, z. B. eines Symbols oder einer ID\-Spalte|Legen Sie für die Spalte <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> und <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> auf <xref:System.Windows.Forms.DataGridViewTriState> fest.  Initialisieren Sie die Breite, indem Sie die <xref:System.Windows.Forms.DataGridViewColumn.Width%2A>\-Eigenschaft festlegen oder die <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>\-Methode des Steuerelements aufrufen, nachdem das Steuerelement mit Daten gefüllt wurde.|  
|Automatische Größenanpassung, sobald sich der Zelleninhalt ändert, um das Abschneiden von Daten zu verhindern und die verfügbare Fläche optimal zu nutzen|Legen Sie eine Eigenschaft für die automatische Größenanpassung auf einen Wert fest, der einen inhaltsbasierten Größenanpassungsmodus darstellt.  Um bei der Verarbeitung großer Datenmengen Leistungseinbußen zu vermeiden, verwenden Sie einen Größenanpassungsmodus, in dem nur angezeigte Zeilen berechnet werden.|  
|Größenanpassung an Werte in angezeigten Zeilen, um Leistungseinbußen bei der Arbeit mit zahlreichen Zeilen zu vermeiden|Verwenden Sie die entsprechenden Enumerationswerte für einen Größenanpassungsmodus mit automatischer oder programmgesteuerter Größenanpassung.  Um die Größe beim Durchführen eines Bildlaufs an Werte in neu angezeigten Zellen anzupassen, rufen Sie eine Größenänderungsmethode in einem <xref:System.Windows.Forms.DataGridView.Scroll>\-Ereignishandler auf.  Um die vom Benutzer durch Doppelklicken ausgeführte Größenänderung anzupassen, damit die neue Größe nur durch Werte in angezeigten Zeilen bestimmt wird, rufen Sie eine Größenänderungsmethode in einem <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick>\-Ereignishandler oder einem <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick>\-Ereignishandler auf.|  
|Anpassen der Größe an den Zelleninhalt nur in bestimmten Situationen, um Leistungseinbußen zu verhindern oder Größenänderungen durch den Benutzer zu ermöglichen|Rufen Sie eine inhaltsbasierte Größenänderungsmethode in einem Ereignishandler auf.  Verwenden Sie beispielsweise das <xref:System.Windows.Forms.DataGridView.DataBindingComplete>\-Ereignis, um die Größe nach dem Binden zu initialisieren, und behandeln Sie das <xref:System.Windows.Forms.DataGridView.CellValidated>\-Ereignis oder das <xref:System.Windows.Forms.DataGridView.CellValueChanged>\-Ereignis, damit Bearbeitungen von Benutzern oder Änderungen in einer gebundenen Datenquelle berücksichtigt werden.|  
|Anpassen der Zeilenhöhe bei mehrzeiligen Zelleninhalten|Stellen Sie sicher, dass die Spaltenbreite für die Anzeige von Textabsätzen geeignet ist, und verwenden Sie eine automatische oder programmgesteuerte inhaltsbasierte Größenanpassung für Zeilen, um die Höhe anzupassen.  Achten Sie zusätzlich darauf, dass Zellen mit mehrzeiligem Inhalt mit dem <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>\-Wert <xref:System.Windows.Forms.DataGridViewTriState> für den Zellenstil angezeigt werden.<br /><br /> In der Regel verwenden Sie einen automatischen Größenanpassungsmodus für Spalten, um die Spaltenbreite beizubehalten, oder legen die Spalten auf eine bestimmte Breite fest, bevor Sie die Zeilenhöhe anpassen.|  
  
## Größenänderung mit der Maus  
 Benutzer können standardmäßig die Größe von Zeilen, Spalten und Headern ändern, für die kein automatischer, auf Zellenwerten basierender Größenanpassungsmodus verwendet wird.  Um zu verhindern, dass Benutzer andere Größenanpassungsmodi verwenden, z. B. den Spaltenfüllmodus, legen Sie eine oder mehrere der folgenden <xref:System.Windows.Forms.DataGridView>\-Eigenschaften fest:  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 Sie können auch verhindern, dass Benutzer die Größe einzelner Zeilen oder Spalten ändern, indem Sie die zugehörigen <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>\-Eigenschaften festlegen.  Der <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>\-Eigenschaftswert basiert standardmäßig auf dem <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>\-Eigenschaftswert für Spalten und dem <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>\-Eigenschaftswert für Zeilen.  Wenn Sie <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> jedoch explizit auf <xref:System.Windows.Forms.DataGridViewTriState> oder <xref:System.Windows.Forms.DataGridViewTriState> festlegen, wird der Steuerelementwert für die jeweilige Zeile oder Spalte jedoch durch den angegebenen Wert überschrieben.  Legen Sie <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> auf <xref:System.Windows.Forms.DataGridViewTriState> fest, um die Vererbung wiederherzustellen.  
  
 Da die Vererbung von Werten durch <xref:System.Windows.Forms.DataGridViewTriState> wiederhergestellt wird, gibt die <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>\-Eigenschaft nur dann einen <xref:System.Windows.Forms.DataGridViewTriState>\-Wert zurück, wenn die Zeile oder Spalte einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement hinzugefügt wurde.  Wenn Sie feststellen müssen, ob der <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>\-Eigenschaftswert einer Zeile oder Spalte vererbt wurde, überprüfen Sie die zugehörige <xref:System.Windows.Forms.DataGridViewElement.State%2A>\-Eigenschaft.  Wenn der <xref:System.Windows.Forms.DataGridViewElement.State%2A>\-Wert das <xref:System.Windows.Forms.DataGridViewElementStates>\-Flag beinhaltet, wurde der <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>\-Eigenschaftswert nicht vererbt.  
  
## Automatische Größenanpassung  
 Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement bietet zwei Arten der automatischen Größenanpassung: Spaltenfüllmodus und inhaltsbasierte automatische Größenanpassung.  
  
 Im Spaltenfüllmodus füllen die sichtbaren Spalten im Steuerelement dessen Anzeigebereich in der vollen Breite aus.  Weitere Informationen zu diesem Modus finden Sie unter [Spaltenfüllmodus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md).  
  
 Sie können Zeilen, Spalten und Header auch so konfigurieren, dass ihre Größe automatisch in Anpassung an den Zelleninhalt geändert wird.  In diesem Fall wird die Größe angepasst, sobald sich der Zelleninhalt ändert.  
  
> [!NOTE]
>  Wenn Sie die Zellenwerte unter Verwendung des virtuellen Modus in einem benutzerdefinierten Datencache verwalten, wird eine automatische Größenanpassung ausgeführt, wenn der Benutzer einen Zellenwert bearbeitet. Wenn Sie einen zwischengespeicherten Wert außerhalb eines <xref:System.Windows.Forms.DataGridView.CellValuePushed>\-Ereignishandlers ändern, wird sie jedoch nicht ausgeführt.  Rufen Sie in diesem Fall die <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A>\-Methode auf, um die Aktualisierung der Zellenanzeige und die Anwendung der aktuellen automatischen Größenanpassungsmodi im Steuerelement zu erzwingen.  
  
 Wenn die inhaltsbasierte automatische Größenanpassung nur für eine Dimension, d. h., für Zeilen, aber nicht für Spalten, oder für Spalten, aber nicht für Zeilen, aktiviert ist und zusätzlich <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> aktiviert ist, wird auch eine Größenanpassung durchgeführt, wenn sich die andere Dimension ändert.  Wenn beispielsweise nur Zeilen, jedoch keine Spalten für die automatische Größenanpassung konfiguriert sind und <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> aktiviert ist, können Benutzer Spaltenunterteiler ziehen, um die Breite einer Spalte zu ändern. Dabei wird die Zeilenhöhe automatisch angepasst, sodass weiterhin der gesamte Zelleninhalt sichtbar ist.  
  
 Wenn Sie sowohl Zeilen als auch Spalten für die inhaltsbasierte automatische Größenanpassung konfigurieren und <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> aktiviert ist, passt das <xref:System.Windows.Forms.DataGridView>\-Steuerelement die Größe an, sobald sich der Zelleninhalt ändert, und verwendet beim Berechnen der neuen Größe ein optimales Verhältnis zwischen Zellenhöhe und \-breite.  
  
 Um den Größenanpassungsmodus für Header, Zeilen und Spalten zu konfigurieren, durch die der Wert des Steuerelements nicht überschrieben wird, legen Sie eine oder mehrere der folgenden <xref:System.Windows.Forms.DataGridView>\-Eigenschaften fest:  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Um den Größenanpassungsmodus des Steuerelements für eine einzelne Spalte zu überschreiben, legen Sie deren <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>\-Eigenschaft auf einen anderen Wert als <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> fest.  Der Größenanpassungsmodus für eine Spalte wird von deren <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A>\-Eigenschaft bestimmt.  Der Wert dieser Eigenschaft basiert auf dem <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>\-Eigenschaftswert der Spalte, sofern er nicht <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> entspricht. In diesem Fall wird der <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>\-Wert des Steuerelements geerbt.  
  
 Verwenden Sie die inhaltsbasierte automatische Größenanpassung mit Vorsicht, wenn Sie mit großen Datenmengen arbeiten.  Um Leistungseinbußen zu vermeiden, sollten Sie automatische Größenanpassungsmodi verwenden, in denen die Größe nur auf der Grundlage der angezeigten Zeilen berechnet wird, anstatt jede Zeile im Steuerelement zu analysieren.  Optimale Leistung erzielen Sie stattdessen mit der programmgesteuerten Größenanpassung, bei der die Größe in bestimmten Situationen angepasst werden kann, beispielsweise direkt nach dem Laden neuer Daten.  
  
 Inhaltsbasierte automatische Größenanpassungsmodi haben keine Auswirkungen auf Zeilen, Spalten oder Header, die ausgeblendet wurden, indem die <xref:System.Windows.Forms.DataGridViewBand.Visible%2A>\-Eigenschaft der Zeile oder Spalte bzw. die <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A>\-Eigenschaft oder <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A>\-Eigenschaft des Steuerelements auf `false` festgelegt wurde.  Wenn eine Spalte ausgeblendet wurde, nachdem ihre Größe in Anpassung an einen umfangreichen Zellenwert automatisch geändert wurde, wird die Größe der ausgeblendeten Spalte nicht geändert, wenn die Zeile mit dem umfangreichen Zellenwert gelöscht wird.  Es tritt keine automatische Größenanpassung auf, wenn sich die Sichtbarkeit von Daten ändert. Wenn Sie die <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A>\-Eigenschaft der Spalte wieder in `true` ändern, wird daher keine Neuberechnung der Spaltengröße auf der Grundlage ihres aktuellen Inhalts erzwungen.  
  
 Auf Zeilen, Spalten und Header wirkt sich die programmgesteuerte inhaltsbasierte Größenanpassung unabhängig von deren Sichtbarkeit aus.  
  
## Programmgesteuerte Größenanpassung  
 Wenn die automatische Größenanpassung deaktiviert ist, können Sie die exakte Breite oder Höhe von Zeilen, Spalten oder Headern mithilfe der folgenden Eigenschaften programmgesteuert festlegen:  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=fullName>  
  
 Mit den folgenden Methoden können Sie die Größe von Zeilen, Spalten und Headern auch programmgesteuert an ihren Inhalt anpassen:  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 Mit diesen Methoden wird die Größe von Zeilen, Spalten oder Headern einmalig geändert, anstatt sie für die kontinuierliche Größenanpassung zu konfigurieren.  Die neuen Größen werden automatisch so berechnet, dass der gesamte Zelleninhalt angezeigt wird, ohne dass Daten abgeschnitten werden.  Wenn Sie die Größe von Spalten, die über den <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A>\-Eigenschaftswert <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> verfügen, programmgesteuert ändern, werden jedoch die berechneten inhaltsbasierten Breiten verwendet, um die <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>\-Eigenschaftswerte der Spalten proportional anzupassen. Anschließend werden die tatsächlichen Spaltenbreiten entsprechend diesen neuen Proportionen berechnet, sodass der verfügbare Anzeigebereich des Steuerelements von der Gesamtheit der Spalten ausgefüllt wird.  
  
 Die programmgesteuerte Größenanpassung ist hilfreich, um eine Leistungsminderung bei kontinuierlicher Größenanpassung zu vermeiden.  Außerdem ist sie geeignet, um eine Anfangsgröße für Zeilen, Spalten und Header bereitzustellen, deren Größe vom Benutzer geändert werden kann, sowie für den Spaltenfüllmodus.  
  
 In der Regel werden die programmgesteuerten Größenänderungsmethoden in bestimmten Situationen aufgerufen.  Beispielsweise, wenn Sie die Größe sämtlicher Spalten direkt nach dem Laden von Daten oder eine bestimmte Zeile nach dem Ändern eines bestimmten Zellenwerts programmgesteuert ändern möchten.  
  
## Anpassen des Verhaltens bei der inhaltsbasierten Größenanpassung  
 Beim Arbeiten mit abgeleiteten <xref:System.Windows.Forms.DataGridView>\-Zellen\-, \-Zeilen\- und \-Spaltentypen können Sie das Größenänderungsverhalten anpassen, indem Sie die Methode <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=fullName>, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=fullName> oder <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=fullName> überschreiben oder Überladungen für geschützte Größenänderungsmethoden in einem abgeleiteten <xref:System.Windows.Forms.DataGridView>\-Steuerelement aufrufen.  Die Überladungen für geschützte Größenänderungsmethoden sind für die paarweise Ausführung ausgelegt, um ein ideales Verhältnis zwischen Zellenhöhe und \-breite zu erzielen und übermäßig breite oder hohe Zellen zu vermeiden.  Wenn Sie beispielsweise die `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)`\-Überladung der <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>\-Methode aufrufen und den Wert `false` für den <xref:System.Boolean>\-Parameter übergeben, berechnet die Überladung die ideale Höhe und Breite für Zellen in der Zeile, passt jedoch nur die Zeilenhöhe an.  Anschließend müssen Sie die <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>\-Methode aufrufen, um die Spaltenbreite auf den berechneten Idealwert einzustellen.  
  
## Inhaltsbasierte Größenäderungsoptionen  
 Die Enumerationen, die von den Eigenschaften und Methoden für die Größenänderung verwendet werden, verfügen über ähnliche Werte für die inhaltsbasierte Größenanpassung.  Mit diesen Werten können Sie die Zellen einschränken, die zur Berechnung der bevorzugten Größen verwendet werden.  Bei allen Enumerationen für die Größenanpassung werden Berechnungen bei Werten mit Namen, die sich auf angezeigte Zellen beziehen, auf Zellen in angezeigten Zeilen beschränkt.  Das Ausschließen von Zeilen erweist sich als hilfreich, um Leistungseinbußen bei der Bearbeitung vieler Zeilen zu vermeiden.  Sie können Berechnungen auch auf Zellenwerte in Headerzellen oder außerhalb von Headerzellen beschränken.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>   
 <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>   
 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>   
 [Größenanpassung bei Spalten und Zeilen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)   
 [Spaltenfüllmodus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Festlegen der Größenanpassungsmodi des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)