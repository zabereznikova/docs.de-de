---
title: Größen Anpassungsoptionen im DataGridView-Steuerelement
description: Erfahren Sie mehr Übergrößen Anpassungsoptionen im Windows Forms DataGridView-Steuerelement. DataGridView-Zeilen,-Spalten und-Header ändern die Größe infolge verschiedener vorkommen.
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sizing
- data grids [Windows Forms], column sizing
- DataGridView control [Windows Forms], column sizing
- DataGridView control [Windows Forms], sizing options
- data grids [Windows Forms], row sizing
- data grids [Windows Forms], sizing options
ms.assetid: a5620a9c-0d06-41e3-8934-c25ddb16c9e6
ms.openlocfilehash: 8ddf72c412db74df35bc3f035ff05d1e7e9738d1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613721"
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms
<xref:System.Windows.Forms.DataGridView>Zeilen, Spalten und Header können die Größe aufgrund vieler verschiedener vorkommen ändern. In der folgenden Tabelle sind diese Vorkommen aufgeführt.  
  
|Vorkommen|BESCHREIBUNG|  
|----------------|-----------------|  
|Benutzer Größe ändern|Benutzer können Größenanpassungen vornehmen, indem Sie Zeilen-, Spalten-oder Header unter Teiler ziehen oder doppelklicken.|  
|Größenänderung des Steuer Elements|Im Spalten Füll Modus ändern sich die Spaltenbreite, wenn sich die Breite des Steuer Elements ändert. beispielsweise, wenn das Steuerelement an sein übergeordnetes Formular angedockt ist und der Benutzer die Größe des Formulars ändert.|  
|Zell Wertänderung|In den Modi für die Inhalts basierte automatische Größenanpassung ändern sich Größen in neue Anzeigewerte.|  
|Methodenaufruf|Mithilfe der programmgesteuerten Inhalts basierten Größenänderung können Sie auf der Grundlage der Zellwerte zum Zeitpunkt des Methoden Aufrufes die opportunistischen Größenanpassungen vornehmen.|  
|Eigenschafts Einstellung|Sie können auch bestimmte Werte für Höhe und Breite festlegen.|  
  
 Standardmäßig ist die Größenänderung von Benutzern aktiviert, die automatische Größenanpassung ist deaktiviert, und Zellen Werte, die breiter als ihre Spalten sind, werden abgeschnitten.  
  
 In der folgenden Tabelle sind Szenarien aufgeführt, mit denen Sie das Standardverhalten anpassen oder bestimmte Größen Anpassungsoptionen verwenden können, um bestimmte Effekte zu erzielen.  
  
|Szenario|Implementierung|  
|--------------|--------------------|  
|Verwenden Sie den Spalten Füll Modus zum Anzeigen von ähnlich großen Daten in einer relativ kleinen Anzahl von Spalten, die die gesamte Breite des Steuer Elements belegen, ohne die horizontale Schiebe Leiste anzuzeigen.|Legen Sie die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> -Eigenschaft auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>fest.|  
|Verwenden Sie den Spalten Füll Modus mit Anzeige Werten unterschiedlicher Größen.|Legen Sie die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> -Eigenschaft auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>fest. Initialisieren Sie die relative Spaltenbreite, indem Sie die Spalten <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> Eigenschaften festlegen oder die Control-Methode aufrufen, <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> nachdem Sie das Steuerelement mit Daten gefüllt haben.|  
|Verwenden Sie den Spalten Füll Modus mit Werten unterschiedlicher Wichtigkeit.|Legen Sie die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> -Eigenschaft auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>fest. Legen <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> Sie große Werte für Spalten fest, die immer einige Ihrer Daten anzeigen müssen, oder verwenden Sie eine andere Optionen als den Füll Modus für bestimmte Spalten.|  
|Verwenden Sie den Spalten Füll Modus, um den Hintergrund des Steuer Elements nicht anzuzeigen.|Legen <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> Sie die-Eigenschaft der letzten Spalte auf fest, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> und verwenden Sie andere Größen Anpassungsoptionen für die anderen Spalten. Wenn für die anderen Spalten zu viel verfügbarer Speicherplatz verwendet wird, legen Sie die- <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> Eigenschaft der letzten Spalte fest.|  
|Zeigt eine Spalte mit fester Breite an, z. b. eine Symbol-oder ID-Spalte.|Legen <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> Sie <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> für die Spalte auf und auf fest <xref:System.Windows.Forms.DataGridViewTriState.False> . Initialisieren Sie die Breite, indem Sie die- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> Eigenschaft festlegen oder die Control-Methode aufrufen, <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> nachdem Sie das Steuerelement mit Daten gefüllt haben.|  
|Passen Sie Größen automatisch an, wenn sich Zellen Inhalte ändern, um Clipping zu vermeiden und die Verwendung von Speicherplatz zu optimieren.|Legen Sie eine Eigenschaft für die automatische Größenanpassung auf einen Wert fest, der einen Inhalts basierten Größen Anpassungsmodus darstellt. Um eine Leistungs Einbuße bei der Arbeit mit großen Datenmengen zu vermeiden, verwenden Sie einen Größen Anpassungsmodus, der nur angezeigte Zeilen berechnet.|  
|Passen Sie die Größe an Werte in angezeigten Zeilen an, um beim Arbeiten mit vielen Zeilen Leistungseinbußen zu vermeiden.|Verwenden Sie die entsprechenden Aufzählungs Modus-Enumerationswerte mit automatischer oder Programm gesteuerter Größenänderung. Zum Anpassen von Größen, um Werte in neu angezeigte Zeilen beim Scrollen anzupassen <xref:System.Windows.Forms.DataGridView.Scroll> Zum Anpassen der Größenänderung des Benutzers, sodass nur Werte in den angezeigten Zeilen die neuen Größen bestimmen, wird eine Größen Anpassungs Methode in einem <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> - <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick> Ereignishandler oder einem-Ereignishandler aufgerufen.|  
|Passen Sie die Größe an den Zellen Inhalt nur zu bestimmten Zeiten an, um Leistungseinbußen zu vermeiden oder die Größenänderung von Benutzern zu aktivieren.|Ruft eine Inhalts basierte resisierungsmethode in einem Ereignishandler auf. Verwenden Sie z. b. das <xref:System.Windows.Forms.DataGridView.DataBindingComplete> -Ereignis, um Größen nach der Bindung zu initialisieren, und behandeln Sie das-Ereignis oder das-Ereignis, um <xref:System.Windows.Forms.DataGridView.CellValidated> <xref:System.Windows.Forms.DataGridView.CellValueChanged> Größen anzupassen, um Benutzer Bearbeitungen oder Änderungen in einer gebundenen Datenquelle|  
|Zeilenhöhe für mehrzeiligen Zellinhalt anpassen.|Stellen Sie sicher, dass die Spaltenbreite zum Anzeigen von Text Absätzen geeignet ist, und verwenden Sie die automatische oder programmgesteuerte Inhalts basierte Zeilengröße, um die Höhe anzupassen. Stellen Sie außerdem sicher, dass Zellen mit mehrzeiligen Inhalten mit einem <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> zellstilwert von angezeigt werden <xref:System.Windows.Forms.DataGridViewTriState.True> .<br /><br /> In der Regel verwenden Sie einen automatischen Spaltengrößen Änderungs Modus, um die Spaltenbreiten beizubehalten oder Sie auf bestimmte breitenfest zulegen, bevor die Zeilenhöhe angepasst wird.|  
  
## <a name="resizing-with-the-mouse"></a>Ändern der Größe mit der Maus  
 Standardmäßig können Benutzer die Größe von Zeilen, Spalten und Headern ändern, für die kein automatischer Größen Anpassungsmodus basierend auf Zellwerten verwendet wird. Legen Sie eine oder mehrere der folgenden Eigenschaften fest, um zu verhindern, dass die Größe der Benutzer in anderen Modi geändert wird, z. b. im Spalten Füll Modus <xref:System.Windows.Forms.DataGridView> :  
  
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 Sie können auch verhindern, dass Benutzer die Größe einzelner Zeilen oder Spalten ändern, indem Sie deren <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschaften festlegen. Der <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschafts Wert basiert standardmäßig auf dem <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> Eigenschafts Wert für Spalten und dem <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> Eigenschafts Wert für Zeilen. Wenn Sie explizit <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> auf <xref:System.Windows.Forms.DataGridViewTriState.True> oder festlegen <xref:System.Windows.Forms.DataGridViewTriState.False> , überschreibt der angegebene Wert den Wert des Steuer Elements für diese Zeile oder Spalte. Legen <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Sie auf fest, <xref:System.Windows.Forms.DataGridViewTriState.NotSet> um die Vererbung wiederherzustellen.  
  
 Da <xref:System.Windows.Forms.DataGridViewTriState.NotSet> die Vererbung des Werts wiederherstellt, gibt die- <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschaft niemals einen Wert zurück, <xref:System.Windows.Forms.DataGridViewTriState.NotSet> es sei denn, die Zeile oder Spalte wurde einem-Steuerelement hinzugefügt <xref:System.Windows.Forms.DataGridView> . Wenn Sie bestimmen müssen, ob der <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschafts Wert einer Zeile oder Spalte vererbt wird, überprüfen Sie die zugehörige- <xref:System.Windows.Forms.DataGridViewElement.State%2A> Eigenschaft. Wenn der- <xref:System.Windows.Forms.DataGridViewElement.State%2A> Wert das- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet> Flag enthält, wird der- <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschafts Wert nicht geerbt.  
  
## <a name="automatic-sizing"></a>Automatische Größenanpassung  
 Es gibt zwei Arten der automatischen Größenanpassung im <xref:System.Windows.Forms.DataGridView> -Steuerelement: Spalten Füll Modus und Inhalts basierte automatische Größenanpassung.  
  
 Der Spalten Füll Modus bewirkt, dass die sichtbaren Spalten im-Steuerelement die Breite des Anzeige Bereichs des-Steuer Elements ausfüllen. Weitere Informationen zu diesem Modus finden Sie unter [Spalten Füll Modus im Windows Forms DataGridView-Steuer](column-fill-mode-in-the-windows-forms-datagridview-control.md)Element.  
  
 Außerdem können Sie Zeilen, Spalten und Header so konfigurieren, dass ihre Größe automatisch an Ihren Zellinhalt angepasst wird. In diesem Fall tritt bei jeder Änderung von Zell Inhalten eine Größenanpassung auf.  
  
> [!NOTE]
> Wenn Sie Zellwerte in einem benutzerdefinierten Daten Cache mithilfe des virtuellen Modus verwalten, erfolgt die automatische Größenanpassung, wenn der Benutzer einen Zellwert bearbeitet, aber nicht, wenn Sie einen zwischengespeicherten Wert außerhalb eines- <xref:System.Windows.Forms.DataGridView.CellValuePushed> Ereignis Handlers ändern. Aufrufen Sie in diesem Fall die-Methode, um zu erzwingen, dass <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> das Steuerelement die Zellen Anzeige aktualisiert und die aktuellen automatischen Größen Anpassungs Modi anwendet.  
  
 Wenn die Inhalts basierte automatische Größenanpassung nur für eine einzelne Dimension aktiviert ist – d. h. für Zeilen, aber nicht für Spalten oder für Spalten, jedoch nicht für Zeilen – und <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> auch aktiviert ist, wird die Größenanpassung auch immer dann durchgeführt, wenn die andere Dimension geändert wird. Wenn z. b. Zeilen, aber keine Spalten für die automatische Größenanpassung konfiguriert sind und <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> aktiviert ist, können Benutzer Spalten Teiler ziehen, um die Breite einer Spalte zu ändern, und die Zeilenhöhe wird automatisch angepasst, sodass der Inhalt der Zelle weiterhin vollständig angezeigt wird.  
  
 Wenn Sie sowohl Zeilen als auch Spalten für die Inhalts basierte automatische Größenanpassung konfigurieren und <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> aktiviert ist, passt das Steuerelement die <xref:System.Windows.Forms.DataGridView> Größe immer dann an, wenn sich der Zellen Inhalt geändert hat und bei der Berechnung neuer Größen ein ideales Zell Höhen-zu-Breite-Verhältnis verwendet wird.  
  
 Legen Sie eine oder mehrere der folgenden Eigenschaften fest, um den Größen Anpassungsmodus für Header und Zeilen und für Spalten zu konfigurieren, die den Steuerelement Wert nicht überschreiben <xref:System.Windows.Forms.DataGridView> :  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Legen Sie die- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> Eigenschaft auf einen anderen Wert als fest, um den Spaltengrößen Modus des Steuer Elements für eine einzelne Spalte zu überschreiben <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet> . Der Größen Anpassungsmodus für eine Spalte wird tatsächlich durch die- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> Eigenschaft bestimmt. Der Wert dieser Eigenschaft basiert auf dem <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> Eigenschafts Wert der Spalte, es sei denn, dieser Wert ist <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet> . in diesem Fall wird der Wert des Steuer Elements <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> geerbt.  
  
 Verwenden Sie bei der Arbeit mit großen Datenmengen die Inhalts basierte automatische Größenänderung mit Bedacht. Um Leistungseinbußen zu vermeiden, verwenden Sie die automatischen Größen Anpassungs Modi, die die Größen nur auf der Grundlage der angezeigten Zeilen berechnen, anstatt jede Zeile im Steuerelement zu analysieren. Verwenden Sie für maximale Leistung stattdessen die programmgesteuerte Größenänderung, damit Sie die Größe zu bestimmten Zeitpunkten ändern können, beispielsweise unmittelbar nach dem Laden neuer Daten.  
  
 Inhalts basierte automatische Größen Anpassungs Modi wirken sich nicht auf Zeilen, Spalten oder Header aus, die Sie ausgeblendet haben, indem Sie die Zeilen-oder Spalten <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> Eigenschaft oder das-Steuerelement oder die- <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> Eigenschaften auf festlegen `false` . Wenn eine Spalte z. b. ausgeblendet wird, nachdem Sie automatisch an einen großen Zellwert angepasst wurde, ändert sich die Größe der ausgeblendeten Spalte nicht, wenn die Zeile, die den großen Zellwert enthält, gelöscht wird. Die automatische Größenanpassung tritt nicht auf, wenn sich die Sichtbarkeit ändert. Wenn Sie also die Spalten <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> Eigenschaft wieder in ändern, `true` wird Sie nicht gezwungen, ihre Größe basierend auf dem aktuellen Inhalt neu zu berechnen.  
  
 Die programmgesteuerte Anpassung der Inhalts basierten Größe wirkt sich auf Zeilen, Spalten und Header unabhängig von ihrer Sichtbarkeit aus.  
  
## <a name="programmatic-resizing"></a>Programmgesteuerte Größe ändern  
 Wenn die automatische Größenanpassung deaktiviert ist, können Sie die exakte Breite oder Höhe von Zeilen, Spalten oder Headern mit den folgenden Eigenschaften Programm gesteuert festlegen:  
  
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
  
 Mithilfe der folgenden Methoden können Sie die Größe von Zeilen, Spalten und Headern auch Programm gesteuert ändern.  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 Diese Methoden ändern die Größe der Zeilen, Spalten oder Header einmal, anstatt Sie für die kontinuierliche Größenänderung zu konfigurieren. Die neuen Größen werden automatisch so berechnet, dass alle Zell Inhalte ohne Clipping angezeigt werden. Wenn Sie eine programmgesteuerte Größenänderung von Spalten mit den <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> Eigenschafts Werten von vornehmen, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> werden die berechneten Inhalts basierten breiten jedoch verwendet, um die Spalten <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> Eigenschaftswerte proportional anzupassen. die Spaltenbreiten werden dann entsprechend diesen neuen Proportionen berechnet, sodass alle Spalten den verfügbaren Anzeigebereich des Steuer Elements ausfüllen.  
  
 Die programmgesteuerte Änderung ist hilfreich, um Leistungseinbußen bei der kontinuierlichen Anpassung zu vermeiden. Außerdem ist es hilfreich, die Anfangs Größen für Zeilen, Spalten und Header von Benutzern, die sich ändern können, und für den Spalten Füll Modus bereitzustellen.  
  
 Sie werden in der Regel die programmgesteuerten Ändern der Größe zu bestimmten Zeiten aufruft. Beispielsweise können Sie Programm gesteuert die Größe aller Spalten direkt nach dem Laden von Daten ändern, oder Sie können eine bestimmte Zeile Programm gesteuert ändern, nachdem ein bestimmter Zellwert geändert wurde.  
  
## <a name="customizing-content-based-sizing-behavior"></a>Anpassen des Inhalts basierten Größen Anpassungs Verhaltens  
 Sie können das Größen Änderungs Verhalten beim Arbeiten mit abgeleiteten <xref:System.Windows.Forms.DataGridView> Zellen-, Zeilen-und Spaltentypen anpassen, indem Sie die <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType> Methoden, oder <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType> überschreiben oder die über Ladungen der geschützten Größen Änderungs Methode in einem abgeleiteten Steuerelement aufrufen <xref:System.Windows.Forms.DataGridView> . Die geschützten Methoden Überladungen für die Größenänderung sind so konzipiert, dass Sie paarweise verwendet werden können, um eine optimale Zell Höhen-zu-Breite-Quote zu erzielen und übermäßig große oder große Zellen zu vermeiden. Wenn Sie z. b. die `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` -Überladung der <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> -Methode aufrufen und den Wert `false` für den- <xref:System.Boolean> Parameter übergeben, berechnet die Überladung die ideale Höhe und Breite für Zellen in der Zeile, aber die Zeilen Höhen werden nur angepasst. Anschließend müssen Sie die- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> Methode aufzurufen, um die Spaltenbreite an das berechnete ideal anzupassen.  
  
## <a name="content-based-sizing-options"></a>Optionen für die Inhalts basierte Größenanpassung  
 Die von der Größenanpassung von Eigenschaften und Methoden verwendeten Enumerationen haben ähnliche Werte für die Inhalts basierte Größenanpassung. Mit diesen Werten können Sie einschränken, welche Zellen verwendet werden, um die bevorzugten Größen zu berechnen. Bei allen Größen Anpassungs Enumerationen beschränken Werte mit Namen, die auf angezeigte Zellen verweisen, ihre Berechnungen auf Zellen in angezeigten Zeilen. Das Ausschließen von Zeilen ist hilfreich, um eine Leistungs Einbuße zu vermeiden, wenn Sie mit einer großen Anzahl von Zeilen arbeiten. Sie können auch Berechnungen auf Zellwerte in Header-oder nicht-Header Zellen beschränken.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [Spaltenfüllmodus im DataGridView-Steuerelement in Windows Forms](column-fill-mode-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Festlegen der Größenanpassungsmodi des DataGridView-Steuerelements in Windows Forms](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
