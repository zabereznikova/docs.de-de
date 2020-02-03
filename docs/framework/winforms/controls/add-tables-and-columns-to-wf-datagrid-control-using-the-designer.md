---
title: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: fed7465fbe665b1945161653616e3a21640e0b2a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746267"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms mithilfe des Designers

> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Sie können Daten in der Windows Forms <xref:System.Windows.Forms.DataGrid>-Steuerelement in Tabellen und Spalten anzeigen, indem Sie <xref:System.Windows.Forms.DataGridTableStyle>-Objekte erstellen und Sie dem <xref:System.Windows.Forms.GridTableStylesCollection>-Objekt hinzufügen, auf das über die <xref:System.Windows.Forms.DataGrid>-Eigenschaft des <xref:System.Windows.Forms.DataGrid.TableStyles%2A>-Steuer Elements zugegriffen wird. Jedes Tabellenformat zeigt den Inhalt einer beliebigen Datentabelle an, die in der <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>-Eigenschaft der <xref:System.Windows.Forms.DataGridTableStyle>angegeben ist. Standardmäßig werden in einem Tabellenformat ohne angegebene Spalten Formate alle Spalten in der Datentabelle angezeigt. Sie können einschränken, welche Spalten aus der Tabelle angezeigt werden, indem Sie <xref:System.Windows.Forms.DataGridColumnStyle> Objekte zur <xref:System.Windows.Forms.GridColumnStylesCollection>hinzufügen, auf die Sie über die <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>-Eigenschaft der einzelnen <xref:System.Windows.Forms.DataGridTableStyle>zugreifen.

Die folgenden Prozeduren erfordern ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.DataGrid> Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md). Standardmäßig befindet sich das <xref:System.Windows.Forms.DataGrid>-Steuerelement in Visual Studio 2005 nicht in der **Toolbox**. Weitere Informationen zum Hinzufügen finden Sie unter Gewusst [wie: Hinzufügen von Elementen zur Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>So fügen Sie dem DataGrid-Steuerelement im Designer eine Tabelle hinzu

1. Um Daten in der Tabelle anzuzeigen, müssen Sie zuerst das <xref:System.Windows.Forms.DataGrid>-Steuerelement an ein DataSet binden. Weitere Informationen finden Sie unter Gewusst [wie: Binden des Windows Forms DataGrid-Steuer Elements an eine Datenquelle mithilfe des Designers](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).

2. Wählen Sie im Eigenschaftenfenster die <xref:System.Windows.Forms.DataGrid.TableStyles%2A> Eigenschaft des <xref:System.Windows.Forms.DataGrid> Steuer Elements aus, und klicken Sie dann auf die Schaltfläche mit den Auslassungs Zeichen![(...) im Eigenschaftenfenster von Visual Studio.](./media/visual-studio-ellipsis-button.png)) neben der-Eigenschaft, um den **DataGridTableStyle**-Auflistungs-Editor anzuzeigen.

3. Klicken Sie im Auflistungs-Editor auf **Hinzufügen** , um einen Tabellen Stil einzufügen.

4. Klicken Sie auf **OK** , um den Auflistungs-Editor zu schließen, und öffnen Sie ihn, indem Sie auf die Schaltfläche mit den Auslassungs Punkten neben <xref:System.Windows.Forms.DataGrid.TableStyles%2A> der

     Wenn Sie den Auflistungs-Editor erneut öffnen, werden alle Datentabellen, die an das-Steuerelement gebunden sind, in der Dropdown Liste für die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>-Eigenschaft des Tabellen Stils angezeigt.

5. Klicken Sie im Auflistungs-Editor im Feld **Mitglieder** auf den Tabellen Stil.

6. Wählen Sie im **Eigenschaften** Feld des Auflistungs-Editors den <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> Wert für die Tabelle aus, die Sie anzeigen möchten.

### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>So fügen Sie dem DataGrid-Steuerelement im Designer eine Spalte hinzu

1. Wählen Sie im **DataGridTableStyle**-Auflistungs-Editor im Feld **Mitglieder** den entsprechenden Tabellen Stil aus. Wählen Sie im **Eigenschaften** Feld des Auflistungs-Editors die <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Auflistung aus, und klicken Sie dann auf die Schaltfläche mit den Auslassungs Zeichen![(...) im Eigenschaftenfenster von Visual Studio.](./media/visual-studio-ellipsis-button.png)) neben der-Eigenschaft, um den **DataGridColumnStyle**-Auflistungs-Editor anzuzeigen.

2. Klicken Sie im Auflistungs-Editor auf **Hinzufügen** , um einen Spalten Stil einzufügen, oder auf den Pfeil nach unten neben **Hinzufügen** , um einen Spaltentyp anzugeben.

     Im Dropdown Feld können Sie entweder den Typ <xref:System.Windows.Forms.DataGridTextBoxColumn> oder <xref:System.Windows.Forms.DataGridBoolColumn> auswählen.

3. Klicken Sie auf OK, um den **DataGridColumnStyle**-Auflistungs-Editor zu schließen, und öffnen Sie ihn erneut, indem Sie <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> auf die Schaltfläche mit den Auslassungs Punkten neben

     Wenn Sie den Auflistungs-Editor erneut öffnen, werden alle Datenspalten in der gebundenen Datentabelle in der Dropdown Liste für die <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A>-Eigenschaft des Spalten Stils angezeigt.

4. Klicken Sie im Auflistungs-Editor im Feld **Mitglieder** auf den Spalten Stil.

5. Wählen Sie im **Eigenschaften** Feld des Auflistungs-Editors den <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> Wert für die Spalte aus, die Sie anzeigen möchten.

## <a name="see-also"></a>Weitere Informationen

- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
- [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
