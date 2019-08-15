---
title: 'Vorgehensweise: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: d11c4f7e4cdfb597477bb99f38612ed648849f20
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040052"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Vorgehensweise: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms mithilfe des Designers

> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Sie <xref:System.Windows.Forms.DataGrid> können Daten im Windows Forms-Steuerelement in Tabellen und Spalten anzeigen, indem Sie-Objekte erstellen <xref:System.Windows.Forms.DataGridTableStyle> und <xref:System.Windows.Forms.GridTableStylesCollection> Sie dem-Objekt hinzufügen, <xref:System.Windows.Forms.DataGrid> auf das <xref:System.Windows.Forms.DataGrid.TableStyles%2A> über die-Eigenschaft des-Steuer Elements zugegriffen wird. Jedes Tabellenformat zeigt den Inhalt einer beliebigen Datentabelle an, die in <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> der-Eigenschaft <xref:System.Windows.Forms.DataGridTableStyle>von angegeben ist. Standardmäßig werden in einem Tabellenformat ohne angegebene Spalten Formate alle Spalten in der Datentabelle angezeigt. Sie können einschränken, welche Spalten <xref:System.Windows.Forms.DataGridColumnStyle> aus der Tabelle angezeigt <xref:System.Windows.Forms.GridColumnStylesCollection>werden, indem Sie-Objekte hinzufügen, auf <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> die über die <xref:System.Windows.Forms.DataGridTableStyle>-Eigenschaft der einzelnen Objekte zugegriffen wird.

Die folgenden Prozeduren erfordern ein **Windows-Anwendungs** Projekt mit einem Formular <xref:System.Windows.Forms.DataGrid> , das ein-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu. Standardmäßig befindet sich das <xref:System.Windows.Forms.DataGrid> Steuerelement in Visual Studio 2005 nicht in der **Toolbox**. Weitere Informationen zum Hinzufügen finden [Sie unter Gewusst wie: Fügen Sie der Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))Elemente hinzu.

### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>So fügen Sie dem DataGrid-Steuerelement im Designer eine Tabelle hinzu

1. Um Daten in der Tabelle anzuzeigen, müssen Sie zuerst das <xref:System.Windows.Forms.DataGrid> Steuerelement an ein DataSet binden. Weitere Informationen finden Sie unter [Vorgehensweise: Binden Sie das Windows Forms DataGrid-Steuerelement mithilfe des Designers](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)an eine Datenquelle.

2. Wählen Sie <xref:System.Windows.Forms.DataGrid> im Eigenschaftenfenster die-Eigenschaft des Steuer Elements aus, und klicken Sie dann auf![die Schaltfläche mit den Auslassungs Punkten (...) in der Eigenschaftenfenster](./media/visual-studio-ellipsis-button.png)von Visual Studio.) neben der- <xref:System.Windows.Forms.DataGrid.TableStyles%2A> Eigenschaft, um das **DataGridTableStyle**-Auflistungs-Editor.

3. Klicken Sie im Auflistungs-Editor auf **Hinzufügen** , um einen Tabellen Stil einzufügen.

4. Klicken Sie auf **OK** , um den Auflistungs-Editor zu schließen, und öffnen Sie ihn dann erneut <xref:System.Windows.Forms.DataGrid.TableStyles%2A> , indem Sie neben der-Eigenschaft auf die Schaltfläche

     Wenn Sie den Auflistungs-Editor erneut öffnen, werden alle Datentabellen, die an das-Steuerelement gebunden sind <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> , in der Dropdown Liste für die-Eigenschaft des Tabellen Stils angezeigt.

5. Klicken Sie im Auflistungs-Editor im Feld **Mitglieder** auf den Tabellen Stil.

6. Wählen Sie im **Eigenschaften** Feld des Auflistungs-Editors <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> den Wert für die Tabelle aus, die Sie anzeigen möchten.

### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>So fügen Sie dem DataGrid-Steuerelement im Designer eine Spalte hinzu

1. Wählen Sie im **DataGridTableStyle**-Auflistungs-Editor im Feld **Mitglieder** den entsprechenden Tabellen Stil aus. Wählen Sie im **Eigenschaften** Feld des Auflistungs-Editors <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> die Auflistung aus, und klicken Sie dann auf die![Schaltfläche mit den Auslassungs Punkten (die Schaltfläche mit den Auslassungs Punkten](./media/visual-studio-ellipsis-button.png)(...) im Eigenschaftenfenster von Visual Studio.) neben der-Eigenschaft auf. Anzeigen des **DataGridColumnStyle**-Auflistungs-Editors.

2. Klicken Sie im Auflistungs-Editor auf **Hinzufügen** , um einen Spalten Stil einzufügen, oder auf den Pfeil nach unten neben **Hinzufügen** , um einen Spaltentyp anzugeben.

     Im Dropdown Feld können Sie entweder den-Typ oder <xref:System.Windows.Forms.DataGridTextBoxColumn> <xref:System.Windows.Forms.DataGridBoolColumn> den-Typ auswählen.

3. Klicken Sie auf OK, um den **DataGridColumnStyle**-Auflistungs-Editor zu schließen, und öffnen Sie ihn dann <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> erneut, indem Sie neben der-Eigenschaft auf die Schaltfläche

     Wenn Sie den Auflistungs-Editor erneut öffnen, werden alle Datenspalten in der gebundenen Datentabelle in der Dropdown Liste <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> für die-Eigenschaft des Spalten Stils angezeigt.

4. Klicken Sie im Auflistungs-Editor im Feld **Mitglieder** auf den Spalten Stil.

5. Wählen Sie im **Eigenschaften** Feld des Auflistungs-Editors <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> den Wert für die Spalte aus, die Sie anzeigen möchten.

## <a name="see-also"></a>Siehe auch

- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
- [Vorgehensweise: Löschen oder Ausblenden von Spalten im Windows Forms DataGrid-Steuerelement](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
