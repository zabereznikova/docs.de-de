---
title: 'Vorgehensweise: Festlegen von standardmäßigen Zellenstilen und Datenformaten für das DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: 53faf31c8dd3be1606c491e95594c4aae5aedf98
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039671"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Vorgehensweise: Festlegen von standardmäßigen Zellenstilen und Datenformaten für das DataGridView-Steuerelement in Windows Forms mithilfe des Designers

Mit <xref:System.Windows.Forms.DataGridView> dem-Steuerelement können Sie Standardzellen Stile und Zellen Datenformate für das gesamte-Steuerelement, für bestimmte Spalten, für Zeilen-und Spaltenüberschriften und für abwechselnde Zeilen angeben, um einen Ledger-Effekt zu erstellen. Standard Stile, die für das gesamte-Steuerelement festgelegt sind, werden von Standard Stilen überschrieben, die für Spalten und abwechselnde Zeilen Außerdem überschreiben Stile, die Sie im Code für einzelne Zeilen und Zellen festlegen, die Standard Stile.

Weitere Informationen zu Zell Formaten finden Sie unter [Zellen Stile im Windows Forms DataGridView-Steuer](cell-styles-in-the-windows-forms-datagridview-control.md)Element. Informationen zum Festlegen von Stilen für abwechselnde [Zeilen finden Sie unter Gewusst wie: Festlegen von abwechselnden Zeilen Stilen für das Windows Forms DataGridView-Steuer](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)Element mithilfe des Designers.

Sie können auch Stile mithilfe der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> -Eigenschaft festlegen, um alle Zeilen zu beeinflussen, die dem Steuerelement hinzugefügt werden. Weitere Informationen zur Zeilen Vorlage finden [Sie unter Gewusst wie: Verwenden Sie die Zeilen Vorlage, um Zeilen im Windows Forms DataGridView-](use-the-row-template-to-customize-rows-in-the-datagrid.md)Steuerelement anzupassen.

Die folgenden Prozeduren erfordern ein **Windows-Anwendungs** Projekt mit einem <xref:System.Windows.Forms.DataGridView> Formular, das ein-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.


### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>So legen Sie Standard Stile für alle Zellen im Steuerelement fest

1. Wählen Sie <xref:System.Windows.Forms.DataGridView> das Steuerelement im Designer aus.

2. Klicken Sie im **Eigenschaften** Fenster auf die Schaltfläche mit den![Auslassungs Punkten (die Schaltfläche mit den Auslassungs Punkten (...](./media/visual-studio-ellipsis-button.png)) im Eigenschaftenfenster von Visual Studio. <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> ) neben der <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>-, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>-oder-Eigenschaft. Das Dialogfeld **CellStyle Builder** wird angezeigt.

3. Definieren Sie den Stil durch Festlegen der Eigenschaften, indem Sie den **Vorschau** Bereich verwenden, um Ihre Auswahl zu bestätigen.

> [!NOTE]
> Wenn visuelle Stile aktiviert sind, werden die Zeilen-und Spaltenüberschriften ( <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>außer dem) automatisch durch das aktuelle Design formatiert, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> wobei <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> die-Eigenschaft und die-Eigenschaftswerte überschrieben werden.
>
> Sie können Zellen Stile für mehrere ausgewählte <xref:System.Windows.Forms.DataGridView> Steuerelemente mithilfe des Designers festlegen, aber nur, wenn Sie über identische Werte für die zu ändernde Eigenschaft des Zellen Stils verfügen. Wenn sich für diese Eigenschaft beliebige Zellstile unterscheiden, sind die Fenster **Eigenschaften** des Dialog Felds **CellStyle Builder** leer.

### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>So legen Sie Standard Stile für Zellen in einzelnen Spalten fest

1. Klicken Sie im Designer <xref:System.Windows.Forms.DataGridView> mit der rechten Maustaste auf das Steuerelement, und wählen Sie **Spalten bearbeiten**.

2. Wählen Sie in der Liste **Ausgewählte Spalten** eine Spalte aus.

3. Klicken Sie im Raster **Spalten Eigenschaften** auf die Schaltfläche mit den![Auslassungs Punkten (die Schaltfläche mit den Auslassungs Punkten (...](./media/visual-studio-ellipsis-button.png)) im Eigenschaftenfenster von <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> Visual Studio.) neben der-Eigenschaft. Das Dialogfeld **CellStyle Builder** wird angezeigt.

4. Definieren Sie den Stil durch Festlegen der Eigenschaften, indem Sie den **Vorschau** Bereich verwenden, um Ihre Auswahl zu bestätigen.

### <a name="to-format-data-in-cells"></a>So formatieren Sie Daten in Zellen

1. Verwenden Sie eines der oben aufgeführten Prozeduren, um ein Dialogfeld für den **CellStyle** -Generator anzuzeigen

2. Klicken Sie im Dialogfeld **CellStyle** Generator auf die Schaltfläche mit den![Auslassungs Punkten (die Schaltfläche mit den Auslassungs Punkten (...](./media/visual-studio-ellipsis-button.png)) im Eigenschaftenfenster von <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> Visual Studio.) neben der-Eigenschaft. Das Dialogfeld **Format Zeichenfolge** wird angezeigt.

3. Wählen Sie einen Formattyp aus, und ändern Sie dann die Details des Typs (z. b. die Anzahl der anzuzeigenden Dezimalstellen), indem Sie das **Beispiel** Feld verwenden, um Ihre Auswahl zu bestätigen.

4. Wenn Sie das <xref:System.Windows.Forms.DataGridView> Steuerelement an eine Datenquelle binden, die wahrscheinlich NULL-Werte enthält, füllen Sie das Textfeld **NULL-Wert** aus. Dieser Wert wird angezeigt, wenn der Zellwert einem NULL-Verweis (`Nothing` in Visual Basic) oder <xref:System.DBNull.Value?displayProperty=nameWithType>entspricht.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Festlegen von abwechselnden Zeilen Stilen für das Windows Forms DataGridView-Steuerelement mithilfe des Designers](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
