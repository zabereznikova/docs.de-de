---
title: 'Vorgehensweise: Binden an eine ADO.NET-Datenquelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: 08933e67c2cc4b7ccfb6ae0c9dfde34f40e4e5f5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62021041"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a>Vorgehensweise: Binden an eine ADO.NET-Datenquelle

Dieses Beispiel zeigt, wie Sie binden ein [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> die Steuerung an eine [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`.

## <a name="example"></a>Beispiel

In diesem Beispiel wird ein `OleDbConnection`-Objekt zum Herstellen der Verbindung mit der Datenquelle verwendet, die als `Access MDB`-Datei in der Verbindungszeichenfolge angegeben ist. Nach dem Herstellen der Verbindung wird ein `OleDbDataAdapter`-Objekt erstellt. Das `OleDbDataAdapter`-Objekt führt eine SQL-Anweisung des Typs [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] aus, um das Recordset aus der Datenbank abzurufen. Die Ergebnisse des [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)]-Befehls werden in einer `DataTable` für das `DataSet` gespeichert, indem die `Fill`-Methode von `OleDbDataAdapter` aufgerufen wird. Die `DataTable` in diesem Beispiel heißt `BookTable`. Anschließend wird im Beispiel die <xref:System.Windows.FrameworkElement.DataContext%2A> Eigenschaft der <xref:System.Windows.Controls.ListBox> auf die `DataSet` Objekt.

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

Können wir binden, klicken Sie dann die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft der <xref:System.Windows.Controls.ListBox> zu `BookTable` von der `DataSet`:

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

`BookItemTemplate` ist die <xref:System.Windows.DataTemplate> , die definiert, wie die Daten angezeigt:

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

`IntColorConverter` konvertiert `int` in eine Farbe. Mit der Verwendung dieses Konverters der <xref:System.Windows.Controls.TextBlock.Background%2A> Farbe des dritten <xref:System.Windows.Controls.TextBlock> grün wenn der Wert des `NumPages` andernfalls wird von höchstens 350 und Rot. Die Implementierung des Konverters wird hier nicht gezeigt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.BindingListCollectionView>
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
