---
title: 'Gewusst wie: Hinzufügen von Zeilendetails zu einem DataGrid-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: b6b0cc99c9833e514d2d52ecf139ab8e110f73e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>Gewusst wie: Hinzufügen von Zeilendetails zu einem DataGrid-Steuerelement
Bei Verwendung der <xref:System.Windows.Controls.DataGrid> -Steuerelement, können Sie die Präsentation der Daten anpassen, indem Sie Abschnitt einer Zeile hinzufügen. Hinzufügen eines Zeilendetailabschnitts ermöglicht Ihnen, einige Daten in einer Vorlage zu gruppieren, die optional sichtbar oder reduziert ist. Sie können z. B. Zeilendetails zum Hinzufügen einer <xref:System.Windows.Controls.DataGrid> stellt nur eine Zusammenfassung der Daten für jede Zeile in der <xref:System.Windows.Controls.DataGrid>, aber weitere Datenfelder präsentiert, wenn der Benutzer eine Zeile auswählt. Sie definieren die Vorlage für die Zeile im Abschnitt die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Eigenschaft. Die folgende Abbildung zeigt ein Beispiel für eine Zeilendetailabschnitt.  
  
 ![DataGrid mit Zeilendetails](../../../../docs/framework/wpf/controls/media/ndp-rowdetails.png "NDP_RowDetails")  
  
 Sie definieren die Details Zeilenvorlage als Inline-XAML oder als Ressource. In den folgenden Verfahren werden beide Ansätze angezeigt. Eine Datenvorlage, die als eine Ressource im Verlauf des Projekts verwendet werden kann, ohne das erneute Erstellen der Vorlage hinzugefügt wird. Eine Datenvorlage, die hinzugefügt wird, als Inline-XAML nur über das Steuerelement zugegriffen werden kann, wo er definiert ist.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>Anzuzeigende Zeilendetails mit Inline-XAML  
  
1.  Erstellen einer <xref:System.Windows.Controls.DataGrid> , die Daten aus einer Datenquelle anzeigt.  
  
2.  Fügen Sie im <xref:System.Windows.Controls.DataGrid>-Element ein <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>-Element hinzu.  
  
3.  Erstellen einer <xref:System.Windows.DataTemplate> , definiert die Darstellung der Detailbereich Zeile.  
  
     Der folgende XAML-Code zeigt die <xref:System.Windows.Controls.DataGrid> und zum Definieren der <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Inline. Die <xref:System.Windows.Controls.DataGrid> zeigt drei Werte in jeder Zeile und drei weitere Werte an, wenn die Zeile ausgewählt ist.  
  
     [!code-xaml[DataGrid_RowDetails#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     Der folgende Code zeigt die Abfrage, die verwendet wird, um Daten auszuwählen, die in angezeigt wird der <xref:System.Windows.Controls.DataGrid>. In diesem Beispiel wählt die Abfrage Daten aus einer Entität, die Kundeninformationen enthält.  
  
     [!code-csharp[DataGrid_RowDetails#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>Um die Zeilendetails anzeigen, indem Sie eine Ressource  
  
1.  Erstellen einer <xref:System.Windows.Controls.DataGrid> , die Daten aus einer Datenquelle anzeigt.  
  
2.  Hinzufügen einer <xref:System.Windows.FrameworkElement.Resources%2A> Element dem Stammelement wie z. B. eine <xref:System.Windows.Window> Steuerelement oder ein <xref:System.Windows.Controls.Page> steuern, oder fügen eine <xref:System.Windows.Application.Resources%2A> Element der <xref:System.Windows.Application> Klasse in der Datei App.xaml (oder Application.xaml).  
  
3.  Erstellen Sie im Ressourcenelement, eine <xref:System.Windows.DataTemplate> , definiert die Darstellung der Detailbereich Zeile.  
  
     Der folgende XAML-Code zeigt die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definiert, der <xref:System.Windows.Application> Klasse.  
  
     [!code-xaml[DataGrid_RowDetails#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4.  Auf der <xref:System.Windows.DataTemplate>legen die [X: Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md) auf einen Wert, der die Datenvorlage eindeutig identifiziert.  
  
5.  In der <xref:System.Windows.Controls.DataGrid> -Elementgruppe, die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Eigenschaft auf die Ressource, die in den vorherigen Schritten definiert. Weisen Sie den Ressourcen als statische Ressource.  
  
     Der folgende XAML-Code zeigt die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> -Eigenschaft auf die Ressource aus dem vorherigen Beispiel.  
  
     [!code-xaml[DataGrid_RowDetails#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>Legen Sie die Sichtbarkeit und zu verhindern, dass horizontalen Bildlauf für Zeilendetails  
  
1.  Legen Sie bei Bedarf die <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> Eigenschaft, um eine <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> Wert.  
  
     Der Wert wird standardmäßig auf festgelegt <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>. Sie können sie festlegen, um <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> zum Anzeigen der Details für alle Zeilen oder <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> So blenden Sie die Details für alle Zeilen aus.  
  
2.  Legen Sie bei Bedarf die <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> Eigenschaft `true` erläutert, um zu verhindern, dass die Zeile einen horizontalen Bildlauf.
