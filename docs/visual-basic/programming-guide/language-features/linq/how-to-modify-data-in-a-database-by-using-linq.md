---
title: 'Vorgehensweise: Ändern von Daten in einer Datenbank mithilfe von LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
ms.openlocfilehash: 9a10efef5ae92dd21888594ae80a3fc07869a8c0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344946"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>Gewusst wie: Ändern von Daten in einer Datenbank mit LINQ (Visual Basic)

LINQ-Abfragen (Language-Integrated Query) erleichtern den Zugriff auf Datenbankinformationen und das Ändern von Werten in der Datenbank.

Im folgenden Beispiel wird gezeigt, wie Sie eine neue Anwendung erstellen, die Informationen in einer SQL Server-Datenbank abruft und aktualisiert.

In den Beispielen in diesem Thema wird die Beispieldatenbank Northwind verwendet. Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese aus dem Microsoft Download Center herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispiel Datenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).

### <a name="to-create-a-connection-to-a-database"></a>So erstellen Sie eine Verbindung mit einer Datenbank

1. Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** , indem Sie auf das Menü **Ansicht** und dann auf **Server-Explorer**/**Datenbank-Explorer**klicken.

2. Klicken Sie in **Server-Explorer**/**Datenbank-Explorer**mit der rechten Maustaste auf **Datenverbindungen** , und klicken Sie auf **Verbindung hinzufügen**.

3. Geben Sie eine gültige Verbindung mit der Northwind-Beispieldatenbank an.

### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>So fügen Sie ein Projekt mit einer LINQ to SQL Datei hinzu

1. Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**. Wählen Sie Visual Basic **Windows Forms Anwendung** als Projekttyp aus.

2. Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. Wählen Sie die Element Vorlage **LINQ to SQL Klassen** aus.

3. Nennen Sie die Datei `northwind.dbml`. Klicken Sie auf **Hinzufügen**. Der objektrelationaler Designer (O/R-Designer) wird für die `northwind.dbml`-Datei geöffnet.

### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>So fügen Sie Tabellen zum Abfragen und Ändern des Designers hinzu

1. Erweitern Sie in **Server-Explorer**/**Datenbank-Explorer**die Verbindung mit der Northwind-Datenbank. Erweitern Sie den Ordner **Tabellen** .

     Wenn Sie den O/R-Designer geschlossen haben, können Sie ihn erneut öffnen, indem Sie auf die `northwind.dbml` Datei doppelklicken, die Sie zuvor hinzugefügt haben.

2. Klicken Sie auf die Tabelle Customers, und ziehen Sie Sie in den linken Bereich des Designers.

     Der Designer erstellt ein neues Customer-Objekt für das Projekt.

3. Speichern Sie die Änderungen, und schließen Sie den Designer.

4. Speichern Sie das Projekt.

### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>So fügen Sie Code hinzu, um die Datenbank zu ändern und die Ergebnisse anzuzeigen

1. Ziehen Sie aus der **Toolbox**ein <xref:System.Windows.Forms.DataGridView>-Steuerelement auf das standardmäßige Windows Form für Ihr Projekt, Form1.

2. Wenn Sie dem O/R-Designer Tabellen hinzugefügt haben, hat der Designer dem Projekt ein <xref:System.Data.Linq.DataContext> Objekt hinzugefügt. Dieses Objekt enthält Code, den Sie für den Zugriff auf die Customers-Tabelle verwenden können. Sie enthält auch Code, der ein lokales Kunden Objekt und eine Kunden Auflistung für die Tabelle definiert. Das <xref:System.Data.Linq.DataContext>-Objekt für das Projekt wird basierend auf dem Namen der DBML-Datei benannt. Für dieses Projekt wird das <xref:System.Data.Linq.DataContext> Objekt `northwindDataContext`benannt.

     Sie können eine Instanz des <xref:System.Data.Linq.DataContext> Objekts im Code erstellen und die vom O/R-Designer angegebene Kunden Auflistung Abfragen und ändern. Änderungen, die Sie an der Customers-Sammlung vornehmen, werden erst dann in der Datenbank wiedergegeben, wenn Sie Sie durch Aufrufen der <xref:System.Data.Linq.DataContext.SubmitChanges%2A>-Methode des <xref:System.Data.Linq.DataContext>-Objekts übermitteln.

     Doppelklicken Sie auf das Windows Form Form1, um dem <xref:System.Windows.Forms.Form.Load>-Ereignis Code zum Abfragen der Customers-Tabelle hinzuzufügen, die als Eigenschaft ihrer <xref:System.Data.Linq.DataContext>verfügbar gemacht wird. Fügen Sie den folgenden Code hinzu:

    ```vb
    Private db As northwindDataContext

    Private Sub Form1_Load(ByVal sender As System.Object,
                           ByVal e As System.EventArgs
                          ) Handles MyBase.Load
      db = New northwindDataContext()

      RefreshData()
    End Sub

    Private Sub RefreshData()
      Dim customers = From cust In db.Customers
                      Where cust.City(0) = "W"
                      Select cust

      DataGridView1.DataSource = customers
    End Sub
    ```

3. Ziehen Sie aus der **Toolbox**drei <xref:System.Windows.Forms.Button>-Steuerelemente auf das Formular. Wählen Sie das erste `Button` Steuerelement aus. Legen Sie im Fenster **Eigenschaften** die `Name` des `Button` Steuer Elements auf `AddButton` und die `Text` auf `Add`fest. Wählen Sie die zweite Schaltfläche aus, und legen Sie die `Name`-Eigenschaft auf `UpdateButton` und die Eigenschaft `Text` auf `Update`fest. Wählen Sie die dritte Schaltfläche aus, und legen Sie die `Name`-Eigenschaft auf `DeleteButton` und die Eigenschaft `Text` auf `Delete`fest.

4. Doppelklicken Sie auf die Schaltfläche **Hinzufügen** , um dem `Click` Ereignis Code hinzuzufügen. Fügen Sie den folgenden Code hinzu:

    ```vb
    Private Sub AddButton_Click(ByVal sender As System.Object,
                                ByVal e As System.EventArgs
                               ) Handles AddButton.Click
      Dim cust As New Customer With {
        .City = "Wellington",
        .CompanyName = "Blue Yonder Airlines",
        .ContactName = "Jill Frank",
        .Country = "New Zealand",
        .CustomerID = "JILLF"}

      db.Customers.InsertOnSubmit(cust)

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

5. Doppelklicken Sie auf die Schaltfläche **Aktualisieren** , um dem `Click` Ereignis Code hinzuzufügen. Fügen Sie den folgenden Code hinzu:

    ```vb
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles UpdateButton.Click
      Dim updateCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      updateCust.ContactName = "Jill Shrader"
      updateCust.Country = "Wales"
      updateCust.CompanyName = "Red Yonder Airlines"
      updateCust.City = "Cardiff"

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

6. Doppelklicken Sie auf die Schaltfläche **Löschen** , um dem `Click` Ereignis Code hinzuzufügen. Fügen Sie den folgenden Code hinzu:

    ```vb
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles DeleteButton.Click
      Dim deleteCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      db.Customers.DeleteOnSubmit(deleteCust)

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

7. Drücken Sie F5, um das Projekt auszuführen. Klicken Sie auf **Add** , um einen neuen Datensatz hinzuzufügen. Klicken Sie auf **Aktualisieren** , um den neuen Datensatz zu ändern. Klicken Sie auf **Löschen** , um den neuen Datensatz zu löschen.

## <a name="see-also"></a>Siehe auch

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
