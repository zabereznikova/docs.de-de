---
title: "Gewusst wie: Ändern von Daten in einer Datenbank mit LINQ (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c491825d8fcacb9852584e7934682598441c2bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>Gewusst wie: Ändern von Daten in einer Datenbank mit LINQ (Visual Basic)
Language-Integrated Query (LINQ) Abfragen erleichtern die Datenbankinformationen zugreifen und ändern Sie die Werte in der Datenbank.  
  
 Das folgende Beispiel zeigt, wie Sie eine neue Anwendung erstellen, die abruft und Updates Informationen in einer SQL Server-Datenbank.  
  
 In den Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind. Wenn Sie die Beispieldatenbank Northwind nicht auf Ihrem Computer verfügen, können Sie laden Sie es der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Website. Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](https://msdn.microsoft.com/library/bb399411).  
  
### <a name="to-create-a-connection-to-a-database"></a>So erstellen eine Verbindung mit einer Datenbank  
  
1.  Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf die **Ansicht** Menü, und wählen Sie dann **Server-Explorer** / **Datenbank-Explorer**.  
  
2.  Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer**, und klicken Sie auf **Verbindung hinzufügen**.  
  
3.  Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>Ein Projekt mit einer LINQ to SQL-Datei hinzufügen  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**. Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.  
  
2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. Wählen Sie die **LINQ to SQL-Klassen** Elementvorlage.  
  
3.  Nennen Sie die Datei `northwind.dbml`. Klicken Sie auf **Hinzufügen**. Der Object Relational Designer (O/R-Designer) wird geöffnet, für die `northwind.dbml` Datei.  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>So fügen Sie Tabellen, um Abfragen und ändern in den Designer hinzu.  
  
1.  In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung mit der Datenbank Northwind. Erweitern Sie die **Tabellen** Ordner.  
  
     Wenn Sie im O/R-Designer geschlossen haben, können Sie es öffnen, durch Doppelklicken auf die `northwind.dbml` -Datei, die Sie zuvor hinzugefügt haben.  
  
2.  Klicken Sie auf der Customers-Tabelle, und ziehen Sie es in den linken Bereich des Designers.  
  
     Der Designer erstellt ein neues Customer-Objekt für das Projekt.  
  
3.  Speichern Sie die Änderungen zu und schließen Sie den Designer.  
  
4.  Speichern Sie das Projekt.  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>Fügen Sie Code zum Ändern der Datenbank und die Ergebnisse werden angezeigt.  
  
1.  Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> -Steuerelement auf die Standard-Windows Form für das Projekt, Form1.  
  
2.  Wenn Sie Tabellen in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext> -Objekt, das Projekt. Dieses Objekt enthält Code, die Sie zum Zugreifen auf die Customers-Tabelle verwenden können. Außerdem enthält Code, der ein lokales Customer-Objekt und eine Kunden-Auflistung für die Tabelle definiert. Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit der Bezeichnung wird anhand des Namens der DBML-Datei. Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt heißt `northwindDataContext`.  
  
     Erstellen eine Instanz von der <xref:System.Data.Linq.DataContext> Objekt in Ihrem Code und die Abfrage, und ändern Sie die Customers-Auflistung, die vom O/R-Designer angegeben. Auf die Auflistung der Kunden vorgenommene Änderungen werden nicht in der Datenbank wiedergegeben, bis Sie sie, durch Aufrufen Senden der <xref:System.Data.Linq.DataContext.SubmitChanges%2A> Methode der <xref:System.Data.Linq.DataContext> Objekt.  
  
     Doppelklicken Sie auf das Windows Form, Form1, um zum Hinzufügen von Code die <xref:System.Windows.Forms.Form.Load> Ereignis, um die Abfrage, die die Customers-Tabelle als eine Eigenschaft verfügbar gemacht wird Ihre <xref:System.Data.Linq.DataContext>. Fügen Sie den folgenden Code hinzu:  
  
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
  
3.  Aus der **Toolbox**, ziehen Sie drei <xref:System.Windows.Forms.Button> Steuerelemente auf das Formular. Wählen Sie die erste `Button` Steuerelement. In der **Eigenschaften** legen der `Name` von der `Button` die Steuerung an `AddButton` und die `Text` zu `Add`. Wählen Sie die zweite Schaltfläche, und legen die `Name` Eigenschaft `UpdateButton` und die `Text` Eigenschaft `Update`. Wählen Sie die dritte Schaltfläche, und legen die `Name` Eigenschaft `DeleteButton` und die `Text` Eigenschaft `Delete`.  
  
4.  Doppelklicken Sie auf die **hinzufügen** Schaltfläche zum Hinzufügen von Code, dessen `Click` Ereignis. Fügen Sie den folgenden Code hinzu:  
  
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
  
5.  Doppelklicken Sie auf die **Update** Schaltfläche zum Hinzufügen von Code, dessen `Click` Ereignis. Fügen Sie den folgenden Code hinzu:  
  
    ```vb  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6.  Doppelklicken Sie auf die **löschen** Schaltfläche zum Hinzufügen von Code, dessen `Click` Ereignis. Fügen Sie den folgenden Code hinzu:  
  
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
  
7.  Drücken Sie F5, um das Projekt auszuführen. Klicken Sie auf **hinzufügen** beim Hinzufügen eines neuen Datensatzes. Klicken Sie auf **Update** so ändern Sie den neuen Datensatz. Klicken Sie auf **löschen** beim Löschen des neuen Datensatzes.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)  
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)  
 [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Ausführen von Updates, einfügungen und löschen (O/R-Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
