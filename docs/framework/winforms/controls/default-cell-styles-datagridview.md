---
title: 'Vorgehensweise: Festlegen von standardmäßigen Zellenstilen und Datenformaten für das DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: 003ddd68de22d60b771ca525cfa5cc6b2e1e1e3e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650771"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Vorgehensweise: Festlegen von standardmäßigen Zellenstilen und Datenformaten für das DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Die <xref:System.Windows.Forms.DataGridView> -Steuerelement können Sie das Angeben von standardmäßigen Zellenstilen und Datenformaten für das gesamte Steuerelement, für bestimmte Spalten, für die Zeilen- und Spaltenüberschriften und für abwechselnde Zeilen, um einen Ledger-Effekt zu erstellen von Zellen. Die Standardstile für das gesamte Steuerelement festgelegt werden standardmäßig überschrieben, die Stile für abwechselnde Zeilen und Spalten festgelegt. Stile, die Sie im Code für die einzelnen Zeilen und Zellen festlegen wird darüber hinaus die Standardstile überschreiben.  
  
 Weitere Informationen zu Zellstile, finden Sie unter [Zellstile im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md). Festlegen von Stilen für abwechselnde Zeilen finden Sie unter [Vorgehensweise: Festlegen von abwechselnden Zeilenstilen für das Windows Forms-DataGridView-Steuerelement mithilfe des Designers](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md).  
  
 Sie können auch festlegen, Stile, die mit der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> Eigenschaft, um alle Zeilen auswirken, die dem Steuerelement hinzugefügt werden. Weitere Informationen zu der Zeilenvorlage, finden Sie unter [Vorgehensweise: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md).  
  
 Benötigen Sie die folgenden Verfahren eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.DataGridView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>Um die Standardstile für alle Zellen im Steuerelement festgelegt.  
  
1.  Wählen Sie die <xref:System.Windows.Forms.DataGridView> Steuerelement im Designer.  
  
2.  In der **Eigenschaften** Fenster, klicken Sie auf die Schaltfläche mit den Auslassungspunkten (![VisualStudioEllipsesButton-bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, oder <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> Eigenschaft. Die **CellStyle-Generator** Dialogfeld wird angezeigt.  
  
3.  Definieren Sie durch Festlegen der Eigenschaften, die über den Stil der **Vorschau** Bereich, um Ihre Auswahl zu bestätigen.  
  
> [!NOTE]
>  Wenn visuelle Stile aktiviert sind, die Zeilen- und Spaltenüberschriften (mit Ausnahme der <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) automatisch angewendet, das aktuelle Design, das Überschreiben der <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> und <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> Eigenschaftswerte.  
>   
>  Sie können festlegen, Zellstile für mehrere ausgewählte <xref:System.Windows.Forms.DataGridView> Steuerelemente im Designer jedoch nur verwenden, vorausgesetzt, Sie verfügen über identische Werte für die Zelle Style-Eigenschaft, die Sie ändern möchten. Wenn einer der Zellenstile für diese Eigenschaft unterscheiden sich die **Eigenschaften** Windows von der **CellStyle-Generator** Dialogfeld wird leer gelassen werden.  
  
### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>Standard-Formate für Zellen in den einzelnen Spalten festlegen  
  
1.  Mit der rechten Maustaste die <xref:System.Windows.Forms.DataGridView> steuern im Designer, und wählen Sie **Spalten bearbeiten**.  
  
2.  Wählen Sie eine Spalte aus der **Selected Columns** Liste.  
  
3.  In der **Spalteneigenschaften** Raster klicken Sie auf die Schaltfläche mit den Auslassungspunkten (![VisualStudioEllipsesButton-bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> Eigenschaft. Die **CellStyle-Generator** Dialogfeld wird angezeigt.  
  
4.  Definieren Sie durch Festlegen der Eigenschaften, die über den Stil der **Vorschau** Bereich, um Ihre Auswahl zu bestätigen.  
  
### <a name="to-format-data-in-cells"></a>So formatieren Sie Daten in Zellen  
  
1.  Verwenden Sie eine der vorangehenden Verfahren zum Anzeigen einer **CellStyle-Generator** Dialogfeld im Zusammenhang mit der eine standardmäßige Zelle Style-Eigenschaft.  
  
2.  In der **CellStyle-Generator** Dialogfeld klicken Sie auf die Schaltfläche mit den Auslassungspunkten (![VisualStudioEllipsesButton-bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben dem <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> Diese Eigenschaft. Die **Formatzeichenfolge** Dialogfeld wird angezeigt.  
  
3.  Wählen Sie einen Formattyp aus, und ändern Sie die Details des Typs (z. B. die Anzahl der anzuzeigenden Dezimalstellen), mit der **Beispiel** Feld, um Ihre Auswahl zu bestätigen.  
  
4.  Wenn Sie binden die <xref:System.Windows.Forms.DataGridView> Steuerelement mit einer Datenquelle, die wahrscheinlich zu null-Werte enthalten, geben Sie die **Null-Wert** Textfeld. Dieser Wert wird angezeigt, wenn der Wert der Zelle ein null-Verweis entspricht (`Nothing` in Visual Basic) oder <xref:System.DBNull.Value?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [Zellstile im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Festlegen von abwechselnden Zeilenstilen für das DataGridView-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Create a New Windows Forms Application Project (Vorgehensweise: Erstellen Sie ein Windows-Anwendungsprojekt)](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
