---
title: 'Gewusst wie: Binden an eine ADO.NET-Datenquelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: 0b3d7147f45bee5e8abd95bdc51c5f5f695cf830
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458407"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a>Gewusst wie: Binden an eine ADO.NET-Datenquelle

In diesem Beispiel wird gezeigt, wie ein [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox>-Steuerelement an eine ADO.net-`DataSet`gebunden wird.

## <a name="example"></a>Beispiel

In diesem Beispiel wird ein `OleDbConnection`-Objekt zum Herstellen der Verbindung mit der Datenquelle verwendet, die als `Access MDB`-Datei in der Verbindungszeichenfolge angegeben ist. Nach dem Herstellen der Verbindung wird ein `OleDbDataAdapter`-Objekt erstellt. Das `OleDbDataAdapter`-Objekt führt eine SELECT strukturierte Abfragesprache (SQL)-Anweisung aus, um das Recordset aus der Datenbank abzurufen. Die Ergebnisse des SQL-Befehls werden in einer `DataTable` der `DataSet` gespeichert, indem die `Fill`-Methode der `OleDbDataAdapter`aufgerufen wird. Die `DataTable` in diesem Beispiel heißt `BookTable`. Im Beispiel wird dann die <xref:System.Windows.FrameworkElement.DataContext%2A>-Eigenschaft des <xref:System.Windows.Controls.ListBox> auf das `DataSet`-Objekt festgelegt.

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

Anschließend können Sie die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>-Eigenschaft des <xref:System.Windows.Controls.ListBox> an `BookTable` der `DataSet`binden:

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

`BookItemTemplate` ist der <xref:System.Windows.DataTemplate>, der definiert, wie die Daten angezeigt werden:

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

`IntColorConverter` konvertiert `int` in eine Farbe. Bei Verwendung dieses Konverters wird die <xref:System.Windows.Controls.TextBlock.Background%2A> Farbe der dritten <xref:System.Windows.Controls.TextBlock> grün angezeigt, wenn der Wert von `NumPages` kleiner als 350 und andernfalls rot ist. Die Implementierung des Konverters wird hier nicht gezeigt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.BindingListCollectionView>
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
