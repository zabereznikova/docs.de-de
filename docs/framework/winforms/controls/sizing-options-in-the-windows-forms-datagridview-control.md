---
title: Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sizing
- data grids [Windows Forms], column sizing
- DataGridView control [Windows Forms], column sizing
- DataGridView control [Windows Forms], sizing options
- data grids [Windows Forms], row sizing
- data grids [Windows Forms], sizing options
ms.assetid: a5620a9c-0d06-41e3-8934-c25ddb16c9e6
ms.openlocfilehash: a236289939b9355e961ce1bfc9a7e0ff5349a95a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717907"
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms
<xref:System.Windows.Forms.DataGridView> Zeilen, Spalten und Header können aus vielen Gründen ihre Größe ändern. Die folgende Tabelle zeigt diese vorkommen.  
  
|Vorkommen|Beschreibung|  
|----------------|-----------------|  
|Benutzer ändern|Benutzer können die Größe Anpassungen vornehmen, durch Ziehen oder Doppelklicken auf Zeilen-, Spalten- oder Header Zeilenunterteiler.|  
|Steuerelement, Größenänderung|Ändern der Spaltenbreite im Spaltenfüllmodus Wenn die Breite des Steuerelements geändert wird; beispielsweise beim übergeordneten Formulars und dem Benutzer das Steuerelement angedockt ist, wird das Formular.|  
|Änderung eines Werts der Zelle|Ändern Sie in Modi zur Größenänderung inhaltsbasierte Größen entsprechend der neuen Werte ein.|  
|Methodenaufruf|Programmgesteuerten größenanpassung inhaltsbasierte können Sie anhand der Werte der Zellen zum Zeitpunkt des Methodenaufrufs opportunistische Größe-Anpassungen vornehmen.|  
|Einstellung der Eigenschaft|Sie können auch bestimmte Höhe und Breitenwerte festlegen.|  
  
 Standardmäßig Ändern der Größe von Benutzer aktiviert ist, automatische Größenänderung ist deaktiviert und Zellwerte, die größer sind als ihre Spalten werden abgeschnitten.  
  
 In der folgende Tabelle werden die Szenarien, die Sie verwenden können, um das Standardverhalten anzupassen oder bestimmte Optionen zu verwenden, um bestimmte Effekte zu erzielen.  
  
|Szenario|Implementierung|  
|--------------|--------------------|  
|Spaltenfüllmodus verwenden, für die Anzeige von Größe auf ähnliche Weise Daten in eine relativ kleine Anzahl von Spalten, die die gesamte Breite des Steuerelements zu belegen, ohne dass die horizontale Bildlaufleiste angezeigt.|Legen Sie die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> -Eigenschaft auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>fest.|  
|Verwenden von Spaltenfüllmodus mit Anzeigewerte mit unterschiedlichen Größen erstellen.|Legen Sie die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> -Eigenschaft auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>fest. Relative Spaltenbreiten zu initialisieren, indem Sie die Spalte <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> Eigenschaften oder durch Aufrufen des Steuerelements <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> -Methode auf, nachdem das Steuerelement mit Daten gefüllt.|  
|Verwenden Sie Spaltenfüllmodus mit Werten von unterschiedliche Bedeutung.|Legen Sie die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> -Eigenschaft auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>fest. Legen Sie große <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> Werte für Spalten, die immer einige ihrer Daten angezeigt werden müssen, oder verwenden die gewünschte Option anders als im Modus für bestimmte Spalten ausfüllen.|  
|Verwenden Sie Spaltenfüllmodus, um zu vermeiden, den Hintergrund des Steuerelements angezeigt.|Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> Eigenschaft der letzten Spalte, die <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> und anderen Größenanpassungsoptionen zur für die anderen Spalten verwenden. Wenn die anderen Spalten zu viel des verfügbaren Speicherplatzes verwenden, legen die <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> -Eigenschaft der letzten Spalte.|  
|Zeigt eine Spalte mit fester Breite, z. B. ein Symbol oder eine ID-Spalte.|Legen Sie <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> zu <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> und <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> zu <xref:System.Windows.Forms.DataGridViewTriState.False> für die Spalte. Initialisieren Sie die Breite durch Festlegen der <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> Eigenschaft oder durch Aufrufen des Steuerelements <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> -Methode auf, nachdem das Steuerelement mit Daten gefüllt.|  
|Stellen Sie die Größe automatisch Zelleninhalt Änderung um dies zu vermeiden und die Verwendung des Speicherplatzes zu optimieren.|Legen Sie eine automatische Größenänderung-Eigenschaft auf einen Wert, der einen inhaltsbasierten Größenanpassungsmodus darstellt. Um eine Leistungseinbuße zu vermeiden, bei der Arbeit mit großen Datenmengen, verwenden Sie einen Größenanpassungsmodus, der nur die angezeigten Zeilen berechnet.|  
|Stellen Sie die Größe um die Werte in Zeilen angezeigt, um Leistungseinbußen zu verhindern, bei der Arbeit mit vielen Zeilen passen.|Verwenden Sie die entsprechende Größenänderungsmodus Enumeration-Werte, mit der automatischen oder eine programmgesteuerte Ändern der Größe. Rufen Sie zum Anpassen der Größe an, dass beim Durchführen eines Bildlaufs in Zeilen neu angezeigt Werte eine Größenänderungsmethode in einem <xref:System.Windows.Forms.DataGridView.Scroll> -Ereignishandler. Anpassen von Benutzer doppelklicken Sie auf Ändern der Größe, damit nur die Werte in Zeilen angezeigt, die neuen Größen, ermitteln rufen eine Größenänderungsmethode in einem <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> oder <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick> -Ereignishandler.|  
|Passen Sie die Größe an Zelleninhalt nur zu bestimmten Zeiten, um Leistungseinbußen zu verhindern oder Ändern der Größe von Benutzer zu ermöglichen.|Rufen Sie eine inhaltsbasierte Größenänderungsmethode in einem Ereignishandler. Beispielsweise verwenden die <xref:System.Windows.Forms.DataGridView.DataBindingComplete> Ereignis, um die Größe nach der Bindung zu initialisieren und zu behandeln die <xref:System.Windows.Forms.DataGridView.CellValidated> oder <xref:System.Windows.Forms.DataGridView.CellValueChanged> Ereignis anpassen Größen zur Kompensierung benutzerbearbeitungen oder Änderungen in einer gebundenen Datenquelle.|  
|Passen Sie die Zeilenhöhe für mehrzeiligen Zelleninhalt.|Stellen Sie sicher, dass die Spaltenbreite für die Anzeige der Absätze mit Text geeignet sind und die größenanpassung von automatischen oder eine programmgesteuerte inhaltsbasierte Zeilen verwenden, um anzupassen, das die Höhen. Stellen Sie außerdem sicher, dass Zellen mit mehrzeiligen Inhalt angezeigt werden, mithilfe einer <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> Style-Wert der Zelle <xref:System.Windows.Forms.DataGridViewTriState.True>.<br /><br /> Verwenden Sie einen automatischen Größenanpassungsmodus in der Regel um Spaltenbreite beizubehalten, oder legen diese auf eine bestimmte Breite aus, bevor die Zeilenhöhen angepasst werden.|  
  
## <a name="resizing-with-the-mouse"></a>Ändern der Größe, mit der Maus  
 Standardmäßig können Größe der Zeilen, Spalten und Header, die eine automatische größenanpassungen basierend auf den Werten der Zelle nicht verwenden. Um zu verhindern, dass Benutzer andere Größenanpassungsmodi verwenden, z. B. Spaltenfüllmodus legen Sie eine oder mehrere der folgenden <xref:System.Windows.Forms.DataGridView> Eigenschaften:  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 Sie können auch verhindern, dass Benutzer ändern einzelner Zeilen oder Spalten durch Festlegen der Größe ihrer <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschaften. In der Standardeinstellung die <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschaftswert basiert auf der <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> Eigenschaftswert für die Spalten und die <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> Wert der Eigenschaft für Zeilen. Wenn Sie explizit festlegen <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> zu <xref:System.Windows.Forms.DataGridViewTriState.True> oder <xref:System.Windows.Forms.DataGridViewTriState.False>jedoch den angegebenen Wert überschrieben, die der Steuerelementwert für diese Zeile oder Spalte ist. Legen Sie <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> zu <xref:System.Windows.Forms.DataGridViewTriState.NotSet> um die Vererbung wiederherzustellen.  
  
 Da <xref:System.Windows.Forms.DataGridViewTriState.NotSet> stellt die Vererbung von Eigenschaftswerten, die <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschaft wird nie zurückgegeben. ein <xref:System.Windows.Forms.DataGridViewTriState.NotSet> Wert, es sei denn, die Zeile oder Spalte nicht hinzugefügt wurde eine <xref:System.Windows.Forms.DataGridView> Steuerelement. Wenn Sie ermitteln müssen, ob die <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschaftswert, der eine Zeile oder Spalte geerbt wird, überprüfen Sie die <xref:System.Windows.Forms.DataGridViewElement.State%2A> Eigenschaft. Wenn die <xref:System.Windows.Forms.DataGridViewElement.State%2A> Wert enthält die <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet> Flag, das <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschaftswert wird nicht geerbt.  
  
## <a name="automatic-sizing"></a>Automatische Größenänderung  
 Es gibt zwei Arten der automatischen größenanpassung in die <xref:System.Windows.Forms.DataGridView> Control: Spaltenfüllmodus und Content-basierte automatische größenanpassung.  
  
 Spaltenfüllmodus bewirkt, dass die sichtbaren Spalten im Steuerelement, um die Breite des Anzeigebereichs des Steuerelements zu füllen. Weitere Informationen zu diesen Modus, finden Sie unter [füllen Spalten-Modus im DataGridView-Steuerelement in Windows Forms](column-fill-mode-in-the-windows-forms-datagridview-control.md).  
  
 Sie können auch Zeilen, Spalten und Header automatisch anpasst, deren Größe an ihren Inhalt der Zelle konfigurieren. In diesem Fall wird die Änderung der Zelleninhalt Größe angepasst.  
  
> [!NOTE]
>  Wenn Sie die Werte von Zellen in einem benutzerdefinierten Datencache, die Verwendung des virtuellen Modus verwalten, automatische größenanpassungen auftritt, wenn der Benutzer einen Zellwert bearbeitet, jedoch tritt nicht auf, wenn Sie einen zwischengespeicherten Wert außerhalb des ändern eine <xref:System.Windows.Forms.DataGridView.CellValuePushed> -Ereignishandler. In diesem Fall rufen die <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> Methode, um das Steuerelement für die Zellenanzeige zu aktualisieren und Anwenden der aktuellen automatischen Größenanpassungsmodi erzwingen.  
  
 Wenn Content-basierte automatische größenanpassung für nur eine Dimension aktiviert ist, d. h. für die Zeilen jedoch nicht für Spalten oder Spalten, jedoch keine Zeilen – und <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> ist ebenfalls aktiviert, Größe Anpassung tritt auch auf, wenn sich die andere Abmessung ändert. Angenommen, für die automatische größenanpassung Zeilen jedoch nicht für Spalten konfiguriert sind und <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> ist aktiviert, können die Benutzer Spaltenunterteiler zum Ändern der Breite einer Spalte ziehen und Zeilenhöhen werden automatisch angepasst, sodass Zelleninhalt weiterhin vollständig angezeigt werden.  
  
 Wenn Sie Zeilen und Spalten für die automatische größenanpassung inhaltsbasierte konfigurieren und <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> aktiviert ist, die <xref:System.Windows.Forms.DataGridView> Steuerelement passt Größen, wenn Zelleninhalt geändert und eine ideale Zelle Höhe und Breite Verhältnis beim Berechnen der neuen Größe verwendet.  
  
 Um den Größenänderungsmodus für Headers- und Rows und Spalten, die nicht den Wert im Steuerelement außer Kraft setzen zu konfigurieren, legen Sie eine oder mehrere der folgenden <xref:System.Windows.Forms.DataGridView> Eigenschaften:  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Um das Steuerelement den Größenanpassungsmodus für eine einzelne Spalte zu überschreiben, legen dessen <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> Eigenschaft, um einen anderen Wert als <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>. Wird von der Größenänderungsmodus für eine Spalte bestimmt die <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> Eigenschaft. Der Wert dieser Eigenschaft wird auf Grundlage der Spalte des <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> Eigenschaftswert, es sei denn, dieser Wert ist <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>, in diesem Fall des Steuerelements <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> Wert geerbt wird.  
  
 Verwenden Sie die Content-basierte automatische Größenänderung mit Vorsicht bei der Arbeit mit großen Datenmengen. Um Leistungseinbußen zu vermeiden, verwenden Sie die Modi zur Größenänderung, die Berechnen der Größen, die nur auf der angezeigten Zeilen basieren, anstatt jede Zeile im Steuerelement zu analysieren. Für maximale Leistung wird die Verwendung programmgesteuerten größenanpassung stattdessen so, dass Sie zu bestimmten Zeitpunkten, z. B. unmittelbar auf neue Daten die Größe ändern geladen.  
  
 Modi zur Größenänderung inhaltsbasierte haben keine Auswirkungen auf Zeilen, Spalten und Header, die Sie durch Festlegen der Zeile oder Spalte ausgeblendet haben <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> Eigenschaft oder das Steuerelement <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> oder <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> Eigenschaften `false`. Z. B. wenn eine Spalte ausgeblendet ist, nachdem es automatisch für die einen große Zellenwert die Größe angepasst wird, ändert die ausgeblendete Spalte seine Größe sich nicht, wenn die Zeile mit dem Wert für große Zelle gelöscht wird. Automatische Größenänderung erfolgt nicht, wenn Sichtbarkeit ändert, so dass die Änderung der Spalte <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> -Eigenschaft zurück auf `true` wird nicht erzwungen, es um die Größe basierend auf den aktuellen Inhalt neu zu berechnen.  
  
 Programmgesteuerten größenanpassung inhaltsbasierte wirkt sich auf Zeilen, Spalten und unabhängig von ihrer Sichtbarkeit.  
  
## <a name="programmatic-resizing"></a>Programmgesteuerten Größenanpassung  
 Wenn automatische größenanpassungen deaktiviert ist, können Sie programmgesteuert die genaue Breite oder Höhe der Zeilen, Spalten und Header über die folgenden Eigenschaften festlegen:  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
  
 Sie können auch programmgesteuert Zeilen, Spalten und Header an ihren Inhalt mithilfe der folgenden Methoden an die Größe ändern:  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 Diese Methoden werden Zeilen, Spalten oder Header einmal anstatt konfigurieren sie continuous Ändern der Größe die Größe ändern. Die neuen Größen werden automatisch alle Zelleninhalt ohne Clipping anzuzeigende berechnet. Wenn Sie programmgesteuerte Änderung der Spaltengröße, die <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> Eigenschaftswerte <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>, jedoch werden der berechneten Breiten verwendet, um die Spalte proportional anzupassen <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> Eigenschaftswerte, und die Spalte tatsächlich breiten sind Klicken Sie dann berechnet basierend auf diesen neuen Proportionen, so, dass alle Spalten des Steuerelements verfügbaren Anzeigebereichs ausfüllen.  
  
 Programmgesteuerten größenanpassung ist nützlich, um Leistungseinbußen mit fortlaufenden Größenänderung zu vermeiden. Es ist auch nützlich, um die anfängliche Größen für Benutzer mit veränderbarer Größe der Zeilen, Spalten und Header und für Spaltenfüllmodus bereitgestellt werden.  
  
 Rufen Sie in der Regel die programmgesteuerten Methoden zum Ändern der Größe zu bestimmten Zeiten. Angenommen, Sie die Größe aller Spalten direkt nach dem Laden von Daten, oder Sie die Größe einer bestimmten Zeile nach ein bestimmten Zellwert geändert wurde.  
  
## <a name="customizing-content-based-sizing-behavior"></a>Anpassen von inhaltsbasierten Größenanpassungsverhalten  
 Sie können die größenanpassung Verhalten anpassen, Arbeit mit abgeleiteten <xref:System.Windows.Forms.DataGridView> Zelle, Zeile und Spalte Typen durch Überschreiben der <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType>, oder <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType> Methoden oder durch Aufrufen von geschützten Größenänderung Überladungen der Methode in einer abgeleiteten <xref:System.Windows.Forms.DataGridView> -Steuerelement. Die geschützten Größenänderung methodenüberladungen dienen zum paarweise erzielen Sie eine ideale Zelle Höhe und Breite Verhältnis zu Breite oder Höhe Zellen vermeiden zu arbeiten. Angenommen, Sie rufen die `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` Überladung von der <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> -Methode und übergeben Sie den Wert `false` für die <xref:System.Boolean> Parameter berechnet die Überladung die ideale Höhe und Breite für Zellen in der Zeile, aber es werden die Zeilenhöhen angepasst nur. Sie müssen dann aufrufen, die <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> Methode, um die Spaltenbreiten dem berechneten ideal angepasst.  
  
## <a name="content-based-sizing-options"></a>Inhaltsbasierte Größenänderungsoptionen  
 Die Enumerationen, die von der von Größeneigenschaften und Methoden verwendet haben ähnliche Werte für die Dimensionierung von inhaltsbasierten. Mit diesen Werten verwenden können Sie einschränken, welche Zellen verwendet werden, um die bevorzugte Größe zu berechnen. Für alle zur größenanpassung-Enumerationen nur die Werte mit Namen, die auf die angezeigten Zellen verweisen ihre Berechnungen für Zellen in Zeilen angezeigt. Ausschließen von Zeilen ist nützlich, um Leistungseinbußen zu vermeiden, wenn Sie mit einer großen Menge von Zeilen arbeiten. Sie können auch Berechnungen durch, um Werte von Zellen in Header oder keine Headerzeile Zellen beschränken.  
  
## <a name="see-also"></a>Siehe auch
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
- [Vorgehensweise: Festlegen der Größenanpassungsmodi des DataGridView-Steuerelement von Windows Forms](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
