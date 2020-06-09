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
ms.openlocfilehash: 1398d8408a0b85d6603d638312e92ba35c5e77d3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591032"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a>Exemplarische Vorgehensweise: Anzeigen von Daten aus einer SQL Server Datenbank in einem DataGrid-Steuerelement

In dieser exemplarischen Vorgehensweise rufen Sie Daten aus einer SQL Server Datenbank ab und zeigen diese Daten in einem-Steuerelement an <xref:System.Windows.Controls.DataGrid> . Verwenden Sie die ADO.NET-Entity Framework, um die Entitäts Klassen zu erstellen, die die Daten darstellen, und verwenden Sie LINQ, um eine Abfrage zu schreiben, mit der die angegebenen Daten aus einer Entitäts Klasse abgerufen werden.

## <a name="prerequisites"></a>Voraussetzungen

Zum Abschließen dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:

- Visual Studio.

- Zugriff auf eine laufende Instanz von SQL Server oder SQL Server Express, der die AdventureWorks-Beispieldatenbank angefügt ist. Sie können die AdventureWorks-Datenbank von [GitHub](https://github.com/Microsoft/sql-server-samples/releases)herunterladen.

## <a name="create-entity-classes"></a>Erstellen von Entitäts Klassen

1. Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder c#, und nennen Sie es `DataGridSQLExample` .

2. Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, zeigen Sie auf **Hinzufügen**, und wählen Sie dann **Neues Element**aus.

     Das Dialogfeld Neues Element hinzufügen wird angezeigt.

3. Wählen Sie im Bereich installierte Vorlagen die Option **Daten** aus, und wählen Sie in der Liste der Vorlagen die Option **ADO.NET Entity Data Model**aus.

     ![ADO.NET Entity Data Model-Element Vorlage](../../wcf/feature-details/media/ado-net-entity-data-model-item-template.png)

4. Benennen Sie die Datei, `AdventureWorksModel.edmx` und klicken Sie auf **Hinzufügen**.

     Der Assistent für Entity Data Model wird angezeigt.

5. Wählen Sie im Bildschirm Modell Inhalt auswählen die Option **EF-Designer aus Datenbank aus** , und klicken Sie dann auf **weiter**.

6. Stellen Sie im Bildschirm Wählen Sie Ihre Datenverbindung aus die Verbindung mit der AdventureWorksLT2008-Datenbank her. Weitere Informationen finden Sie unter [Auswählen der Datenverbindung (Dialog Feld](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100))).

    Stellen Sie sicher, dass der Name lautet `AdventureWorksLT2008Entities` und dass das Kontrollkästchen **Entitäts Verbindungseinstellungen in app. config speichern** aktiviert ist, und klicken Sie dann auf **weiter**.

7. Erweitern Sie im Bildschirm Wählen Sie Ihre Datenbankobjekte aus den Knoten Tabellen, und wählen Sie die Tabelle **Product** und **ProductCategory** aus.

     Sie können Entitäts Klassen für alle Tabellen generieren. in diesem Beispiel rufen Sie jedoch nur Daten aus diesen beiden Tabellen ab.

     ![Product und ProductCategory aus Tabellen auswählen](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")

8. Klicken Sie auf **Fertig stellen**.

     Die Product-und ProductCategory-Entitäten werden in der Entity Designer angezeigt.

     ![Entitätsmodelle Product und ProductCategory](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")

## <a name="retrieve-and-present-the-data"></a>Abrufen und präsentieren der Daten

1. Öffnen Sie die Datei "MainWindow. XAML".

2. Legen Sie die- <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft für den auf <xref:System.Windows.Window> 450 fest.

3. Fügen Sie im XAML-Editor das folgende <xref:System.Windows.Controls.DataGrid> -Tag zwischen den `<Grid>` Tags und hinzu, `</Grid>` um einen mit dem Namen hinzuzufügen <xref:System.Windows.Controls.DataGrid> `dataGrid1` .

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     ![Fenster mit DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")

4. Wählen Sie <xref:System.Windows.Window> aus.

5. Erstellen Sie mit dem Eigenschaftenfenster-oder XAML-Editor einen Ereignishandler für das mit <xref:System.Windows.Window> `Window_Loaded` dem Namen für das- <xref:System.Windows.FrameworkElement.Loaded> Ereignis. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines einfachen Ereignis Handlers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

     Der folgende Code zeigt das XAML für "MainWindow. XAML".

    > [!NOTE]
    > Wenn Sie Visual Basic verwenden, ersetzen Sie in der ersten Zeile der Datei "MainWindow. XAML" `x:Class="DataGridSQLExample.MainWindow"` durch `x:Class="MainWindow"` .

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. Öffnen Sie die Code Behind-Datei (MainWindow. XAML. vb oder MainWindow.XAML.cs) für das <xref:System.Windows.Window> .

7. Fügen Sie den folgenden Code hinzu, um nur bestimmte Werte aus den verbundenen Tabellen abzurufen, und legen Sie die- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft des-Objekts <xref:System.Windows.Controls.DataGrid> auf die Ergebnisse der Abfrage fest.

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. Führen Sie das Beispiel aus.

     Es sollte ein <xref:System.Windows.Controls.DataGrid> angezeigt werden, in dem Daten angezeigt werden.

     ![DataGrid mit Daten aus SQL-Datenbank](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.DataGrid>
