---
title: 'Vorgehensweise: Hinzufügen von Zeilendetails zu einem DataGrid-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: d5b6539f3d379088528b9654861267988b6fc69b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317888"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>Vorgehensweise: Hinzufügen von Zeilendetails zu einem DataGrid-Steuerelement
Bei Verwendung der <xref:System.Windows.Controls.DataGrid> -Steuerelement, Sie können die Darstellung von Daten durch das Hinzufügen einer Zeilendetailabschnitt anpassen. Hinzufügen einer Zeilendetailabschnitt ermöglicht Ihnen, einige Daten in einer Vorlage zu gruppieren, die optional sichtbar oder ausgeblendet ist. Sie können z. B. Hinzufügen von Zeilendetails zu einem <xref:System.Windows.Controls.DataGrid> bereitstellt, die nur eine Zusammenfassung der Daten für jede Zeile in der <xref:System.Windows.Controls.DataGrid>, weitere Datenfelder angezeigt, wenn der Benutzer eine Zeile auswählt jedoch. Definieren Sie die Vorlage für den Zeilendetailabschnitt in die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Eigenschaft. Die folgende Abbildung zeigt ein Beispiel für eine Zeilendetailabschnitt.  
  
 ![DataGrid mit Zeilendetails](./media/ndp-rowdetails.png "NDP_RowDetails")  
  
 Sie definieren die Zeilendetailvorlage als XAML Inline oder als Ressource. In den folgenden Verfahren werden beide Ansätze beschrieben. Eine Datenvorlage, die hinzugefügt wird, wie eine Ressource im gesamten Projekt verwendet werden kann, ohne Vorlage neu zu erstellen. Eine Datenvorlage, die hinzugefügt wird, als Inline-XAML nur aus dem Steuerelement zugegriffen werden kann, wo sie definiert ist.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>Zum Anzeigen von Details für die Zeile mit Inline-XAML  
  
1. Erstellen Sie eine <xref:System.Windows.Controls.DataGrid> , die Daten aus einer Datenquelle anzeigt.  
  
2. Fügen Sie im <xref:System.Windows.Controls.DataGrid>-Element ein <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>-Element hinzu.  
  
3. Erstellen Sie eine <xref:System.Windows.DataTemplate> , die die Darstellung der Zeilendetailabschnitt definiert.  
  
     Das folgende XAML zeigt die <xref:System.Windows.Controls.DataGrid> und zum Definieren der <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Inline. Die <xref:System.Windows.Controls.DataGrid> zeigt drei Werte in jeder Zeile und drei weitere Werte an, wenn die Zeile ausgewählt ist.  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     Der folgende Code zeigt die Abfrage, die verwendet wird, um die Daten auszuwählen, die in angezeigt wird der <xref:System.Windows.Controls.DataGrid>. In diesem Beispiel wählt die Abfrage Daten aus einer Entität, die Kundeninformationen enthält.  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>Details für die Zeile angezeigt wird, mithilfe einer Ressource  
  
1. Erstellen Sie eine <xref:System.Windows.Controls.DataGrid> , die Daten aus einer Datenquelle anzeigt.  
  
2. Hinzufügen einer <xref:System.Windows.FrameworkElement.Resources%2A> Element das Stammelement, wie z. B. eine <xref:System.Windows.Window> Steuerelement oder ein <xref:System.Windows.Controls.Page> steuern, oder fügen eine <xref:System.Windows.Application.Resources%2A> Element der <xref:System.Windows.Application> Klasse in der Datei "App.xaml" (oder "Application.xaml").  
  
3. Erstellen Sie in die Resources-Element, ein <xref:System.Windows.DataTemplate> , die die Darstellung der Zeilendetailabschnitt definiert.  
  
     Das folgende XAML zeigt die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definiert, der <xref:System.Windows.Application> Klasse.  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. Auf der <xref:System.Windows.DataTemplate>legen die [X: Key Directive](../../xaml-services/x-key-directive.md) auf einen Wert, der die Datenvorlage eindeutig identifiziert.  
  
5. In der <xref:System.Windows.Controls.DataGrid> -Element legen Sie die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Eigenschaft, um die Ressource, die in den vorherigen Schritten definiert. Weisen Sie die Ressource als statische Ressource.  
  
     Das folgende XAML zeigt die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> -Eigenschaft auf die Ressource aus dem vorherigen Beispiel.  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>Legen Sie Sichtbarkeit und horizontalen Bildlauf für Zeilendetails  
  
1. Legen Sie bei Bedarf die <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> Eigenschaft, um eine <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> Wert.  
  
     Der Wert ist standardmäßig auf festgelegt <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>. Sie können sie festlegen, um <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> um die Details für alle Zeilen anzuzeigen oder <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> So blenden Sie die Details für alle Zeilen aus.  
  
2. Legen Sie bei Bedarf die <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> Eigenschaft `true` erläutert, um zu verhindern, dass die Zeile einen horizontalen Bildlauf.
