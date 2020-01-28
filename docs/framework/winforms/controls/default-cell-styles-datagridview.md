---
title: Festlegen von Standardzellen Stilen und Datenformaten für das DataGridView-Steuerelement mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: ca602fa15e4648550bfa171a9c3abd057e930eca
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731361"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Gewusst wie: Festlegen von standardmäßigen Zellenstilen und Datenformaten für das DataGridView-Steuerelement in Windows Forms mithilfe des Designers

Mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement können Sie Standardzellen Stile und Zellen Datenformate für das gesamte-Steuerelement, für bestimmte Spalten, für Zeilen-und Spaltenüberschriften und für abwechselnde Zeilen angeben, um einen Ledger-Effekt zu erstellen. Standard Stile, die für das gesamte-Steuerelement festgelegt sind, werden von Standard Stilen überschrieben, die für Spalten und abwechselnde Zeilen Außerdem überschreiben Stile, die Sie im Code für einzelne Zeilen und Zellen festlegen, die Standard Stile.

Weitere Informationen zu Zell Formaten finden Sie unter [Zellen Stile im Windows Forms DataGridView-Steuer](cell-styles-in-the-windows-forms-datagridview-control.md)Element. Informationen zum Festlegen von Stilen für abwechselnde Zeilen finden Sie unter Gewusst [wie: Festlegen von abwechselnden Zeilen Stilen für das Windows Forms DataGridView-Steuerelement mithilfe des Designers](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).

Sie können auch Stile mithilfe der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>-Eigenschaft festlegen, um alle Zeilen zu beeinflussen, die dem Steuerelement hinzugefügt werden. Weitere Informationen zur Zeilen Vorlage finden Sie unter Gewusst [wie: Verwenden der Zeilen Vorlage zum Anpassen von Zeilen im Windows Forms DataGridView-Steuer](use-the-row-template-to-customize-rows-in-the-datagrid.md)Element.

Die folgenden Prozeduren erfordern ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.DataGridView>-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>So legen Sie Standard Stile für alle Zellen im Steuerelement fest

1. Wählen Sie im Designer das <xref:System.Windows.Forms.DataGridView>-Steuerelement aus.

2. Klicken Sie im **Eigenschaften** Fenster auf die Schaltfläche mit den Auslassungs Punkten (![die Schaltfläche mit den Auslassungs Punkten (...) in der Eigenschaftenfenster von Visual Studio.](./media/visual-studio-ellipsis-button.png)) neben der <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>-, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>-oder <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>-Eigenschaft. Das Dialogfeld **CellStyle Builder** wird angezeigt.

3. Definieren Sie den Stil durch Festlegen der Eigenschaften, indem Sie den **Vorschau** Bereich verwenden, um Ihre Auswahl zu bestätigen.

> [!NOTE]
> Wenn visuelle Stile aktiviert sind, werden die Zeilen-und Spaltenüberschriften (mit Ausnahme des <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) automatisch durch das aktuelle Design formatiert, wobei die <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>-und <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>-Eigenschaftswerte überschrieben werden.
>
> Sie können Zellen Stile für mehrere ausgewählte <xref:System.Windows.Forms.DataGridView> Steuerelemente mithilfe des Designers festlegen, aber nur, wenn Sie identische Werte für die Eigenschaft für den Zellstil haben, die Sie ändern möchten. Wenn sich für diese Eigenschaft beliebige Zellstile unterscheiden, sind die Fenster **Eigenschaften** des Dialog Felds **CellStyle Builder** leer.

### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>So legen Sie Standard Stile für Zellen in einzelnen Spalten fest

1. Klicken Sie im Designer mit der rechten Maustaste auf das <xref:System.Windows.Forms.DataGridView>-Steuerelement, und wählen Sie **Spalten bearbeiten**

2. Wählen Sie in der Liste **Ausgewählte Spalten** eine Spalte aus.

3. Klicken Sie im Raster **Spalten Eigenschaften** auf die Schaltfläche mit den Auslassungs Punkten (![der Schaltfläche mit den Auslassungs Punkten (...) in der Eigenschaftenfenster von Visual Studio.](./media/visual-studio-ellipsis-button.png)) neben der <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>-Eigenschaft. Das Dialogfeld **CellStyle Builder** wird angezeigt.

4. Definieren Sie den Stil durch Festlegen der Eigenschaften, indem Sie den **Vorschau** Bereich verwenden, um Ihre Auswahl zu bestätigen.

### <a name="to-format-data-in-cells"></a>So formatieren Sie Daten in Zellen

1. Verwenden Sie eines der oben aufgeführten Prozeduren, um ein Dialogfeld für den **CellStyle** -Generator anzuzeigen

2. Klicken Sie im Dialogfeld **CellStyle** Generator auf die Schaltfläche mit den Auslassungs Punkten (![der Schaltfläche mit den Auslassungs Punkten (...) in der Eigenschaftenfenster von Visual Studio.](./media/visual-studio-ellipsis-button.png)) neben der <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>-Eigenschaft. Das Dialogfeld **Format Zeichenfolge** wird angezeigt.

3. Wählen Sie einen Formattyp aus, und ändern Sie dann die Details des Typs (z. b. die Anzahl der anzuzeigenden Dezimalstellen), indem Sie das **Beispiel** Feld verwenden, um Ihre Auswahl zu bestätigen.

4. Wenn Sie das <xref:System.Windows.Forms.DataGridView>-Steuerelement an eine Datenquelle binden, die wahrscheinlich NULL-Werte enthält, füllen Sie das Textfeld **NULL-Wert** aus. Dieser Wert wird angezeigt, wenn der Zellwert einem NULL-Verweis (`Nothing` in Visual Basic) oder <xref:System.DBNull.Value?displayProperty=nameWithType>entspricht.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Gewusst wie: Festlegen von abwechselnden Zeilenstilen für das Windows Forms-Steuerelement DataGridView mithilfe des Designers](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
