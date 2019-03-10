---
title: 'Vorgehensweise: Hinzufügen von Tabellen und Spalten zu der DataGrid-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: 741da635ec187d8605a9f67aa010ff49a83ba86b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725349"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Vorgehensweise: Hinzufügen von Tabellen und Spalten zu der DataGrid-Steuerelement in Windows Forms mithilfe des Designers

> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Sie können Daten anzeigen, in Windows Forms <xref:System.Windows.Forms.DataGrid> -Steuerelement in Tabellen und Spalten durch das Erstellen <xref:System.Windows.Forms.DataGridTableStyle> Objekte und Hinzufügen der Benutzer zur der <xref:System.Windows.Forms.GridTableStylesCollection> -Objekt, das über zugegriffen wird die <xref:System.Windows.Forms.DataGrid> des Steuerelements <xref:System.Windows.Forms.DataGrid.TableStyles%2A> Eigenschaft. Jedes Format zeigt den Inhalt der Datentabelle, in angegeben ist der <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridTableStyle>. Ein Tabellenformat ohne Spaltenformate angegeben werden standardmäßig alle Spalten innerhalb dieser Datentabelle angezeigt. Können Sie einschränken, welche Spalten aus der Tabelle angezeigt werden, indem das Hinzufügen von <xref:System.Windows.Forms.DataGridColumnStyle> Objekte die <xref:System.Windows.Forms.GridColumnStylesCollection>, das erfolgt über die <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Eigenschaft der einzelnen <xref:System.Windows.Forms.DataGridTableStyle>.  
  
 Benötigen Sie die folgenden Verfahren eine **Windows-Anwendung** -Projekt mit einem Formular mit einer <xref:System.Windows.Forms.DataGrid> Steuerelement. Informationen zum Festlegen eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md). Standardmäßig in Visual Studio 2005 die <xref:System.Windows.Forms.DataGrid> Steuerelement befindet sich nicht in der **Toolbox**. Informationen zum Hinzufügen, finden Sie unter [Vorgehensweise: Hinzufügen von Elementen zur Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Zum Hinzufügen einer Tabelle zum DataGrid-Steuerelement im designer  
  
1.  Sie müssen zuerst binden, um Daten in der Tabelle anzuzeigen, die <xref:System.Windows.Forms.DataGrid> Steuerelement zu einem Dataset. Weitere Informationen finden Sie unter [Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle mithilfe des Designers](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).  
  
2.  Wählen Sie die <xref:System.Windows.Forms.DataGrid> des Steuerelements <xref:System.Windows.Forms.DataGrid.TableStyles%2A> Eigenschaft im Eigenschaftenfenster, und klicken Sie dann auf die Schaltfläche mit den Auslassungspunkten (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) neben die Eigenschaft zum Anzeigen der **DataGridTableStyle Auflistungs-Editor**.  
  
3.  Klicken Sie im auflistungs-Editor auf **hinzufügen** ein Tabellenformat eingefügt.  
  
4.  Klicken Sie auf **OK** den auflistungs-Editor zu schließen und erneut öffnen, indem Sie auf die Schaltfläche mit den Auslassungspunkten neben der <xref:System.Windows.Forms.DataGrid.TableStyles%2A> Eigenschaft.  
  
     Wenn Sie den auflistungs-Editor erneut öffnen, erscheint in der Dropdown-Liste für alle Datentabellen, die an das Steuerelement gebunden der <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> das Format der Eigenschaft.  
  
5.  In der **Mitglieder** Feld von der auflistungs-Editor, klicken Sie auf das Tabellenformat.  
  
6.  In der **Eigenschaften** im Feld den auflistungs-Editor auf die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> Wert für die Tabelle, die Sie anzeigen möchten.  
  
### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Hinzufügen eine Spalte zum DataGrid-Steuerelement im designer  
  
1.  In der **Mitglieder** im Feld der **DataGridTableStyle Auflistungs-Editor**, wählen Sie den Stil der entsprechenden Tabelle. In der **Eigenschaften** im Feld den auflistungs-Editor wählen die <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> -Auflistung, und klicken Sie dann auf die Schaltfläche mit den Auslassungspunkten (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png " VbEllipsesButton")) neben der Eigenschaft zum Anzeigen der **DataGridColumnStyle Auflistungs-Editor**.  
  
2.  Klicken Sie im auflistungs-Editor auf **hinzufügen** ein Spaltenformat einfügen, oder klicken Sie auf den Pfeil nach unten neben **hinzufügen** zum Angeben eines Spaltentyps.  
  
     In der Dropdown-Feld, Sie haben die Wahl zwischen der <xref:System.Windows.Forms.DataGridTextBoxColumn> oder <xref:System.Windows.Forms.DataGridBoolColumn> Typ.  
  
3.  Klicken Sie auf OK, um schließen die **DataGridColumnStyle Auflistungs-Editor**, und erneut öffnen, indem Sie auf die Schaltfläche mit den Auslassungspunkten neben der <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Eigenschaft.  
  
     Wenn Sie den auflistungs-Editor erneut öffnen, erscheint in der Dropdown-Liste für alle Datenspalten in der gebundenen Datentabelle die <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> Eigenschaft von das Spaltenformat.  
  
4.  In der **Mitglieder** Feld von der auflistungs-Editor, klicken Sie auf das Spaltenformat.  
  
5.  In der **Eigenschaften** im Feld den auflistungs-Editor auf die <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> Wert für die Spalte, die Sie anzeigen möchten.  
  
## <a name="see-also"></a>Siehe auch
- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
- [Vorgehensweise: Löschen oder Ausblenden von Spalten im DataGrid-Steuerelement in Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
