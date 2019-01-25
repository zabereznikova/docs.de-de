---
title: 'Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle mithilfe des Designers'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
ms.openlocfilehash: 414c989d258ca4b7a9097afa2b7f2407505fb629
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687582"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a>Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle mithilfe des Designers

> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Die Windows-Formulare <xref:System.Windows.Forms.DataGrid> Steuerelement wurde speziell zur Anzeige von Informationen aus einer Datenquelle. Binden des Steuerelements zur Entwurfszeit durch Festlegen der <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften oder zur Laufzeit durch Aufrufen der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode. Obwohl Sie Daten aus einer Vielzahl von Datenquellen anzeigen können, sind die häufigsten Quellen Datasets und Ansichten.  
  
 Wenn die Datenquelle zur Entwurfszeit verfügbar ist – z. B., wenn das Formular eine Instanz eines Datasets oder eine Data source View enthält – Sie können im Raster mit der Datenquelle zur Entwurfszeit zu binden. Sie können dann anzeigen, wie die Daten im Raster aussehen werden.  
  
 Sie können im Raster auch programmgesteuert zur Laufzeit binden. Dies ist nützlich, wenn Sie eine Datenquelle basierend auf Informationen, die Sie zur Laufzeit erhalten festlegen möchten. Beispielsweise kann die Anwendung den Benutzer aus, geben Sie den Namen einer Tabelle anzeigen können. Es ist auch in Situationen, in dem die Datenquelle zur Entwurfszeit noch nicht vorhanden ist, erforderlich. Dazu gehören Datenquellen wie z. B. Arrays, Auflistungen, nicht typisierte Datasets und Datenleser.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.DataGrid> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). In Visual Studio 2005 die <xref:System.Windows.Forms.DataGrid> Steuerelement befindet sich nicht in der **Toolbox** standardmäßig. Informationen zum Hinzufügen, finden Sie unter [Vorgehensweise: Hinzufügen von Elementen zur Toolbox](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0). Darüber hinaus in Visual Studio 2005 können Sie mithilfe der **Datenquellen** Fenster für die Datenbindung zur Entwurfszeit. Weitere Informationen finden Sie unter [Binden von Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a>An Daten des DataGrid-Steuerelements an eine einzelne Tabelle im Designer gebunden werden soll  
  
1.  Legen Sie die <xref:System.Windows.Forms.DataGrid.DataSource%2A> Eigenschaft, um das Objekt, enthält die Datenelemente, die Sie binden möchten.  
  
2.  Wenn die Datenquelle ein Dataset ist, legen Sie die <xref:System.Windows.Forms.DataGrid.DataMember%2A> -Eigenschaft auf den Namen der Tabelle zu binden.  
  
3.  Ist die Datenquelle ein Dataset oder eine basierend auf einer Dataset-Tabelle an, fügen Sie Code zum Formular, um das Dataset zu füllen.  
  
     Die genaue Code, den Sie verwenden, hängt davon ab, in dem das Dataset Daten erhält. Wenn der Dataset direkt aus einer Datenbank gefüllt wird, rufen Sie in der Regel die `Fill` Methode eines Datenadapters, wie im folgenden Codebeispiel wird, die aufgefüllt, ein Dataset mit dem Namen wird `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  (Optional) Fügen Sie die geeigneten Tabellen- und Spaltenformate zum Raster an.  
  
     Wenn es keine Tabellenformate sind, sehen Sie in der Tabelle, jedoch mit minimaler Formatierung und alle Spalten angezeigt.  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a>Klicken Sie auf dem DataGrid-Steuerelement an mehrere Tabellen in einem Dataset in der Designer Datenbindung  
  
1.  Legen Sie die <xref:System.Windows.Forms.DataGrid.DataSource%2A> Eigenschaft, um das Objekt, enthält die Datenelemente, die Sie binden möchten.  
  
2.  Wenn das Dataset über verknüpfte Tabellen enthält (d. h. wenn er ein Relation-Objekt enthält), legen die <xref:System.Windows.Forms.DataGrid.DataMember%2A> -Eigenschaft auf den Namen der übergeordneten Tabelle.  
  
3.  Schreiben Sie Code aus, um das Dataset zu füllen.  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über das DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [Windows Forms-Datenbindung](../../../../docs/framework/winforms/windows-forms-data-binding.md)
- [Zugreifen auf Daten in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)
