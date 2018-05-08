---
title: 'Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: 4b29a3040415cce8fad27abf9bf46aa3d3e14b4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms mithilfe des Designers
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Zeigen Sie Daten in Windows Forms <xref:System.Windows.Forms.DataGrid> -Steuerelement in Tabellen und Spalten durch das Erstellen <xref:System.Windows.Forms.DataGridTableStyle> -Objekte und durch Hinzufügen, damit die <xref:System.Windows.Forms.GridTableStylesCollection> -Objekt, das über zugegriffen wird die <xref:System.Windows.Forms.DataGrid> des Steuerelements <xref:System.Windows.Forms.DataGrid.TableStyles%2A> Eigenschaft. Jedes Tabellenformat zeigt den Inhalt der Datentabelle, in angegeben ist der <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> Eigenschaft von der <xref:System.Windows.Forms.DataGridTableStyle>. Ein Tabellenformat ohne Spaltenformate angegeben werden in der Standardeinstellung alle Spalten in der Datentabelle angezeigt. Können Sie einschränken, welche Spalten aus der Tabelle angezeigt werden, indem das Hinzufügen von <xref:System.Windows.Forms.DataGridColumnStyle> Datenbankobjekte in der <xref:System.Windows.Forms.GridColumnStylesCollection>, die erfolgt über die <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> -Eigenschaft jedes <xref:System.Windows.Forms.DataGridTableStyle>.  
  
 Benötigen Sie die folgenden Verfahren eine **Windows-Anwendung** -Projekts mit einem Formular, enthält ein <xref:System.Windows.Forms.DataGrid> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). Standardmäßig in [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> Steuerelement befindet sich nicht in der **Toolbox**. Informationen zum Hinzufügen, finden Sie unter [wie: Hinzufügen von Elementen zur Toolbox](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>DataGrid-Steuerelement im Designer eine Tabelle hinzu  
  
1.  Sie müssen zuerst binden, um die Daten in der Tabelle anzuzeigen, die <xref:System.Windows.Forms.DataGrid> Steuerelement zu einem Dataset. Weitere Informationen finden Sie unter [Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms in einer Datenquelle mit dem Designer](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).  
  
2.  Wählen Sie die <xref:System.Windows.Forms.DataGrid> des Steuerelements <xref:System.Windows.Forms.DataGrid.TableStyles%2A> Eigenschaft im Eigenschaftenfenster, und klicken Sie dann auf die Schaltfläche mit den Auslassungspunkten (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) neben die Eigenschaft zum Anzeigen der **DataGridTableStyle Auflistungs-Editor**.  
  
3.  Klicken Sie in den auflistungs-Editor auf **hinzufügen** ein Tabellenformat einfügen.  
  
4.  Klicken Sie auf **OK** den auflistungs-Editor zu schließen und erneut öffnen, indem Sie auf die Schaltfläche mit den Auslassungszeichen neben der <xref:System.Windows.Forms.DataGrid.TableStyles%2A> Eigenschaft.  
  
     Wenn Sie den auflistungs-Editor erneut öffnen, erscheint in der Dropdown-Liste für alle Datentabellen, die mit dem Steuerelement verbunden die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> Eigenschaft Tabellenformat.  
  
5.  In der **Elemente** Feld für den auflistungs-Editor, klicken Sie auf das Tabellenformat.  
  
6.  In der **Eigenschaften** im Feld der Auflistungseditor der <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> Wert für die Tabelle, die Sie anzeigen möchten.  
  
### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>DataGrid-Steuerelement im Designer eine Spalte hinzu  
  
1.  In der **Elemente** im Feld der **DataGridTableStyle Auflistungs-Editor**, wählen Sie den Stil der entsprechenden Tabelle. In der **Eigenschaften** im Feld der Auflistungseditor der <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> -Auflistung, und klicken Sie dann auf die Schaltfläche mit den Auslassungspunkten (![von VisualStudioEllipsesButton] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " VbEllipsesButton")) neben der Eigenschaft zum Anzeigen der **DataGridColumnStyle Auflistungs-Editor**.  
  
2.  Klicken Sie in den auflistungs-Editor auf **hinzufügen** ein Spaltenformat einfügen, oder klicken Sie auf den Pfeil nach unten neben **hinzufügen** Spaltentyp an.  
  
     Klicken Sie im Dropdown-Menü Wählen Sie entweder die <xref:System.Windows.Forms.DataGridTextBoxColumn> oder <xref:System.Windows.Forms.DataGridBoolColumn> Typ.  
  
3.  Klicken Sie auf OK, um das Schließen der **DataGridColumnStyle Auflistungs-Editor**, und erneut öffnen, indem Sie auf die Schaltfläche mit den Auslassungszeichen neben der <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Eigenschaft.  
  
     Wenn Sie den auflistungs-Editor erneut öffnen, erscheint in der Dropdown-Liste für alle Datenspalten in der Tabelle gebundenen Daten, die die <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> Eigenschaft, von das Spaltenformat.  
  
4.  In der **Elemente** Feld für den auflistungs-Editor, klicken Sie auf das Spaltenformat.  
  
5.  In der **Eigenschaften** im Feld der Auflistungseditor der <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> Wert für die Spalte, die Sie anzeigen möchten.  
  
## <a name="see-also"></a>Siehe auch  
 [DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
