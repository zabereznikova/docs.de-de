---
title: 'Vorgehensweise: Hinzufügen von Zeilendetails zu einem DataGrid-Steuerelement'
description: Erfahren Sie, wie Sie die Datendarstellung anpassen, wenn Sie das DataGrid-Steuerelement Windows Presentation Foundation durch Hinzufügen eines Abschnitts Zeilen Details hinzufügen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: 8fd6b07f454681a0eed70d7a6208cfcc426dc920
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164945"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>Vorgehensweise: Hinzufügen von Zeilendetails zu einem DataGrid-Steuerelement
Wenn Sie das-Steuerelement verwenden <xref:System.Windows.Controls.DataGrid> , können Sie die Datendarstellung anpassen, indem Sie einen Abschnitt mit Zeilen Details hinzufügen. Durch das Hinzufügen eines Abschnitts "Zeilen Details" können Sie einige Daten in einer Vorlage gruppieren, die optional sichtbar oder reduziert ist. Beispielsweise können Sie Zeilen Details zu einem hinzufügen, <xref:System.Windows.Controls.DataGrid> das nur eine Zusammenfassung der Daten für jede Zeile in der darstellt <xref:System.Windows.Controls.DataGrid> , es werden jedoch weitere Datenfelder angezeigt, wenn der Benutzer eine Zeile auswählt. Die Vorlage für den Zeilen Detail Abschnitt wird in der- <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Eigenschaft definiert. Die folgende Abbildung zeigt ein Beispiel für einen Zeilen Detail Abschnitt.  
  
 ![DataGrid mit Zeilendetails](./media/ndp-rowdetails.png "NDP_RowDetails")  
  
 Die Vorlage für Zeilen Details wird entweder als Inline-XAML oder als Ressource definiert. Beide Ansätze werden in den folgenden Prozeduren angezeigt. Eine Daten Vorlage, die als Ressource hinzugefügt wird, kann im gesamten Projekt verwendet werden, ohne dass die Vorlage neu erstellt werden muss. Eine Daten Vorlage, die als Inline-XAML hinzugefügt wird, ist nur über das Steuerelement zugänglich, wo Sie definiert ist.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>So zeigen Sie Zeilen Details mithilfe von Inline-XAML an  
  
1. Erstellen Sie einen <xref:System.Windows.Controls.DataGrid> , der Daten aus einer Datenquelle anzeigt.  
  
2. Fügen Sie im <xref:System.Windows.Controls.DataGrid>-Element ein <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>-Element hinzu.  
  
3. Erstellen Sie einen <xref:System.Windows.DataTemplate> , der die Darstellung des Abschnitts mit den Zeilen Details definiert.  
  
     Der folgende XAML-Code zeigt <xref:System.Windows.Controls.DataGrid> und wie Sie <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Inline definieren. <xref:System.Windows.Controls.DataGrid>In werden drei Werte in jeder Zeile und drei weitere Werte angezeigt, wenn die Zeile ausgewählt wird.  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     Der folgende Code zeigt die Abfrage, die verwendet wird, um die Daten auszuwählen, die in der angezeigt werden <xref:System.Windows.Controls.DataGrid> . In diesem Beispiel wählt die Abfrage Daten aus einer Entität aus, die Kundeninformationen enthält.  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>So zeigen Sie Zeilen Details mithilfe einer Ressource an  
  
1. Erstellen Sie einen <xref:System.Windows.Controls.DataGrid> , der Daten aus einer Datenquelle anzeigt.  
  
2. Fügen Sie ein- <xref:System.Windows.FrameworkElement.Resources%2A> Element zum root-Element hinzu, z. b. ein- <xref:System.Windows.Window> Steuerelement oder ein- <xref:System.Windows.Controls.Page> Steuerelement, oder fügen Sie <xref:System.Windows.Application.Resources%2A> der- <xref:System.Windows.Application> Klasse in der Datei app. XAML (oder Application. XAML) ein-Element hinzu.  
  
3. Erstellen Sie im Resources-Element einen <xref:System.Windows.DataTemplate> , der die Darstellung des Abschnitts mit den Zeilen Details definiert.  
  
     Der folgende XAML-Code zeigt das, das <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> in der-Klasse definiert ist <xref:System.Windows.Application> .  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <xref:System.Windows.DataTemplate>Legen Sie für die [x:Key-Direktive](../../../desktop-wpf/xaml-services/xkey-directive.md) einen Wert fest, der die Daten Vorlage eindeutig identifiziert.  
  
5. <xref:System.Windows.Controls.DataGrid>Legen Sie im-Element die- <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Eigenschaft auf die Ressource fest, die in den vorherigen Schritten definiert wurde. Weisen Sie die Ressource als statische Ressource zu.  
  
     Der folgende XAML-Code zeigt die- <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Eigenschaft, die auf die Ressource aus dem vorherigen Beispiel festgelegt ist.  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>So legen Sie Sichtbarkeit fest und verhindern den horizontalen Bildlauf für Zeilen Details  
  
1. Legen Sie bei Bedarf die- <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> Eigenschaft auf einen <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> Wert fest.  
  
     In der Standardeinstellung ist dieser Wert auf <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected> festgelegt. Sie können es auf festlegen, <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> um die Details für alle Zeilen anzuzeigen oder <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> um die Details für alle Zeilen auszublenden.  
  
2. Legen Sie bei Bedarf die- <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> Eigenschaft auf fest, `true` um zu verhindern, dass der Zeilen Detail Abschnitt horizontal durch Scrollen wird.
