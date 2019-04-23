---
title: 'Vorgehensweise: Ändern von Daten in einer Datenbank mit LINQ (Visual Basic)'
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
ms.openlocfilehash: 8770a8761af4b55394d9280b21d2a6a5b71b6ed5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304895"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>Vorgehensweise: Ändern von Daten in einer Datenbank mit LINQ (Visual Basic)
Language Integrated Query (LINQ) Abfragen erleichtern Ihnen den Zugriff auf Informationen und Ändern von Werten in der Datenbank.  
  
 Das folgende Beispiel zeigt wie Sie eine neue Anwendung erstellen, die abruft und Informationen zu Softwareupdates in einer SQL Server-Datenbank.  
  
 In die Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind. Wenn Sie diese Datenbank nicht auf dem Entwicklungscomputer gespeichert haben, können Sie es aus dem Microsoft Download Center herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
### <a name="to-create-a-connection-to-a-database"></a>Um eine Verbindung mit einer Datenbank zu erstellen.  
  
1. Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf die **Ansicht** Menü, und wählen Sie dann **fürServer-Explorer** / **Datenbank-Explorer**.  
  
2. Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer**, und klicken Sie auf **Verbindung hinzufügen**.  
  
3. Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>Ein Projekt mit einer LINQ to SQL-Datei hinzufügen  
  
1. Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**. Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.  
  
2. Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. Wählen Sie die **LINQ to SQL-Klassen** Elementvorlage.  
  
3. Nennen Sie die Datei `northwind.dbml`. Klicken Sie auf **Hinzufügen**. Der Object Relational Designer (O/R Designer) wird geöffnet, für die `northwind.dbml` Datei.  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>Zum Hinzufügen von Tabellen zum Abfragen und ändern in den designer  
  
1. In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung zur Northwind-Datenbank. Erweitern Sie die **Tabellen** Ordner.  
  
     Wenn Sie den O/R-Designer geschlossen haben, können Sie es öffnen, durch Doppelklicken auf die `northwind.dbml` -Datei, die Sie zuvor hinzugefügt haben.  
  
2. Klicken Sie auf der Customers-Tabelle aus, und ziehen Sie es in den linken Bereich des Designers.  
  
     Der Designer erstellt ein neues Customer-Objekt, für das Projekt.  
  
3. Speichern Sie die Änderungen zu und schließen Sie den Designer.  
  
4. Speichern Sie das Projekt.  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>Zum Hinzufügen von Code zum Ändern der Datenbank und die Ergebnisse anzeigen  
  
1. Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> Steuerelement auf das Standard-Windows-Formular für das Projekt, Form1.  
  
2. Wenn Sie Tabellen in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt eine <xref:System.Data.Linq.DataContext> Objekt, das Ihr Projekt. Dieses Objekt enthält Code, mit denen Sie Zugriff auf die Customers-Tabelle. Sie enthält auch Code, ein lokales Kundenobjekt und eine Sammlung "Kunden" für die Tabelle definiert. Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit dem Namen wird anhand des Namens der DBML-Datei. Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt mit dem Namen `northwindDataContext`.  
  
     Sie können eine Instanz von erstellen die <xref:System.Data.Linq.DataContext> Objekt in Ihrem Code und die Abfrage aus, und ändern Sie die Sammlung "Kunden" durch den O/R-Designer angegeben. Änderungen, die Sie für die Sammlung "Kunden" machen, werden nicht in der Datenbank wiedergegeben, bis Sie sie durch Aufrufen von übermitteln der <xref:System.Data.Linq.DataContext.SubmitChanges%2A> Methode der <xref:System.Data.Linq.DataContext> Objekt.  
  
     Doppelklicken Sie auf das Windows Form, Form1, um zum Hinzufügen von Code die <xref:System.Windows.Forms.Form.Load> Ereignis, um die Abfrage, die Customers-Tabelle als eine Eigenschaft verfügbar gemacht wird Ihre <xref:System.Data.Linq.DataContext>. Fügen Sie den folgenden Code hinzu:  
  
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
  
3. Von der **Toolbox**, ziehen Sie drei <xref:System.Windows.Forms.Button> Steuerelemente auf das Formular. Wählen Sie die erste `Button` Steuerelement. In der **Eigenschaften** legen die `Name` von der `Button` die Steuerung an `AddButton` und `Text` zu `Add`. Wählen Sie die zweite Schaltfläche, und legen die `Name` Eigenschaft `UpdateButton` und `Text` Eigenschaft `Update`. Wählen Sie die dritte Schaltfläche, und legen die `Name` Eigenschaft `DeleteButton` und `Text` Eigenschaft `Delete`.  
  
4. Doppelklicken Sie auf die **hinzufügen** Schaltfläche Hinzufügen von Code, dessen `Click` Ereignis. Fügen Sie den folgenden Code hinzu:  
  
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
  
5. Doppelklicken Sie auf die **Update** Schaltfläche Hinzufügen von Code, dessen `Click` Ereignis. Fügen Sie den folgenden Code hinzu:  
  
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
  
6. Doppelklicken Sie auf die **löschen** Schaltfläche Hinzufügen von Code, dessen `Click` Ereignis. Fügen Sie den folgenden Code hinzu:  
  
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
  
7. Drücken Sie F5, um das Projekt auszuführen. Klicken Sie auf **hinzufügen** um einen neuen Datensatz hinzuzufügen. Klicken Sie auf **Update** so ändern Sie den neuen Datensatz. Klicken Sie auf **löschen** auf den neuen Datensatz zu löschen.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
