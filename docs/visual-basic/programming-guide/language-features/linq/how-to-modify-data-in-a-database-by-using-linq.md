---
title: "How to: Modify Data in a Database by Using LINQ (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "inserting rows [LINQ to SQL]"
  - "deleting rows [LINQ to SQL]"
  - "updating rows [LINQ to SQL]"
  - "inserting data [Visual Basic]"
  - "deleting data"
  - "data [Visual Basic], updating"
  - "updating data [LINQ]"
  - "queries [LINQ in Visual Basic], data changes in database"
  - "queries [LINQ in Visual Basic], how-to topics"
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Modify Data in a Database by Using LINQ (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Mit LINQ \(Language\-Integrated Query\) ist es einfach, auf Datenbankinformationen zuzugreifen und Werte in einer Datenbank zu ändern.  
  
 Im folgenden Beispiel wird gezeigt, wie eine neue Anwendung erstellt wird, mit der in einer SQL Server\-Datenbank Informationen abgefragt und aktualisiert werden.  
  
 In den Beispielen dieses Themas wird die Beispieldatenbank Northwind verwendet.  Wenn die Beispieldatenbank Northwind auf dem Entwicklungscomputer nicht installiert ist, können Sie sie von der Website [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) herunterladen.  Anweisungen dazu finden Sie unter [Herunterladen von Beispieldatenbanken](../Topic/Downloading%20Sample%20Databases.md).  
  
### So erstellen Sie eine Verbindung zu einer Datenbank  
  
1.  Öffnen Sie in Visual Studio den **Server\-Explorer**\/**Datenbank\-Explorer**, indem Sie auf das Menü **Ansicht** klicken und dann **Server\-Explorer**\/**Datenbank\-Explorer** auswählen.  
  
2.  Klicken Sie im **Server\-Explorer**\/**Datenbank\-Explorer** mit der rechten Maustaste auf **Datenverbindungen**, und klicken Sie dann auf **Verbindung hinzufügen**.  
  
3.  Geben Sie eine gültige Verbindung zur Beispieldatenbank Northwind an.  
  
### So fügen ein Projekt mit einer LINQ to SQL\-Datei hinzu  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.  Wählen Sie Visual Basic\-**Windows Forms\-Anwendung** als Projekttyp aus.  
  
2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  Wählen Sie die Elementvorlage **LINQ to SQL\-Klassen** aus.  
  
3.  Nennen Sie die Datei `northwind.dbml`.  Klicken Sie auf **Hinzufügen**.  Der Object Relational Designer \(O\/R\-Designer\) wird für die Datei `northwind.dbml` geöffnet.  
  
### So fügen Sie abzufragende und zu ändernde Tabellen zum Designer hinzu  
  
1.  Erweitern Sie im **Server\-Explorer**\/**Datenbank\-Explorer** die Verbindung zur Datenbank Northwind.  Erweitern Sie den Ordner **Tabellen**.  
  
     Wenn Sie den O\/R\-Designer geschlossen haben, können Sie ihn durch Doppelklicken auf die zuvor hinzugefügte Datei `northwind.dbml` erneut öffnen.  
  
2.  Klicken Sie auf die Tabelle Customers, und ziehen Sie sie in den linken Bereich des Designers.  
  
     Der Designer erstellt ein neues Customer\-Objekt für das Projekt.  
  
3.  Speichern Sie die Änderungen, und schließen Sie den Designer.  
  
4.  Speichern Sie das Projekt.  
  
### So fügen Sie Code für Datenbankänderungen und zum Anzeigen der Ergebnisse hinzu  
  
1.  Ziehen Sie aus der **Toolbox** ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement auf das Standard\-Windows Form \(Form1\) des Projekts.  
  
2.  Wenn Sie dem O\/R\-Designer Tabellen hinzugefügt haben, wurde dem Projekt ein <xref:System.Data.Linq.DataContext>\-Objekt vom Designer hinzugefügt.  Dieses Objekt enthält Code, mit dem Sie auf die Customers\-Tabelle zugreifen können.  Es enthält außerdem Code, der ein lokales Customer\-Objekt und eine Customer\-Auflistung für die Tabelle definiert.  Das <xref:System.Data.Linq.DataContext>\-Objekt des Projekts wird auf Grundlage des Namens der DBML\-Datei benannt.  Für dieses Projekt lautet der Name des <xref:System.Data.Linq.DataContext>\-Objekts `northwindDataContext`.  
  
     Sie können im Code eine Instanz des <xref:System.Data.Linq.DataContext>\-Objekts erstellen und die vom O\/R\-Designer angegebene Customers\-Auflistung abrufen und ändern.  Änderungen in der Customers\-Auflistung wirken sich erst auf die Datenbank aus, wenn sie durch Aufruf der <xref:System.Data.Linq.DataContext.SubmitChanges%2A>\-Methode des <xref:System.Data.Linq.DataContext>\-Objekts übermittelt wurden.  
  
     Doppelklicken Sie auf das Windows Form, Form1, um Code zum <xref:System.Windows.Forms.Form.Load>\-Ereignis hinzuzufügen, mit dem die als eine Eigenschaft des <xref:System.Data.Linq.DataContext> verfügbar gemachte Customers\-Tabelle abgefragt wird.  Fügen Sie den folgenden Code hinzu:  
  
    ```vb#  
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
  
3.  Ziehen Sie aus der **Toolbox** drei <xref:System.Windows.Forms.Button>\-Steuerelemente auf das Formular.  Wählen Sie das erste `Button`\-Steuerelement aus.  Legen Sie im Fenster **Eigenschaften** die `Name`\-Eigenschaft des `Button`\-Steuerelements auf `AddButton` und die `Text`\-Eigenschaft auf `Hinzufügen` fest.  Wählen Sie die zweite Schaltfläche aus, und legen Sie die `Name`\-Eigenschaft auf `UpdateButton` und die `Text`\-Eigenschaft auf `Aktualisieren` fest.  Wählen Sie die dritte Schaltfläche aus, und legen Sie die `Name`\-Eigenschaft auf `DeleteButton` und die `Text`\-Eigenschaft auf `Löschen` fest.  
  
4.  Doppelklicken Sie auf die Schaltfläche **Hinzufügen**, um Code zum `Click`\-Ereignis hinzuzufügen.  Fügen Sie den folgenden Code hinzu:  
  
    ```vb#  
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
  
5.  Doppelklicken Sie auf die Schaltfläche **Aktualisieren**, um Code zum `Click`\-Ereignis hinzuzufügen.  Fügen Sie den folgenden Code hinzu:  
  
    ```vb#  
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
  
6.  Doppelklicken Sie auf die Schaltfläche **Löschen**, um Code zum `Click`\-Ereignis hinzuzufügen.  Fügen Sie den folgenden Code hinzu:  
  
    ```vb#  
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
  
7.  Drücken Sie F5, um das Projekt auszuführen.  Klicken Sie auf **Hinzufügen**, um einen neuen Datensatz hinzuzufügen.  Klicken Sie auf **Aktualisieren**, um den neuen Datensatz zu ändern.  Klicken Sie auf **Löschen**, um den neuen Datensatz zu löschen.  
  
## Siehe auch  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [DataContext\-Methoden \(O\/R\-Designer\)](/visual-studio/data-tools/datacontext-methods-o-r-designer)   
 [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zur Durchführung von Update\-, Einfüge\- und Löschvorgängen \(O\/R\-Designer\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [Exemplarische Vorgehensweise: Erstellen von LINQ to SQL\-Klassen \(O\/R\-Designer\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)