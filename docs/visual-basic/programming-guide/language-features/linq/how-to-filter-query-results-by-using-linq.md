---
title: 'Gewusst wie: Filtern von Abfrageergebnissen unter Verwendung von LINQ (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80d4f05e9f90e8543c61af26080e66f9cf262f01
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a>Gewusst wie: Filtern von Abfrageergebnissen unter Verwendung von LINQ (Visual Basic)
Language-Integrated Query (LINQ) erleichtert die Datenbankinformationen zugreifen und Ausführen von Abfragen.  
  
 Im folgende Beispiel wird gezeigt, wie eine neue Anwendung erstellen, die eine SQL Server-Datenbank abfragt und filtert die Ergebnisse nach einem bestimmten Wert mithilfe der `Where` Klausel. Weitere Informationen finden Sie unter [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
 In den Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind. Wenn Sie die Beispieldatenbank Northwind nicht auf Ihrem Computer verfügen, können Sie laden Sie es der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Website. Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>So erstellen eine Verbindung mit einer Datenbank  
  
1.  Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank Explorer** auf die **Ansicht** Menü.  
  
2.  Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.  
  
3.  Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Ein Projekt hinzufügen, die eine LINQ to SQL-Datei enthält.  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**. Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.  
  
2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. Wählen Sie die **LINQ to SQL-Klassen** Elementvorlage.  
  
3.  Nennen Sie die Datei `northwind.dbml`. Klicken Sie auf **Hinzufügen**. Der Object Relational Designer (O/R-Designer) wird für die Datei northwind.dbml geöffnet.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Hinzufügen von Tabellen zu Abfragen in den O/R-Designer  
  
1.  In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung mit der Datenbank Northwind. Erweitern Sie die **Tabellen** Ordner.  
  
     Wenn Sie im O/R-Designer geschlossen haben, können Sie es durch Doppelklicken auf die Datei northwind.dbml, die Sie zuvor hinzugefügt haben erneut öffnen.  
  
2.  Klicken Sie auf der Customers-Tabelle, und ziehen Sie es in den linken Bereich des Designers. Klicken Sie auf die Orders-Tabelle, und ziehen Sie es in den linken Bereich des Designers.  
  
     Der Designer erstellt neue `Customer` und `Order` Objekte für das Projekt. Beachten Sie, dass der Designer Beziehungen zwischen den Tabellen erkennt automatisch und untergeordneten Eigenschaften für verwandte Objekte erstellt. Z. B. IntelliSense wird angezeigt, die `Customer` Objekt verfügt über eine `Orders` -Eigenschaft für alle Aufträge im Zusammenhang mit diesen Kunden.  
  
3.  Speichern Sie die Änderungen zu und schließen Sie den Designer.  
  
4.  Speichern Sie das Projekt.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Hinzufügen von Code aus, um die Datenbank abzufragen und die Ergebnisse werden angezeigt.  
  
1.  Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> -Steuerelement auf die Standard-Windows Form für das Projekt, Form1.  
  
2.  Doppelklicken Sie auf Form1, um zum Hinzufügen von Code die `Load` -Ereignis des Formulars.  
  
3.  Wenn Sie Tabellen in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext> Objekt für das Projekt. Dieses Objekt enthält den Code, den Sie für den Zugriff auf diese Tabellen, zusätzlich zu den einzelnen Objekte und Sammlungen für jede Tabelle benötigen. Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit der Bezeichnung wird anhand des Namens der DBML-Datei. Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt heißt `northwindDataContext`.  
  
     Erstellen eine Instanz von der <xref:System.Data.Linq.DataContext> in Ihren Code und die Abfrage die Tabellen, die vom O/R-Designer angegeben.  
  
     Fügen Sie folgenden Code, der `Load` Ereignis, um die Tabellen Abfragen, die als Eigenschaften des Datenkontexts verfügbar gemacht werden. Die Abfrage filtert die Ergebnisse und gibt nur die Kunden, die in befinden `London`.  
  
     [!code-vb[VbLINQToSQLHowTos#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]  
  
4.  Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.  
  
5.  Im folgenden werden einige andere Filter, die Sie ausprobieren können.  
  
     [!code-vb[VbLINQToSQLHowTos#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
