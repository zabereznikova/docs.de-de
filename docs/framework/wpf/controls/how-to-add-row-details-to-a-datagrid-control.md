---
title: "Gewusst wie: Hinzuf&#252;gen von Zeilendetails zu einem DataGrid-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DataGrid [WPF], Zeilendetails"
  - "DataTemplate [WPF], DataGrid"
  - "Zeilendetails [WPF], DataGrid"
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Hinzuf&#252;gen von Zeilendetails zu einem DataGrid-Steuerelement
Wenn Sie das <xref:System.Windows.Controls.DataGrid>\-Steuerelement verwenden, können Sie die Datendarstellung anpassen, indem Sie einen Zeilendetailabschnitt hinzufügen.  Durch das Hinzufügen eines Zeilendetailabschnitts können Sie einige Daten in einer Vorlage zu gruppieren, die optional sichtbar oder ausgeblendet ist.  Sie können z. B. einem <xref:System.Windows.Controls.DataGrid> Zeilendetails hinzufügen, der nur eine Zusammenfassung der Daten für jede Zeile im <xref:System.Windows.Controls.DataGrid> darstellt, aber mehr Datenfelder darstellt, wenn der Benutzer eine Zeile auswählt.  Sie definieren die Vorlage für den Zeilendetailabschnitt in der <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>\-Eigenschaft.  Die folgende Darstellung zeigt ein Beispiel eines Zeilendetailabschnitts.  
  
 ![DataGrid mit Zeilendetails](../../../../docs/framework/wpf/controls/media/ndp-rowdetails.png "NDP\_RowDetails")  
  
 Sie definieren die Zeilendetailvorlage als Inline\-XAML oder als Ressource.  Beide Möglichkeiten werden in den folgenden Verfahren dargestellt.  Eine Datenvorlage, die als Ressource hinzugefügt wird, kann im gesamten Projekt verwendet werden, ohne die Vorlage neu zu erstellen.  Auf eine Datenvorlage, die als Inline\-XAML hinzugefügt wird, kann nur von dem Steuerelement zugegriffen werden, in dem sie definiert ist.  
  
### So zeigen Sie Zeilendetails mit Inline\-XAML an  
  
1.  Erstellen Sie ein <xref:System.Windows.Controls.DataGrid>, das Daten aus einer Datenquelle anzeigt.  
  
2.  Fügen Sie im <xref:System.Windows.Controls.DataGrid>\-Element ein <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>\-Element hinzu.  
  
3.  Erstellen Sie eine <xref:System.Windows.DataTemplate>, die die Darstellung des Zeilendetailabschnitts definiert.  
  
     Die folgende XAML zeigt das <xref:System.Windows.Controls.DataGrid> an und zeigt an, wie die  <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline definiert wird.  Das <xref:System.Windows.Controls.DataGrid> zeigt drei Werte in jeder Zeile und drei weitere Werte an, wenn die Zeile ausgewählt wird.  
  
     [!code-xml[DataGrid_RowDetails#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     Im folgenden Code wird die Abfrage dargestellt, die zum Auswählen der Daten verwendet wird, die im <xref:System.Windows.Controls.DataGrid> angezeigt werden.  In diesem Beispiel wählt die Abfrage Daten aus einer Entität aus, die Kundeninformationen enthält.  
  
     [!code-csharp[DataGrid_RowDetails#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### So zeigen Sie Zeilendetails mit einer Ressource an  
  
1.  Erstellen Sie ein <xref:System.Windows.Controls.DataGrid>, das Daten aus einer Datenquelle anzeigt.  
  
2.  Fügen Sie ein <xref:System.Windows.FrameworkElement.Resources%2A>\-Element zum Stammelement hinzu, wie z. B. ein <xref:System.Windows.Window>\-Steuerelement oder ein <xref:System.Windows.Controls.Page>\-Steuerelement, oder fügen Sie ein <xref:System.Windows.Application.Resources%2A>\-Element zur <xref:System.Windows.Application>\-Klasse in der Datei App.xaml \(oder Application.xaml\) hinzu.  
  
3.  Erstellen Sie im Ressourcenelement eine <xref:System.Windows.DataTemplate>, die die Darstellung des Zeilendetailabschnitts definiert.  
  
     Die folgende XAML zeigt die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>, die in der <xref:System.Windows.Application>\-Klasse definiert wurde.  
  
     [!code-xml[DataGrid_RowDetails#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4.  Legen Sie in der <xref:System.Windows.DataTemplate> das [x:Key\-Direktive](../../../../docs/framework/xaml-services/x-key-directive.md) auf einen Wert fest, der die Datenvorlage eindeutig identifiziert.  
  
5.  Legen Sie im <xref:System.Windows.Controls.DataGrid>\-Element die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>\-Eigenschaft auf die in den vorherigen Schritten definierte Ressource fest.  Weisen Sie die Ressource als statische Ressource zu.  
  
     Die folgende XAML zeigt die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>\-Eigenschaft, die auf die Ressource aus dem vorherigen Beispiel festgelegt ist.  
  
     [!code-xml[DataGrid_RowDetails#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### So legen Sie die Sichtbarkeit fest und verhindern den horizontalen Bildlauf für Zeilendetails  
  
1.  Legen Sie die <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A>\-Eigenschaft gegebenenfalls auf einen <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>\-Wert fest.  
  
     Standardmäßig ist der Wert auf <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> festgelegt.  Sie können ihn auf <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> festlegen, um die Details für alle Zeilen anzuzeigen, oder auf <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>, um die Details für alle Zeilen auszublenden.  
  
2.  Legen Sie die <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A>\-Eigenschaft gegebenenfalls auf `true` fest, um einen horizontalen Bildlauf im Zeilendetailabschnitt zu verhindern.