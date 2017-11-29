---
title: "Steuerelemente mit integrierter Ownerdrawing-Unterstützung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8fb699a93effcdf0b5f88606419479d51754125b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="controls-with-built-in-owner-drawing-support"></a>Steuerelemente mit integrierter Ownerdrawing-Unterstützung
Ownerdrawing in Windows Forms, das auch als benutzerdefiniertes Zeichnen bezeichnet, ist ein Verfahren zum Ändern der Darstellung bestimmter Steuerelemente.  
  
> [!NOTE]
>  Das Wort "Control" in diesem Thema wird verwendet, um Klassen zu verstehen, die entweder ableiten <xref:System.Windows.Forms.Control> oder <xref:System.ComponentModel.Component>.  
  
 In der Regel Windows behandelt Paint-Ereignisse automatisch mit Einstellungen wie z. B. <xref:System.Windows.Forms.Control.BackColor%2A> um die Darstellung eines Steuerelements zu bestimmen. Beim Ownerdrawing übernehmen Sie das Zeichnen und können Darstellungselemente ändern, die nicht mithilfe von Eigenschaften angepasst werden können. Beispielsweise kann bei zahlreichen Steuerelementen die Farbe des angezeigten Textes festgelegt werden. Dabei ist die Anzeige jedoch auf eine Farbe beschränkt. Das Ownerdrawing bietet beispielsweise die Möglichkeit, einen Teil des Textes schwarz und den anderen rot anzuzeigen.  
  
 In der Praxis ähnelt Ownerdrawing dem Zeichnen von Grafiken auf einem Formular. Beispielsweise können Sie Grafikmethoden in einem Ereignishandler für des Formulars <xref:System.Windows.Forms.Control.Paint> Ereignis zum Emulieren einer `ListBox` -Steuerelement, aber Sie müssten Schreiben eigener Code aus, um alle Benutzerinteraktion zu verarbeiten. Beim Ownerdrawing verwendet das Steuerelement den von Ihnen geschriebenen Code, um den Inhalt zu zeichnen, behält im Übrigen aber seine gesamte systeminterne Funktionalität bei. Sie können Grafikmethoden zum Zeichnen der einzelnen Elemente im Steuerelement oder zum Anpassen einiger Aspekte einzelner Elemente verwenden, während für andere Aspekte einzelner Elemente wiederum die Standarddarstellung übernommen werden kann.  
  
## <a name="owner-drawing-in-windows-forms-controls"></a>Ownerdrawing in Windows Forms-Steuerelementen  
 Um Ownerdrawing in Steuerelementen auszuführen, die diese Art des Zeichnens unterstützen, legen Sie normalerweise eine Eigenschaft fest und behandeln mindestens ein Ereignis.  
  
 Die meisten Steuerelemente mit Ownerdrawing-Unterstützung verfügen über die `OwnerDraw`-Eigenschaft oder `DrawMode`-Eigenschaft, die angibt, ob das Steuerelement eines oder mehrere zeichnungsbezogene Ereignisse auslöst, sobald es gezeichnet wird.  
  
 Zu den Steuerelementen, die keine `OwnerDraw`-Eigenschaft oder `DrawMode`-Eigenschaft aufweisen, gehört das `DataGridView`-Steuerelement, das automatisch ausgelöste Zeichnungsereignisse bereitstellt, sowie das `ToolStrip`-Steuerelement, das unter Verwendung einer externen Renderklasse gezeichnet wird, die eigene zeichnungsbezogene Ereignisse aufweist.  
  
 Es stehen viele verschiedene Arten von Zeichnungsereignissen zur Verfügung. Ein typisches Zeichnungsereignis tritt jedoch auf, wenn ein einzelnes Element innerhalb eines Steuerelements gezeichnet werden soll. Der Ereignishandler empfängt ein `EventArgs`-Objekt mit Informationen zum gezeichneten Element sowie zu den Tools, die zum Zeichnen verwendet werden können. Dieses Objekt enthält z. B. in der Regel Indexnummer innerhalb der übergeordneten Auflistung, das Element ein <xref:System.Drawing.Rectangle> , der angibt, des Elements anzuzeigen, Grenzen, und ein <xref:System.Drawing.Graphics> Objekt für das Paint-Methoden aufrufen. Bei einigen Ereignissen umfasst das `EventArgs`-Objekt zusätzliche Informationen zum Element sowie zu den Methoden, die aufgerufen werden können, um einige Aspekte des Elements in der Standarddarstellung zu zeichnen, z. B. den Hintergrund oder ein Fokusrechteck.  
  
 Zum Erstellen eines wiederverwendbaren Steuerelements, das Ownerdrawing-Anpassungen enthält, erstellen Sie eine neue Klasse, die von einer Steuerelementklasse mit Ownerdrawing-Unterstützung abgeleitet ist. Anstatt Zeichnungsereignisse zu behandeln, sollten Sie Ownerdrawing-Code in Überschreibungen für mindestens eine geeignete `On`*EventName*-Methode in der neuen Klasse einfügen. Stellen Sie in diesem Fall sicher, dass die `On`*EventName*-Methoden der Basisklasse aufgerufen werden, damit Benutzer des Steuerelements Ownerdrawing-Ereignisse behandeln und weitere Anpassungen vornehmen können.  
  
 Die folgenden Windows Forms-Steuerelemente unterstützen Ownerdrawing in allen Versionen von .NET Framework:  
  
-   <xref:System.Windows.Forms.ListBox>  
  
-   <xref:System.Windows.Forms.ComboBox>  
  
-   <xref:System.Windows.Forms.MenuItem>(verwendet von <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu>)  
  
-   <xref:System.Windows.Forms.TabControl>  
  
 Die folgenden Steuerelemente unterstützen Ownerdrawing nur in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:  
  
-   <xref:System.Windows.Forms.ToolTip>  
  
-   <xref:System.Windows.Forms.ListView>  
  
-   <xref:System.Windows.Forms.TreeView>  
  
 Die folgenden Steuerelemente unterstützen Ownerdrawing und sind in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] neu:  
  
-   <xref:System.Windows.Forms.DataGridView>  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
 Die folgenden Abschnitte enthalten zusätzliche Details zu jedem dieser Steuerelemente.  
  
### <a name="listbox-and-combobox-controls"></a>Die Steuerelemente ListBox und ComboBox  
 Die <xref:System.Windows.Forms.ListBox> und <xref:System.Windows.Forms.ComboBox> Steuerelemente ermöglichen es Ihnen, einzelne Elemente im Steuerelement entweder in derselben oder in verschiedenen Größen zu zeichnen.  
  
> [!NOTE]
>  Obwohl die <xref:System.Windows.Forms.CheckedListBox> Steuerelement stammt aus der <xref:System.Windows.Forms.ListBox> -Steuerelement, er unterstützt keine Ownerdrawing.  
  
 Um jedes Element dieselbe Größe zu zeichnen, legen Sie die `DrawMode` Eigenschaft <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> und behandeln die `DrawItem` Ereignis.  
  
 Um jedes Element mit einer anderen Größe zu zeichnen, legen Sie die `DrawMode` Eigenschaft <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> und behandeln Sie sowohl die `MeasureItem` und `DrawItem` Ereignisse. Mit dem `MeasureItem`-Ereignis können Sie die Größe eines Elements angeben, bevor das `DrawItem`-Ereignis für das jeweilige Element auftritt.  
  
 Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Themen:  
  
-   <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
-   [Gewusst wie: Erstellen von Text mit variabler Größe in einem ComboBox-Steuerelement](../../../../docs/framework/winforms/controls/how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a>MenuItem-Komponente  
 Die <xref:System.Windows.Forms.MenuItem> -Komponente darstellt, ein einzelnes Menüelement in ein <xref:System.Windows.Forms.MainMenu> oder <xref:System.Windows.Forms.ContextMenu> Komponente.  
  
 Gezeichnet werden soll eine <xref:System.Windows.Forms.MenuItem>legen seine `OwnerDraw` Eigenschaft, um `true` und behandeln die `DrawItem` Ereignis. Um die Größe des Menüelements anzupassen, bevor das `DrawItem`-Ereignis auftritt, behandeln Sie das `MeasureItem`-Ereignis des Elements.  
  
 Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Referenzthemen:  
  
-   <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a>TabControl-Steuerelement  
 Die <xref:System.Windows.Forms.TabControl> -Steuerelement ermöglicht Ihnen die einzelne Registerkarten im Steuerelement gezeichnet werden soll. Ownerdrawing wirkt sich nur die Registerkarten. die <xref:System.Windows.Forms.TabPage> Inhalt sind nicht betroffen.  
  
 Zum Zeichnen der einzelnen Registerkarten in einem <xref:System.Windows.Forms.TabControl>, legen die `DrawMode` Eigenschaft, um <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> und behandeln die `DrawItem` Ereignis. Dieses Ereignis tritt jeweils einmal für jede Registerkarte auf, jedoch nur dann, wenn die Registerkarte im Steuerelement sichtbar ist.  
  
 Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Referenzthemen:  
  
-   <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a>ToolTip-Komponente  
 Die <xref:System.Windows.Forms.ToolTip> -Komponente können Sie die gesamte QuickInfo zu zeichnen, wenn er angezeigt wird.  
  
 Gezeichnet werden soll eine <xref:System.Windows.Forms.ToolTip>legen seine `OwnerDraw` Eigenschaft, um `true` und behandeln die `Draw` Ereignis. Zum Anpassen der Größe des der <xref:System.Windows.Forms.ToolTip> vor der `Draw` Ereignis auftritt, behandelt der `Popup` Ereignis, und legen die <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> Eigenschaft im Ereignishandler.  
  
 Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Referenzthemen:  
  
-   <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a>ListView-Steuerelement  
 Die <xref:System.Windows.Forms.ListView> Steuerelement können Sie einzelne Elemente und Unterelemente Spaltenüberschriften im Steuerelement gezeichnet werden soll.  
  
 Um Ownerdrawing im Steuerelement zu aktivieren, legen Sie die `OwnerDraw`-Eigenschaft `true` fest.  
  
 Um jedes Element im Steuerelement zu zeichnen, behandeln Sie das `DrawItem`-Ereignis.  
  
 Jedes Unterelement oder den Spaltenüberschrift im Steuerelement gezeichnet werden soll. bei der <xref:System.Windows.Forms.ListView.View%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.View.Details>, behandeln die `DrawSubItem` und `DrawColumnHeader` Ereignisse.  
  
 Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Referenzthemen:  
  
-   <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a>TreeView-Steuerelement  
 Die <xref:System.Windows.Forms.TreeView> -Steuerelement ermöglicht es Ihnen, einzelne Knoten im Steuerelement zu zeichnen.  
  
 Um nur die in den einzelnen Knoten angezeigten Text zu zeichnen, legen die `DrawMode` Eigenschaft <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> und behandeln die `DrawNode` Ereignis zum Zeichnen des Texts.  
  
 Um alle Elemente der einzelnen Knoten zu zeichnen, legen Sie die `DrawMode` Eigenschaft <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> und behandeln die `DrawNode` Ereignis unabhängig davon, welche Elemente zu zeichnen, müssen Sie, wie z. B. Text, Symbole, Kontrollkästchen, Plus- und Minuszeichen und Verbindungslinien zwischen den Knoten.  
  
 Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Referenzthemen:  
  
-   <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a>DataGridView-Steuerelement  
 Die <xref:System.Windows.Forms.DataGridView> -Steuerelement ermöglicht es Ihnen, einzelne Zellen und Zeilen im Steuerelement zu zeichnen.  
  
 Um einzelne Zellen zu zeichnen, behandeln Sie das `CellPainting`-Ereignis.  
  
 Um einzelne Zeilen oder Zeilenelemente zu zeichnen, behandeln Sie das `RowPrePaint`- und/oder `RowPostPaint`-Ereignis. Das `RowPrePaint`-Ereignis tritt vor dem Zeichnen der Zellen in einer Zeile und das `RowPostPaint`-Ereignis danach auf. Sie können beide Ereignisse und das `CellPainting`-Ereignis behandeln, um den Zeilenhintergrund, einzelne Zellen sowie den Zeilenvordergrund separat zu zeichnen. Alternativ können Sie für bestimmte Elemente spezielle Anpassungen bereitstellen und für die übrigen Zeilenelemente die Standarddarstellung verwenden.  
  
 Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Themen:  
  
-   <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
-   [Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
  
-   [Gewusst wie: Anpassen der Darstellung von Zeilen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a>ToolStrip-Steuerelement  
 <xref:System.Windows.Forms.ToolStrip>und abgeleitete Steuerelemente ermöglichen es Ihnen, Aspekte ihrer Darstellung anpassen.  
  
 Benutzerdefiniertes Rendering für bereitstellen <xref:System.Windows.Forms.ToolStrip> legen Sie Steuerelemente, die `Renderer` Eigenschaft eine <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, oder <xref:System.Windows.Forms.ToolStripContentPanel> auf eine `ToolStripRenderer` -Objekt und eine oder mehrere der vom bereitgestellten viele zeichnen-Ereignisse behandeln die `ToolStripRenderer` Klasse. Alternativ können Sie einstellen eine `Renderer` -Eigenschaft auf eine Instanz Ihrer eigenen Klasse abgeleitet `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, oder <xref:System.Windows.Forms.ToolStripSystemRenderer> implementiert oder bestimmte überschreibt `On` *EventName* Methoden.  
  
 Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Themen:  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>  
  
-   [Gewusst wie: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
-   [Gewusst wie: Benutzerdefiniertes Zeichnen eines ToolStrip-Steuerelements](../../../../docs/framework/winforms/controls/how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
