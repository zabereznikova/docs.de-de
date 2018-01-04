---
title: "Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e0bde96442e09ee33a63cecd56a4cd6e2cf19a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a>Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle mithilfe des Designers
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Windows Forms <xref:System.Windows.Forms.DataGrid> Steuerelement ist speziell für die Anzeige von Informationen aus einer Datenquelle. Binden des Steuerelements zur Entwurfszeit durch Festlegen der <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften oder zur Laufzeit durch Aufrufen der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode. Obwohl Sie Daten aus einer Vielzahl von Datenquellen anzeigen können, sind die häufigsten Quellen Datasets und Ansichten.  
  
 Wenn die Datenquelle zur Entwurfszeit verfügbar ist – z. B., wenn das Formular eine Instanz eines Datasets oder einer Datenansicht enthält – Sie können das Raster zur Entwurfszeit an die Datenquelle binden. Anschließend können Sie anzeigen, wie die Daten im Raster aussehen werden.  
  
 Sie können im Raster auch programmgesteuert zur Laufzeit binden. Dies ist hilfreich, wenn Sie eine Datenquelle basierend auf Informationen erhalten Sie zur Laufzeit festlegen möchten. Beispielsweise kann die Anwendung den Benutzer aus, geben Sie den Namen einer Tabelle anzeigen lassen. Es ist auch in Situationen, in denen die Datenquelle zur Entwurfszeit nicht vorhanden ist, erforderlich. Dies schließt Datenquellen wie z. B. Arrays, Auflistungen, nicht typisierte Datasets und Datenleser.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.DataGrid> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> Steuerelement befindet sich nicht in der **Toolbox** standardmäßig. Informationen zum Hinzufügen, finden Sie unter [wie: Hinzufügen von Elementen zur Toolbox](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0). Darüber hinaus können in [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], können Sie die **Datenquellen** Fenster für die Datenbindung zur Entwurfszeit. Weitere Informationen finden Sie unter [Binden von Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a>Daten-binden von DataGrid-Steuerelement mit einer einzelnen Tabelle im designer  
  
1.  Legen Sie das Steuerelement <xref:System.Windows.Forms.DataGrid.DataSource%2A> Eigenschaft, um das Objekt mit den Datenelementen, die Sie binden möchten.  
  
2.  Wenn die Datenquelle ein Dataset ist, legen Sie die <xref:System.Windows.Forms.DataGrid.DataMember%2A> -Eigenschaft auf den Namen der Tabelle zu binden.  
  
3.  Ist die Datenquelle ein Dataset oder einer Datenansicht basierend auf einer Dataset-Tabelle, fügen Sie Code zum Formular, um das Dataset zu füllen.  
  
     Der genaue Code, den Sie verwenden, hängt davon ab, in dem das Dataset Daten erhält. Wenn das Dataset direkt aus einer Datenbank aufgefüllt wird, rufen Sie in der Regel die `Fill` Methode eines Datenadapters, wie im folgenden Codebeispiel wird, die ein Dataset mit dem Namen füllt `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  (Optional) Fügen Sie die entsprechenden Tabellenformate und Spaltenformate zum Raster an.  
  
     Wenn keine Tabellenformate sind, sehen Sie die Tabelle, jedoch mit minimaler Formatierung und alle Spalten angezeigt.  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a>Um das DataGrid-Steuerelement an mehrere Tabellen in einem Dataset im Designer Datenbindung  
  
1.  Legen Sie das Steuerelement <xref:System.Windows.Forms.DataGrid.DataSource%2A> Eigenschaft, um das Objekt mit den Datenelementen, die Sie binden möchten.  
  
2.  Wenn das Dataset verknüpfte Tabellen enthält (d. h., wenn sie über ein Beziehungsobjekt enthält), legen die <xref:System.Windows.Forms.DataGrid.DataMember%2A> -Eigenschaft auf den Namen der übergeordneten Tabelle.  
  
3.  Schreiben Sie Code zum Füllen des Datasets.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Windows Forms-Datenbindung](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Zugreifen auf Daten in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)
