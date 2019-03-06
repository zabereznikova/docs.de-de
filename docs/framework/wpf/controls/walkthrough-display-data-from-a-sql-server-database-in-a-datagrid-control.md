---
title: 'Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server-Datenbank in einem DataGrid-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: 022be17c946529583694afc0fe1c61b832aa03e4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351320"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a>Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server-Datenbank in einem DataGrid-Steuerelement

In dieser exemplarischen Vorgehensweise können Sie auch das Abrufen von Daten aus einer SQL Server-Datenbank und Daten angezeigt werden, in einem <xref:System.Windows.Controls.DataGrid> Steuerelement. Sie verwenden das ADO.NET Entity Framework, um Entitätsklassen zu erstellen, die die Daten darstellen, und LINQ verwenden, um eine Abfrage schreiben, die die angegebenen Daten aus einer Entitätsklasse abruft.

## <a name="prerequisites"></a>Vorraussetzungen

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

-   Visual Studio.

-   Zugriff auf eine ausgeführte Instanz von SQL Server oder SQL Server Express, die AdventureWorks-Beispieldatenbank angefügt ist. Sie können die AdventureWorks-Datenbank aus der [GitHub](https://github.com/Microsoft/sql-server-samples/releases).

## <a name="create-entity-classes"></a>Erstellen von Entitätsklassen

1.  Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder C# -Code, und nennen Sie es `DataGridSQLExample`.

2.  Im Projektmappen-Explorer mit der Maustaste des Projekts, zeigen Sie auf **hinzufügen**, und wählen Sie dann **neues Element**.

     Das Dialogfeld "Neues Element hinzufügen" angezeigt wird.

3.  Wählen Sie im Bereich Vorlagen installiert **Daten** , und wählen Sie in der Liste der Vorlagen, **ADO.NET Entity Data Model**.

     ![ADO.NET Entity Data Model-Elementvorlage](../../wcf/feature-details/./media/ado-net-entity-data-model-item-template.png)

4.  Nennen Sie die Datei `AdventureWorksModel.edmx` , und klicken Sie dann auf **hinzufügen**.

     Der Assistent für Entity Data Model wird angezeigt.

5.  Wählen Sie im Bildschirm Auswählen des Modellinhalts **EF Designer aus Datenbank** , und klicken Sie dann auf **Weiter**.

6.  Geben Sie die Verbindung mit der AdventureWorksLT2008-Datenbank, auf dem Bildschirm Wählen Sie Ihre Datenverbindung. Weitere Informationen finden Sie unter [wählen Sie Ihre Daten im Dialogfeld Verbindung](https://go.microsoft.com/fwlink/?LinkId=160190).

    Stellen Sie sicher, dass der Name `AdventureWorksLT2008Entities` und dass die **Entitätsverbindungseinstellungen in App.Config speichern als** Kontrollkästchen ausgewählt ist, und klicken Sie dann auf **Weiter**.

7.  Klicken Sie auf dem Bildschirm Wählen Sie Ihre Datenbankobjekte erweitern Sie den Knoten "Tabellen", und wählen die **Produkt** und **"ProductCategory"** Tabellen.

     Sie können Entitätsklassen für alle Tabellen generieren; Allerdings rufen Sie in diesem Beispiel nur Daten aus diesen zwei Tabellen.

     ![Wählen Sie Product und ProductCategory aus Tabellen](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")

8. Klicken Sie auf **Fertig stellen**.

     Die Entitäten Product und ProductCategory werden im Entity Designer angezeigt.

     ![Product und ProductCategory-Entitätsmodellen](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")

## <a name="retrieve-and-present-the-data"></a>Abrufen und die Darstellung der Daten

1.  Öffnen Sie die Datei "MainWindow.xaml".

2.  Legen Sie die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft für die <xref:System.Windows.Window> auf 450.

3.  In den XAML-Editor, fügen Sie die folgenden <xref:System.Windows.Controls.DataGrid> tag zwischen der `<Grid>` und `</Grid>` von Tags zum Hinzufügen einer <xref:System.Windows.Controls.DataGrid> mit dem Namen `dataGrid1`.

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     ![Fenster mit DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")

4.  Wählen Sie das <xref:System.Windows.Window>-Steuerelement aus.

5.  Erstellen Sie mit dem Fenster "Eigenschaften" oder der XAML-Editor, einen Ereignishandler für die <xref:System.Windows.Window> mit dem Namen `Window_Loaded` für die <xref:System.Windows.FrameworkElement.Loaded> Ereignis. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines einfachen Ereignishandlers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

     Das folgende Beispiel zeigt die XAML für "MainWindow.xaml".

    > [!NOTE]
    > Ersetzen Sie bei Verwendung von Visual Basic in der ersten Zeile der Datei "MainWindow.xaml" `x:Class="DataGridSQLExample.MainWindow"` mit `x:Class="MainWindow"`.

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6.  Öffnen Sie die CodeBehind-Datei ("MainWindow.Xaml.vb" bzw. "MainWindow.Xaml.cs") für die <xref:System.Windows.Window>.

7.  Fügen Sie den folgenden Code, um nur bestimmte Werte aus den verknüpften Tabellen abzurufen, und legen Sie die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft der <xref:System.Windows.Controls.DataGrid> auf die Ergebnisse der Abfrage.

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8.  Führen Sie das Beispiel aus.

     Daraufhin sollte eine <xref:System.Windows.Controls.DataGrid> , das Daten anzeigt.

     ![DataGrid mit Daten aus SQL-Datenbank](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.DataGrid>
- [Gewusst wie: Erste Schritte mit Entitätsframework in WPF-Anwendungen](https://go.microsoft.com/fwlink/?LinkId=159868)