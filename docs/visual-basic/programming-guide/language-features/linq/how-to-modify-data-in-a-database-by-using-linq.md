---
title: "Gewusst wie: Ändern von Daten in einer Datenbank mit LINQ (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
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
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 44ca3e44d8411a6329d176eb778677bfab2b365c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>Gewusst wie: Ändern von Daten in einer Datenbank mit LINQ (Visual Basic)
Language-Integrated Query (LINQ) Abfragen erleichtern den Zugriff auf Datenbankinformationen und Ändern von Werten in der Datenbank.  
  
 Das folgende Beispiel zeigt eine neue Anwendung erstellen, die abruft und Informationen zu Softwareupdates in einer SQL Server-Datenbank.  
  
 In den Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind. Wenn Sie die Beispieldatenbank Northwind auf dem Entwicklungscomputer nicht haben, können Sie herunterladen aus der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Website. Eine Anleitung hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](https://msdn.microsoft.com/library/bb399411).  
  
### <a name="to-create-a-connection-to-a-database"></a>Um eine Verbindung mit einer Datenbank zu erstellen.  
  
1.  Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf die **Ansicht** , und wählen Sie dann **Server-Explorer**/**Datenbank-Explorer**.  
  
2.  Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer**, und klicken Sie auf **Verbindung hinzufügen**.  
  
3.  Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>Ein Projekt mit einer LINQ to SQL-Datei hinzufügen  
  
1.  In Visual Studio auf die **Datei** auf **neu** , und klicken Sie dann auf **Projekt**. Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.  
  
2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. Wählen Sie die **LINQ to SQL Classes** Elementvorlage.  
  
3.  Nennen Sie die Datei `northwind.dbml`. Klicken Sie auf **Hinzufügen**. Der Object Relational Designer (O/R-Designer) geöffnet ist, für die `northwind.dbml` Datei.  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>Hinzufügen von Tabellen zum Abfragen und ändern in den designer  
  
1.  In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung zur Northwind-Datenbank. Erweitern Sie die **Tabellen** Ordner.  
  
     Wenn Sie den O/R-Designer geschlossen haben, können Sie es öffnen, durch Doppelklicken auf die `northwind.dbml` -Datei, die Sie zuvor hinzugefügt haben.  
  
2.  Klicken Sie auf die Tabelle Customers, und ziehen Sie es auf den linken Bereich des Designers.  
  
     Der Designer erstellt ein neues benutzerdefiniertes Objekt für das Projekt.  
  
3.  Speichern Sie die Änderungen und schließen Sie den Designer.  
  
4.  Speichern Sie das Projekt.  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>Fügen Sie Code zum Ändern der Datenbank und die Ergebnisse werden angezeigt.  
  
1.  Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView>-Steuerelement auf das Standard-Windows Form für Ihr Projekt, Form1.</xref:System.Windows.Forms.DataGridView>  
  
2.  Wenn Sie den O/R-Designer Tabellen hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext>Objekt zu Ihrem Projekt.</xref:System.Data.Linq.DataContext> Dieses Objekt enthält Code, mit denen Sie Zugriff auf die Customers-Tabelle. Außerdem enthält Sie Code, der ein lokales Customer-Objekt und eine Customer-Auflistung für die Tabelle definiert. Das <xref:System.Data.Linq.DataContext>-Objekt für das Projekt mit dem Namen basierend auf den Namen der DBML-Datei.</xref:System.Data.Linq.DataContext> Für dieses Projekt die <xref:System.Data.Linq.DataContext>-Objekt mit dem Namen `northwindDataContext`.</xref:System.Data.Linq.DataContext>  
  
     Erstellen Sie können eine Instanz von der <xref:System.Data.Linq.DataContext>Objekt in Ihrem Code und die Abfrage, und ändern Sie die vom O/R-Designer angegebene Customers-Auflistung.</xref:System.Data.Linq.DataContext> Auf die Auflistung der Kunden vornehmen, werden nicht in der Datenbank wiedergegeben, bis durch Aufrufen Senden der <xref:System.Data.Linq.DataContext.SubmitChanges%2A>Methode der <xref:System.Data.Linq.DataContext>Objekt.</xref:System.Data.Linq.DataContext> </xref:System.Data.Linq.DataContext.SubmitChanges%2A>  
  
     Doppelklicken Sie auf das Windows Form, Form1, um Code hinzufügen, auf das <xref:System.Windows.Forms.Form.Load>Ereignis, um die Customers-Tabelle abgefragt, die als eine Eigenschaft von Ihrem <xref:System.Data.Linq.DataContext>.</xref:System.Data.Linq.DataContext> bereitgestellt wird</xref:System.Windows.Forms.Form.Load> Fügen Sie den folgenden Code hinzu:  
  
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
  
3.  Aus der **Toolbox**, ziehen Sie drei <xref:System.Windows.Forms.Button>-Steuerelemente auf das Formular.</xref:System.Windows.Forms.Button> Wählen Sie das erste `Button` Steuerelement. In der **Eigenschaften** legen die `Name` von der `Button` die Steuerung an `AddButton` und `Text` auf `Add`. Wählen Sie die zweite Schaltfläche, und legen die `Name` -Eigenschaft `UpdateButton` und `Text` -Eigenschaft `Update`. Wählen Sie die dritte Schaltfläche aus, und legen Sie die `Name` -Eigenschaft `DeleteButton` und `Text` -Eigenschaft `Delete`.  
  
4.  Doppelklicken Sie auf die **hinzufügen** Schaltfläche zum Hinzufügen von Code auf seine `Click` Ereignis. Fügen Sie den folgenden Code hinzu:  
  
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
  
5.  Doppelklicken Sie auf die **Update** Schaltfläche zum Hinzufügen von Code auf seine `Click` Ereignis. Fügen Sie den folgenden Code hinzu:  
  
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
  
6.  Doppelklicken Sie auf die **löschen** Schaltfläche zum Hinzufügen von Code auf seine `Click` Ereignis. Fügen Sie den folgenden Code hinzu:  
  
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
  
7.  Drücken Sie F5, um das Projekt auszuführen. Klicken Sie auf **hinzufügen** um einen neuen Datensatz hinzufügen. Klicken Sie auf **Update** um den neuen Datensatz zu ändern. Klicken Sie auf **löschen** um den neuen Datensatz zu löschen.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)   
 [DataContext-Methoden (O/R-Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)   
 [Gewusst wie: Zuweisen von gespeicherten Prozeduren zum Aktualisieren, einfügen und löschen (O/R-Designer) ausführen.](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
