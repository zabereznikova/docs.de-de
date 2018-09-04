---
title: 'Gewusst wie: Aufrufen einer gespeicherten Prozedur mithilfe von LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: 50a4dff90dc1ce02869978f1da147e530cefc3e1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43560843"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>Gewusst wie: Aufrufen einer gespeicherten Prozedur mithilfe von LINQ (Visual Basic)
Language Integrated Query (LINQ) erleichtert Ihnen den Zugriff auf Datenbankinformationen, einschließlich Datenbankobjekten, z. B. gespeicherte Prozeduren.  
  
 Das folgende Beispiel zeigt, wie Sie eine Anwendung erstellen, die in einer SQL Server-Datenbank eine gespeicherte Prozedur aufruft. Das Beispiel zeigt, wie Sie zwei verschiedene gespeicherte Prozeduren in der Datenbank aufrufen. Jede Prozedur gibt die Ergebnisse einer Abfrage zurück. Eine Prozedur die Eingabeparameter akzeptiert, und die andere Prozedur nimmt keine Parameter.  
  
 In die Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind. Wenn Sie diese Datenbank nicht auf dem Entwicklungscomputer gespeichert haben, können Sie es aus dem Microsoft Download Center herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Um eine Verbindung mit einer Datenbank zu erstellen.  
  
1.  Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank Explorer** auf die **Ansicht** Menü.  
  
2.  Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.  
  
3.  Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Zum Hinzufügen eines Projekts, das eine LINQ to SQL-Datei enthält.  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**. Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.  
  
2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. Wählen Sie die **LINQ to SQL-Klassen** Elementvorlage.  
  
3.  Nennen Sie die Datei `northwind.dbml`. Klicken Sie auf **Hinzufügen**. Der Object Relational Designer (O/R Designer) wird für die Datei northwind.dbml geöffnet.  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>Hinzufügen von gespeicherten Prozeduren in den O/R-Designer  
  
1.  In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung zur Northwind-Datenbank. Erweitern Sie die **gespeicherte Prozeduren** Ordner.  
  
     Wenn Sie den O/R-Designer geschlossen haben, können Sie sie durch Doppelklicken auf die Datei northwind.dbml, die Sie zuvor hinzugefügt haben erneut öffnen.  
  
2.  Klicken Sie auf die **Umsatz nach Jahr** gespeicherte Prozedur aus, und ziehen Sie es in den rechten Bereich des Designers. Klicken Sie auf die **Ten Most Expensive Products** gespeicherte Prozedur, ziehen Sie es in den rechten Bereich des Designers.  
  
3.  Speichern Sie die Änderungen zu und schließen Sie den Designer.  
  
4.  Speichern Sie das Projekt.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>Hinzufügen von Code zum Anzeigen der Ergebnisse der gespeicherten Prozeduren  
  
1.  Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> Steuerelement auf das Standard-Windows-Formular für das Projekt, Form1.  
  
2.  Doppelklicken Sie auf Form1, um zum Hinzufügen von Code die `Load` Ereignis.  
  
3.  Wenn Sie gespeicherte Prozeduren in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt eine <xref:System.Data.Linq.DataContext> Objekt für das Projekt. Dieses Objekt enthält den Code, der für diese Prozeduren zugreifen. Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit dem Namen wird anhand des Namens der DBML-Datei. Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt mit dem Namen `northwindDataContext`.  
  
     Sie können eine Instanz von erstellen die <xref:System.Data.Linq.DataContext> in Ihrem Code und der Aufruf die gespeicherte Prozedur-Methoden, die vom O/R-Designer angegeben. Zum Binden an die <xref:System.Windows.Forms.DataGridView> Objekt ist, wird Sie möglicherweise erzwingen, dass die auszuführende Abfrage sofort durch Aufrufen der <xref:System.Linq.Enumerable.ToList%2A> -Methode für die Ergebnisse der gespeicherten Prozedur.  
  
     Fügen Sie den folgenden Code der `Load` Ereignis, rufen Sie entweder mit den gespeicherten Prozeduren, die als Methoden für den Data-Kontext verfügbar gemacht werden.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  Drücken Sie F5, um das Projekt ausführen und die Ergebnisse anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Abfragen](../../../../visual-basic/language-reference/queries/index.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)](https://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
