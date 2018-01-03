---
title: 'Gewusst wie: Aufrufen einer gespeicherten Prozedur mithilfe von LINQ (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8bb7b970d42a44ad925883b7a935aae386b1f1d5
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>Gewusst wie: Aufrufen einer gespeicherten Prozedur mithilfe von LINQ (Visual Basic)
Language-Integrated Query (LINQ) erleichtert die Datenbankinformationen, einschließlich Datenbankobjekten wie z. B. gespeicherte Prozeduren zugreifen.  
  
 Das folgende Beispiel zeigt, wie eine Anwendung erstellen, die in einer SQL Server-Datenbank eine gespeicherte Prozedur aufruft. Das Beispiel zeigt, wie zwei verschiedene gespeicherte Prozeduren in der Datenbank aufgerufen wird. Jede Prozedur gibt die Ergebnisse einer Abfrage zurück. Eine Prozedur verwendet die Eingabeparameter, und die andere Prozedur akzeptiert Parameter.  
  
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
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>Gespeicherte Prozeduren in den O/R-Designer hinzugefügt.  
  
1.  In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung mit der Datenbank Northwind. Erweitern Sie die **gespeicherte Prozeduren** Ordner.  
  
     Wenn Sie im O/R-Designer geschlossen haben, können Sie es durch Doppelklicken auf die Datei northwind.dbml, die Sie zuvor hinzugefügt haben erneut öffnen.  
  
2.  Klicken Sie auf die **Umsatz nach Jahr** gespeicherte Prozedur, und ziehen Sie es in den rechten Bereich des Designers. Klicken Sie auf die **zehn teuersten Artikel** gespeicherte Prozedur ziehen Sie es in den rechten Bereich des Designers.  
  
3.  Speichern Sie die Änderungen zu und schließen Sie den Designer.  
  
4.  Speichern Sie das Projekt.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>Hinzufügen von Code zum Anzeigen der Ergebnisse der gespeicherten Prozeduren  
  
1.  Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> -Steuerelement auf die Standard-Windows Form für das Projekt, Form1.  
  
2.  Doppelklicken Sie auf Form1, um zum Hinzufügen von Code die `Load` Ereignis.  
  
3.  Wenn Sie gespeicherte Prozeduren in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt ein <xref:System.Data.Linq.DataContext> Objekt für das Projekt. Dieses Objekt enthält den Code, den Sie benötigen diese Prozeduren zugreifen. Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit der Bezeichnung wird anhand des Namens der DBML-Datei. Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt heißt `northwindDataContext`.  
  
     Erstellen eine Instanz von der <xref:System.Data.Linq.DataContext> in Ihrem Code, und rufen die gespeicherte Prozedur-Methoden, die vom O/R-Designer angegeben. Zum Binden an die <xref:System.Windows.Forms.DataGridView> Objekt möglicherweise so erzwingen die auszuführende Abfrage sofort durch Aufrufen der <xref:System.Linq.Enumerable.ToList%2A> -Methode für die Ergebnisse der gespeicherten Prozedur.  
  
     Fügen Sie folgenden Code, der `Load` Ereignis aufrufen, entweder die gespeicherten Prozeduren, die als Methoden für Ihren Datenkontext verfügbar gemacht.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Abfragen](../../../../visual-basic/language-reference/queries/queries.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Ausführen von Updates, einfügungen und löschen (O/R-Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
