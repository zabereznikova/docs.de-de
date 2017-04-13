---
title: "Steuerelemente mit integrierter Ownerdrawing-Unterst&#252;tzung | Microsoft Docs"
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
  - "Zeichnen, Besitzer"
  - "benutzerdefinierte Zeichnung"
  - "Steuerelemente [Windows Forms], Ändern der Darstellung"
  - "Benutzerdefiniertes Zeichnen"
  - "Ownerdrawing"
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Steuerelemente mit integrierter Ownerdrawing-Unterst&#252;tzung
Ownerdrawing in Windows Forms, das auch als benutzerdefiniertes Zeichnen bezeichnet, ist ein Verfahren zum Ändern der Darstellung bestimmter Steuerelemente.  
  
> [!NOTE]
>  Das Wort "Control" in diesem Thema wird verwendet, um Klassen bezeichnet, die entweder ableiten <xref:System.Windows.Forms.Control> oder <xref:System.ComponentModel.Component>.  
  
 In der Regel Windows-handles Zeichnen automatisch mithilfe von Eigenschaften wie z. B. <xref:System.Windows.Forms.Control.BackColor%2A> um die Darstellung eines Steuerelements zu bestimmen. Beim Ownerdrawing übernehmen Sie den Anstrich Ändern von Elementen der Darstellung, die Eigenschaften nicht verfügbar sind. Z. B. viele Steuerelemente können Sie festlegen, die Farbe des Texts, der angezeigt wird, aber Sie können nur eine einzelne Farbe. Ownerdrawing können Sie veranlassen, z. B. einen Teil des Textes in Schwarz und rot angezeigt.  
  
 In der Praxis ähnelt Ownerdrawing zeichnen Grafiken in einem Formular. Beispielsweise können Sie Grafikmethoden in einem Handler für des Formulars <xref:System.Windows.Forms.Control.Paint> Ereignis emulieren ein `ListBox` Steuerelement, sondern alle Benutzerinteraktionen behandeln Ihren eigenen Code schreiben müssten. Beim Ownerdrawing des Steuerelements verwendet den Code für den Inhalt zu zeichnen andernfalls behält jedoch seine gesamte systeminterne Funktionalität. Jedes Element im Steuerelement zu zeichnen oder passen Sie einige Aspekte der einzelnen Elemente, während Sie das Standardaussehen für andere Aspekte der einzelnen Elemente verwenden, können Sie Grafikmethoden verwenden.  
  
## <a name="owner-drawing-in-windows-forms-controls"></a>Ownerdrawing in Windows Forms-Steuerelementen  
 Zum Ausführen von Ownerdrawing in Steuerelementen, die sie unterstützen Sie in der Regel legen Sie eine Eigenschaft und ein oder mehrere Ereignisse behandeln.  
  
 Die meisten Steuerelemente mit Ownerdrawing-Unterstützung verfügen über eine `OwnerDraw` oder `DrawMode` -Eigenschaft, die angibt, ob das Steuerelement ausgelöst wird, die Zeichnung-bezogener Ereignisse oder Ereignisse aus, wenn sie selbst zeichnet.  
  
 Steuerelemente, die keine `OwnerDraw` oder `DrawMode` -Eigenschaft enthalten die `DataGridView` -Steuerelement, das bereitstellt, die automatisch ausgeführt werden, und die `ToolStrip` Steuerelement, das mithilfe einer externen Rendering-Klasse, die eigene Zeichnung-bezogene Ereignisse gezeichnet wird.  
  
 Es gibt viele verschiedene Arten von Ereignissen zu zeichnen, jedoch eine normale zeichnen-Ereignis tritt auf, um ein einzelnes Element in einem Steuerelement zu zeichnen. Der Ereignishandler empfängt ein `EventArgs` -Objekt, das enthält Informationen zu dem Element gezeichnet werden, und tools, die Sie zum Zeichnen verwendet werden kann. Dieses Objekt enthält z. B. in der Regel Indexnummer für das Element in der übergeordneten Auflistung, ein <xref:System.Drawing.Rectangle> , der des Elements angezeigt wird, Grenzen, angibt und ein <xref:System.Drawing.Graphics> Objekt für das Paint-Methoden aufrufen. Für einige Ereignisse die `EventArgs` -Objekt enthält zusätzliche Informationen zum Artikel und den Methoden, die Sie aufrufen können, um einige Aspekte des Elements standardmäßig, wie z. B. den Hintergrund oder ein Rechteck zu zeichnen.  
  
 Um ein wiederverwendbares Steuerelement zu erstellen, das die Ownerdrawn-Anpassungen enthält, erstellen Sie eine neue Klasse, die eine Steuerelement-Klasse abgeleitet, die Ownerdrawing unterstützt. Anstatt Ereignisse zeichnen behandeln, schließen Sie den Ownerdrawing-Code in Außerkraftsetzungen für die entsprechende `On` *EventName* Methoden in der neuen Klasse. Stellen Sie sicher, dass Sie die Basisklasse aufrufen `On` *EventName* Methoden in diesem Fall, damit Benutzer des Steuerelements Ownerdrawing-Ereignisse behandeln und weitere Anpassung bereitstellen können.  
  
 Die folgenden Windows Forms-Steuerelemente unterstützen Ownerdrawing in allen Versionen von .NET Framework:  
  
-   <xref:System.Windows.Forms.ListBox>  
  
-   <xref:System.Windows.Forms.ComboBox>  
  
-   <xref:System.Windows.Forms.MenuItem> (verwendet von <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu>)  
  
-   <xref:System.Windows.Forms.TabControl>  
  
 Die folgenden Steuerelemente unterstützen Ownerdrawing nur in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:  
  
-   <xref:System.Windows.Forms.ToolTip>  
  
-   <xref:System.Windows.Forms.ListView>  
  
-   <xref:System.Windows.Forms.TreeView>  
  
 Die folgenden Steuerelemente unterstützen Ownerdrawing und sind in neue [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:  
  
-   <xref:System.Windows.Forms.DataGridView>  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
 Die folgenden Abschnitte enthalten zusätzliche Details für jedes dieser Steuerelemente.  
  
### <a name="listbox-and-combobox-controls"></a>ListBox und ComboBox-Steuerelemente  
 Die <xref:System.Windows.Forms.ListBox> und <xref:System.Windows.Forms.ComboBox> Steuerelemente ermöglichen es Ihnen, einzelne Elemente im Steuerelement entweder in derselben oder in verschiedenen Größen zu zeichnen.  
  
> [!NOTE]
>  Obwohl die <xref:System.Windows.Forms.CheckedListBox> Steuerelement abgeleitet ist die <xref:System.Windows.Forms.ListBox> Steuerelement, er unterstützt keine Ownerdrawing.  
  
 Um alle Elemente in derselben Größe zu zeichnen, legen die `DrawMode` -Eigenschaft <xref:System.Windows.Forms.DrawMode> und Behandeln der `DrawItem` Ereignis.  
  
 Um alle Elemente in einer anderen Größe zu zeichnen, legen die `DrawMode` -Eigenschaft <xref:System.Windows.Forms.DrawMode> und behandeln sowohl die `MeasureItem` und `DrawItem` Ereignisse. Die `MeasureItem` -Ereignis können Sie die Größe eines Elements vor dem Angeben der `DrawItem` -Ereignis für dieses Element auftritt.  
  
 Weitere Informationen und Codebeispiele finden Sie unter den folgenden Themen:  
  
-   <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=fullName>  
  
-   [Gewusst wie: Erstellen von Text mit variabler Größe in einem ComboBox-Steuerelement](../../../../docs/framework/winforms/controls/how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a>MenuItem-Komponente  
 Die <xref:System.Windows.Forms.MenuItem> Komponente stellt ein einzelnes Menüelement in einer <xref:System.Windows.Forms.MainMenu> oder <xref:System.Windows.Forms.ContextMenu> Komponente.  
  
 Zum Zeichnen einer <xref:System.Windows.Forms.MenuItem>, legen seine `OwnerDraw` -Eigenschaft `true` und behandeln die `DrawItem` Ereignis. Die Größe des Menüelements vor dem Anpassen der `DrawItem` -Ereignis auftritt, Behandeln des Elements `MeasureItem` Ereignis.  
  
 Weitere Informationen und Codebeispiele finden Sie unter den folgenden Themen:  
  
-   <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=fullName>  
  
### <a name="tabcontrol-control"></a>TabControl-Steuerelement  
 Die <xref:System.Windows.Forms.TabControl> -Steuerelement ermöglicht es Ihnen, einzelne Registerkarten im Steuerelement zu zeichnen. Ownerdrawing wirkt sich nur auf die Registerkarten. die <xref:System.Windows.Forms.TabPage> Inhalt sind davon nicht betroffen.  
  
 Zum Zeichnen der einzelnen Registerkarten einem <xref:System.Windows.Forms.TabControl>, legen die `DrawMode` -Eigenschaft auf <xref:System.Windows.Forms.TabDrawMode> und Behandeln der `DrawItem` Ereignis. Dieses Ereignis tritt einmal für jede Registerkarte nur, wenn die Registerkarte im Steuerelement sichtbar ist.  
  
 Weitere Informationen und Codebeispiele finden Sie unter den folgenden Themen:  
  
-   <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=fullName>  
  
### <a name="tooltip-component"></a>ToolTip-Komponente  
 Die <xref:System.Windows.Forms.ToolTip> Komponente können Sie die gesamte QuickInfo zu zeichnen, wenn es angezeigt wird.  
  
 Zum Zeichnen einer <xref:System.Windows.Forms.ToolTip>, legen seine `OwnerDraw` -Eigenschaft `true` und behandeln die `Draw` Ereignis. Anpassen die Größe der der <xref:System.Windows.Forms.ToolTip> vor der `Draw` -Ereignis auftritt, behandeln die `Popup` Ereignis, und legen die <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> -Eigenschaft im Ereignishandler.  
  
 Weitere Informationen und Codebeispiele finden Sie unter den folgenden Themen:  
  
-   <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=fullName>  
  
### <a name="listview-control"></a>ListView-Steuerelement  
 Die <xref:System.Windows.Forms.ListView> Steuerelement ermöglicht es Ihnen, einzelne Elemente, Unterelemente und Spaltenheader im Steuerelement zu zeichnen.  
  
 Um Ownerdrawing im Steuerelement zu aktivieren, legen Sie die `OwnerDraw` -Eigenschaft `true`.  
  
 Um jedes Element im Steuerelement zu zeichnen, behandeln die `DrawItem` Ereignis.  
  
 Um jedes Unterelement oder jeden Spaltenheader im Steuerelement zu zeichnen bei der <xref:System.Windows.Forms.ListView.View%2A> -Eigenschaft auf festgelegt ist <xref:System.Windows.Forms.View>, behandelt der `DrawSubItem` und `DrawColumnHeader` Ereignisse.  
  
 Weitere Informationen und Codebeispiele finden Sie unter den folgenden Themen:  
  
-   <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=fullName>  
  
### <a name="treeview-control"></a>TreeView-Steuerelement  
 Die <xref:System.Windows.Forms.TreeView> -Steuerelement ermöglicht es Ihnen, einzelne Knoten im Steuerelement zu zeichnen.  
  
 Um nur den in den einzelnen Knoten angezeigten Text zu zeichnen, legen die `DrawMode` -Eigenschaft <xref:System.Windows.Forms.TreeViewDrawMode> und Behandeln der `DrawNode` Ereignis zum Zeichnen des Texts.  
  
 Um alle Elemente jedes Knotens zu zeichnen, legen die `DrawMode` -Eigenschaft <xref:System.Windows.Forms.TreeViewDrawMode> und Behandeln der `DrawNode` Ereignis, zeichnen Sie, wie z. B. Text, Symbole, Kontrollkästchen, Plus- und Minuszeichen und Verbindungslinien zwischen den Knoten.  
  
 Weitere Informationen und Codebeispiele finden Sie unter den folgenden Themen:  
  
-   <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=fullName>  
  
### <a name="datagridview-control"></a>DataGridView-Steuerelement  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement ermöglicht es Ihnen, einzelne Zellen und Zeilen im Steuerelement zu zeichnen.  
  
 Um einzelne Zellen zu zeichnen, behandeln die `CellPainting` Ereignis.  
  
 Um einzelne Zeilen oder Zeilen zu zeichnen, behandeln Sie eines oder beider der `RowPrePaint` und `RowPostPaint` Ereignisse. Die `RowPrePaint` -Ereignis tritt vor dem Zeichnen der Zellen in einer Zeile und die `RowPostPaint` Ereignis tritt auf, nachdem die Zellen gezeichnet werden. Sie können beide Ereignisse behandeln und die `CellPainting` Ereignis, um den Zeilenhintergrund, einzelne Zellen, separat zu zeichnen, oder Sie können bestimmte Anpassungen, in denen sie und verwenden Sie die Standardanzeige für andere Elemente der Zeile, bereitstellen.  
  
 Weitere Informationen und Codebeispiele finden Sie unter den folgenden Themen:  
  
-   <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
-   [Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
  
-   [Gewusst wie: Anpassen der Darstellung von Zeilen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a>ToolStrip-Steuerelement  
 <xref:System.Windows.Forms.ToolStrip> und abgeleitete Steuerelemente ermöglichen es Ihnen, Aspekte ihrer Darstellung anpassen.  
  
 Benutzerdefiniertes Rendering für bereitstellen <xref:System.Windows.Forms.ToolStrip> Steuerelemente der `Renderer` Eigenschaft eine <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, oder <xref:System.Windows.Forms.ToolStripContentPanel> zu eine `ToolStripRenderer` -Objekt und mindestens eines der vielen vom bereitgestellten zeichnen Ereignisse behandeln der `ToolStripRenderer` Klasse. Legen Sie alternativ eine `Renderer` -Eigenschaft auf eine Instanz Ihrer eigenen Klasse abgeleitet `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, oder <xref:System.Windows.Forms.ToolStripSystemRenderer> implementiert oder überschreibt bestimmte `On` *EventName* Methoden.  
  
 Weitere Informationen und Codebeispiele finden Sie unter den folgenden Themen:  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>  
  
-   [Gewusst wie: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
-   [Gewusst wie: benutzerdefiniertes Zeichnen eines ToolStrip-Steuerelements](../../../../docs/framework/winforms/controls/how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)