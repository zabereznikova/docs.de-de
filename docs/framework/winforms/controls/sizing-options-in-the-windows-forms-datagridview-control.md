---
title: "Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], row sizing
- data grids [Windows Forms], column sizing
- DataGridView control [Windows Forms], column sizing
- DataGridView control [Windows Forms], sizing options
- data grids [Windows Forms], row sizing
- data grids [Windows Forms], sizing options
ms.assetid: a5620a9c-0d06-41e3-8934-c25ddb16c9e6
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6cefca8e6856680d509d6166eec4d97855f1babc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Größenänderungsoptionen im DataGridView-Steuerelement in Windows Forms
<xref:System.Windows.Forms.DataGridView>Zeilen, Spalten und Header können aus zahlreichen Gründen ihre Größe ändern. Die folgende Tabelle zeigt diese vorkommen.  
  
|Vorkommen|Beschreibung|  
|----------------|-----------------|  
|Benutzer zum Ändern der Größe|Benutzer können die Größe Anpassungen vornehmen, durch Ziehen oder auf Zeilen-, Spalten- oder Header Trennblättern doppelklicken.|  
|Größe des Steuerelements|Ändern der Spaltenbreite im Spaltenfüllmodus Wenn die Breite des Steuerelements geändert wird; beispielsweise ändert beim übergeordneten Formulars und dem Benutzer das Steuerelement angedockt ist die Form.|  
|Änderung in der Zelle Wert|Ändern Sie in inhaltsbasierten automatischen Größenanpassungsmodi Größen entsprechend der neuen Werte ein.|  
|Methodenaufruf|Programmgesteuerten größenanpassung inhaltsbasierten ermöglicht es Ihnen basierte auf Zellenwerten zum Zeitpunkt des Methodenaufrufs opportunistische Größe-Anpassungen vorzunehmen.|  
|Einstellung der Eigenschaft|Sie können auch bestimmte Höhe und Breitenwerte festlegen.|  
  
 Standardmäßig Ändern der Größe von Benutzer aktiviert ist, Größenänderung ist deaktiviert und Zellwerte, die größer sind als ihre Spalten werden abgeschnitten.  
  
 In der folgenden Tabelle werden Szenarien beschrieben, die Sie verwenden können, um das Standardverhalten anzupassen oder zu bestimmten Größenanpassungsoptionen zu verwenden, um bestimmte Ergebnisse zu erzielen.  
  
|Szenario|Implementierung|  
|--------------|--------------------|  
|Spaltenfüllmodus verwenden, für die Anzeige von Größe auf ähnliche Weise Daten in einer relativ kleinen Anzahl von Spalten, die die gesamte Breite des Steuerelements zu belegen, ohne dass die horizontale Bildlaufleiste angezeigt.|Legen Sie die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> fest.|  
|Verwenden von Spaltenfüllmodus mit Werte mit unterschiedlichen Größen anzeigen|Legen Sie die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> fest. Initialisieren Sie relative Spaltenbreiten, indem Sie die Spalte <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> Eigenschaften oder durch Aufrufen des Steuerelements <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> Methode auf, nachdem das Steuerelement mit Daten gefüllt.|  
|Verwenden Sie Spaltenfüllmodus mit Werten von unterschiedliche Bedeutung.|Legen Sie die <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>-Eigenschaft auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> fest. Legen Sie große <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> Werte für Spalten, die immer einige Daten angezeigt werden müssen, oder verwenden Sie die gewünschte Option nur im Modus für bestimmte Spalten ausfüllen.|  
|Verwenden Sie Spaltenfüllmodus, um zu vermeiden, den Hintergrund des Steuerelements anzeigen.|Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> Eigenschaft der letzten Spalte, die <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> und andere Optionen für die anderen Spalten verwenden. Wenn die anderen Spalten zu viel des verfügbaren Speicherplatzes verwenden, legen die <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> -Eigenschaft der letzten Spalte.|  
|Zeigt eine Spalte mit fester Breite, z. B. ein Symbol oder eine ID-Spalte.|Legen Sie <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> auf <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> und <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> zu <xref:System.Windows.Forms.DataGridViewTriState.False> für die Spalte. Initialisieren Sie die Breite durch Festlegen der <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> Eigenschaft oder durch Aufrufen des Steuerelements <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> Methode auf, nachdem das Steuerelement mit Daten gefüllt.|  
|Stellen Sie die Größe automatisch Änderung Zelleninhalt Clipping zu vermeiden und die Verwendung von Speicherplatz zu optimieren.|Legen Sie eine automatische größenanpassung-Eigenschaft auf einen Wert, der einen inhaltsbasierten Größenanpassungsmodus darstellt. Um Leistungseinbußen zu vermeiden, bei der Arbeit mit großen Mengen von Daten, verwenden Sie einen Größenanpassungsmodus, die nur die angezeigte Zeilen berechnet.|  
|Stellen Sie die Größe um die Werte in Zeilen angezeigt, um Leistungseinbußen zu vermeiden, bei der Arbeit mit vielen Zeilen passen.|Verwenden Sie die geeignete Größenanpassungsmodus Enumerationswerte, mit der automatischen oder eine programmgesteuerte Ändern der Größe. Rufen Sie zum Anpassen der Größe an, dass beim Ausführen eines Bildlaufs in Zeilen neu angezeigten Werte eine Größe Methode in einer <xref:System.Windows.Forms.DataGridView.Scroll> -Ereignishandler. Benutzer doppelklicken anpassen ändern der Größe, damit nur die Werte in Zeilen angezeigt, die neue Größe bestimmen rufen Sie eine Größe Methode in einer <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> oder <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick> -Ereignishandler.|  
|Stellen Sie die Größe angepasst Zelleninhalt nur zu bestimmten Zeitpunkten, um Leistungseinbußen zu vermeiden oder das Ändern der Größe von Benutzer aktivieren.|Eine inhaltsbasierte Größe-Methode in einem Ereignishandler aufrufen. Beispielsweise verwenden die <xref:System.Windows.Forms.DataGridView.DataBindingComplete> Ereignis zu Größen nach der Bindung zu initialisieren, und behandeln die <xref:System.Windows.Forms.DataGridView.CellValidated> oder <xref:System.Windows.Forms.DataGridView.CellValueChanged> Ereignis anpassen Größen zur Kompensierung benutzerbearbeitungen oder Änderungen in einer gebundenen Datenquelle.|  
|Passen Sie die Zeilenhöhe für mehrzeiligen Zelleninhalt.|Stellen Sie sicher, dass die Spaltenbreite für die Anzeige von Absätzen des Texts geeignet sind, und verwenden Sie automatische oder eine programmgesteuerte inhaltsbasierten Zeilengröße die Höhe anpassen. Stellen Sie außerdem sicher, dass Zellen mit mehrzeiligen Inhalt mit angezeigt werden eine <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> Formatwert der Zelle <xref:System.Windows.Forms.DataGridViewTriState.True>.<br /><br /> In der Regel verwenden Sie einen automatischen Größenanpassungsmodus Spaltenbreite verwalten oder sie auf eine bestimmte Breite festlegen, bevor die Zeilenhöhen angepasst werden.|  
  
## <a name="resizing-with-the-mouse"></a>Ändern der Größe, mit der Maus  
 Standardmäßig können Benutzer ändern, Zeilen, Spalten und Header, die eine automatische Größenanpassungsmodus basierend auf den Zellenwerten nicht verwenden. Um zu verhindern, dass Benutzer andere Größenanpassungsmodi verwenden, z. B. Spaltenfüllmodus, legen Sie eine oder mehrere der folgenden <xref:System.Windows.Forms.DataGridView> Eigenschaften:  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 Sie können auch verhindern, dass Benutzer von der Größe der einzelnen Zeilen oder Spalten durch Festlegen ihrer <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschaften. Wird standardmäßig die <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschaftswert basiert auf der <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> Eigenschaftswert für Spalten und die <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> Eigenschaftswert für Zeilen. Wenn Sie explizit festlegen <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> auf <xref:System.Windows.Forms.DataGridViewTriState.True> oder <xref:System.Windows.Forms.DataGridViewTriState.False>, jedoch die angegebene Wert überschreibt die Control-Wert für diese Zeile oder Spalte ist. Legen Sie <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> zu <xref:System.Windows.Forms.DataGridViewTriState.NotSet> um die Vererbung wiederherzustellen.  
  
 Da <xref:System.Windows.Forms.DataGridViewTriState.NotSet> Vererbung wiederhergestellt wird der Wert, der <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschaft wird nie zurückgegeben. ein <xref:System.Windows.Forms.DataGridViewTriState.NotSet> Wert, es sei denn, die Zeile oder Spalte nicht hinzugefügt wurde eine <xref:System.Windows.Forms.DataGridView> Steuerelement. Wenn Sie bestimmen müssen, ob die <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschaftswert, der eine Zeile oder Spalte geerbt wird, überprüfen Sie die <xref:System.Windows.Forms.DataGridViewElement.State%2A> Eigenschaft. Wenn die <xref:System.Windows.Forms.DataGridViewElement.State%2A> Wert umfasst die <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet> Flag, das <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> Eigenschaftswert nicht geerbt.  
  
## <a name="automatic-sizing"></a>Automatische Größenanpassung  
 Es gibt zwei Arten der automatischen Größenänderung in die <xref:System.Windows.Forms.DataGridView> Steuerelement: Spaltenfüllmodus und inhaltsbasierte Größenänderung.  
  
 Spaltenfüllmodus bewirkt, dass die sichtbaren Spalten im Steuerelement, füllen Sie die Breite der Anzeigebereich des Steuerelements. Weitere Informationen zu diesem Modus finden Sie unter [Spalte ausfüllen Modus im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md).  
  
 Sie können auch Zeilen, Spalten und Header automatisch ihre Größe an ihre Zelleninhalt anpassen konfigurieren. In diesem Fall tritt auf, Größe, wenn der Inhalt der Zelle ändern.  
  
> [!NOTE]
>  Wenn Sie die Werte von Zellen in einem benutzerdefinierten Datencache Verwendung des virtuellen Modus verwalten, tritt automatische größenanpassung auf, wenn der Benutzer einen Zellwert bearbeitet, jedoch tritt nicht auf, wenn Sie einen zwischengespeicherten Wert außerhalb des alter eine <xref:System.Windows.Forms.DataGridView.CellValuePushed> -Ereignishandler. In diesem Fall rufen die <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> Methode, um das Steuerelement aktualisiert die Zellenanzeige und Anwenden der aktuellen Modi zur Größenänderung zu erzwingen.  
  
 Wenn automatische größenanpassung inhaltsbasierten für nur eine Dimension aktiviert ist – d. h. für Zeilen, jedoch keine Spalten oder für Spalten, jedoch keine Zeilen – und <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> ist auch aktiviert, Größe Anpassung tritt auch bei jeder Änderung die anderen Dimension. Angenommen, wenn Zeilen, jedoch keine Spalten für die automatische größenanpassung konfiguriert sind und <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> ist aktiviert, Benutzer können Spaltenunterteiler zum Ändern der Breite einer Spalte ziehen und Zeilenhöhe werden automatisch angepasst, sodass Zelleninhalt noch vollständig angezeigt werden.  
  
 Wenn Sie Zeilen und Spalten für die automatische größenanpassung inhaltsbasierten konfigurieren und <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> aktiviert ist, die <xref:System.Windows.Forms.DataGridView> Steuerelement wird Größen angepasst, sobald Inhalt der Zelle geändert und es ein Zelle ideale Höhe und Breite Verhältnis verwendet werden, bei der Berechnung der neuer Größen.  
  
 So konfigurieren den Größenanpassungsmodus für Kopf- und Zeilen und Spalten, die nicht den Steuerelementwert außer Kraft setzen, legen Sie eine oder mehrere der folgenden <xref:System.Windows.Forms.DataGridView> Eigenschaften:  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Um das Steuerelement Größenanpassungsmodus für eine einzelne Spalte zu überschreiben, legen dessen <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> -Eigenschaft auf einen anderen Wert als <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>. Der Größenänderungsmodus für eine Spalte wird tatsächlich durch bestimmt dessen <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> Eigenschaft. Der Wert dieser Eigenschaft basiert auf der Spaltenwerts <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> Eigenschaftswert, es sei denn, dass der Wert <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>, in diesem Fall des Steuerelements <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> Wert geerbt wird.  
  
 Verwenden Sie die inhaltsbasierte automatische Größenänderung mit Vorsicht bei der Arbeit mit großen Mengen von Daten. Um Leistungseinbußen zu vermeiden, verwenden Sie die Modi zur Größenänderung, die Größen analysiert jede Zeile im Steuerelement, statt anhand der angezeigten Zeilen zu berechnen. Um eine optimale Leistung wird die Verwendung programmgesteuerten größenanpassung stattdessen, damit Sie zu bestimmten Zeitpunkten, z. B. unmittelbar auf neue Daten ändern können geladen.  
  
 Modi zur Größenänderung inhaltsbasierten haben keine Auswirkungen auf Zeilen, Spalten und Header, die Sie durch Festlegen der Zeile oder Spalte ausgeblendet haben <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> Eigenschaft oder das Steuerelement <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> oder <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> Eigenschaften `false`. Z. B. wenn eine Spalte ausgeblendet ist, nachdem er automatisch für einen großen Zellenwert angepasst wird, wird die ausgeblendete Spalte nicht seine Größe ändern, wenn die Zeile mit dem Wert große Zelle gelöscht wird. Automatische größenanpassung tritt nicht auf, wenn Sichtbarkeit geändert wird, also durch Ändern der Spalte <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> -Eigenschaft zurück auf `true` wird nicht erzwingen, dessen Größe basierend auf den aktuellen Inhalt neu zu berechnen.  
  
 Programmgesteuerten größenanpassung inhaltsbasierten wirkt sich auf Zeilen, Spalten und Header unabhängig von ihrer Sichtbarkeit.  
  
## <a name="programmatic-resizing"></a>Programmgesteuerte Ändern der Größe  
 Wenn automatische größenanpassung deaktiviert ist, können Sie programmgesteuert die genaue Breite oder Höhe der Zeilen, Spalten und Header über die folgenden Eigenschaften festlegen:  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
  
 Sie können auch programmgesteuert Zeilen, Spalten und Header an ihren Inhalt mithilfe der folgenden Methoden ändern:  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 Diese Methoden werden die Größe Zeilen, Spalten oder Kopfzeilen einmal anstatt sie kontinuierliche Größe zu konfigurieren. Die neuen Größen werden automatisch berechnet, um alle Zelleninhalt ohne Clipping anzuzeigen. Wenn Sie programmgesteuert Größe ändern, Spalten mit <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> Eigenschaftswerte des <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>, berechneten Breiten inhaltsbasierten dienen jedoch zum proportionalen Anpassen der Spalte <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> Eigenschaftswerte, und die Spalte tatsächlich breiten sind Klicken Sie dann berechnet gemäß diesen neuen Proportionen, damit, dass alle Spalten mit den verfügbaren Anzeigebereich des Steuerelements ausfüllen.  
  
 Programmgesteuerte Ändern der Größe ist hilfreich, die mit kontinuierlichen Größenänderung Leistungseinbußen zu vermeiden. Es ist auch nützlich, um die Anfangsgröße Benutzer veränderbare Größen von Zeilen, Spalten und Header, und zur Spaltenfüllmodus bereitzustellen.  
  
 Rufen Sie in der Regel die programmgesteuerten Größenänderungsmethoden zu bestimmten Zeitpunkten. Angenommen, Sie die Größe aller Spalten direkt nach dem Laden von Daten, oder Sie die Größe einer bestimmten Zeile nach ein bestimmten Zellwert geändert wurde.  
  
## <a name="customizing-content-based-sizing-behavior"></a>Anpassen von inhaltsbasierten Größenanpassungsverhalten  
 Können Sie Sizing Verhalten anpassen, wenn mit abgeleiteten arbeiten <xref:System.Windows.Forms.DataGridView> Zellen-, Zeilen- und Spalte Typen durch Überschreiben der <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType>, oder <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType> Methoden oder durch Aufrufen geschützt Größe Überladungen der Methode in einer abgeleiteten <xref:System.Windows.Forms.DataGridView> -Steuerelement. Geschützte Größe methodenüberladungen dienen zum Arbeiten in Paaren erzielen eine ideale Zelle Höhe und Breite Ratio übermäßig Breite oder Höhe Zellen vermeiden sind. Angenommen, Sie rufen die `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` Überladung der der <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> -Methode und übergeben Sie den Wert `false` für die <xref:System.Boolean> Parameter, die Überladung berechnet die ideale Höhe und Breite für Zellen in der Zeile, aber es werden die Zeilenhöhen angepasst nur. Sie müssen dann rufen Sie die <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> Methode, um die Spaltenbreite auf den berechneten Idealwert anzupassen.  
  
## <a name="content-based-sizing-options"></a>Content-based Größenanpassungsoptionen  
 Die Enumerationen von Größeneigenschaften und Methoden verwendet, oftmals ähnliche Werte für inhaltsbasierte Größe aufweisen. Mit diesen Werten können Sie einschränken, welche Zellen verwendet werden, um die bevorzugte Größe zu berechnen. Für alle Sizing Enumerationen Grenzwerte mit Namen, die auf der angezeigten Zellen verweisen ihren Berechnungen für Zellen in Zeilen angezeigt. Ausschließen von Zeilen ist nützlich, um Leistungseinbußen zu vermeiden, bei der Arbeit mit einer großen Menge von Zeilen. Sie können auch Berechnungen durch, um Werte von Zellen in der Kopf- oder Tabellenzelle Zellen beschränken.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>  
 <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>  
 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>  
 [Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 [Spaltenfüllmodus im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 [Gewusst wie: Festlegen der Größenanpassungsmodi des DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
