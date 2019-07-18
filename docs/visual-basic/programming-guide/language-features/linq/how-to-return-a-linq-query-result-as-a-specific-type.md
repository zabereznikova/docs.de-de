---
title: 'Vorgehensweise: Zurückgeben eines LINQ-Abfrageergebnisses als bestimmter Typ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 5ccd71d93185f9478f6720419369df713d590c39
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053755"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a>Vorgehensweise: Zurückgeben eines LINQ-Abfrageergebnisses als bestimmter Typ (Visual Basic)
Language Integrated Query (LINQ) erleichtert den Zugriff auf Informationen und Ausführen von Abfragen. Standardmäßig zurück LINQ-Abfragen eine Liste von Objekten als anonymer Typ. Sie können auch angeben, dass eine Abfrage eine Liste eines bestimmten Typs mit Zurückgeben der `Select` Klausel.  
  
 Das folgende Beispiel zeigt, wie Sie eine neue Anwendung zu erstellen, die führt Abfragen in SQL Server-Datenbank und projiziert die Ergebnisse als einen bestimmten benannten Typ. Weitere Informationen finden Sie unter [anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) und [Select-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
 In die Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind. Wenn Sie diese Datenbank nicht auf dem Entwicklungscomputer gespeichert haben, können Sie es aus dem Microsoft Download Center herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Um eine Verbindung mit einer Datenbank zu erstellen.  
  
1. Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank Explorer** auf die **Ansicht** Menü.  
  
2. Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.  
  
3. Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Zum Hinzufügen eines Projekts, das eine LINQ to SQL-Datei enthält.  
  
1. Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**. Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.  
  
2. Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. Wählen Sie die **LINQ to SQL-Klassen** Elementvorlage.  
  
3. Nennen Sie die Datei `northwind.dbml`. Klicken Sie auf **Hinzufügen**. Der Object Relational Designer (O/R Designer) wird für die Datei northwind.dbml geöffnet.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Hinzufügen von Tabellen zu Abfragen in den O/R-Designer  
  
1. In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung zur Northwind-Datenbank. Erweitern Sie die **Tabellen** Ordner.  
  
     Wenn Sie den O/R-Designer geschlossen haben, können Sie sie durch Doppelklicken auf die Datei northwind.dbml, die Sie zuvor hinzugefügt haben erneut öffnen.  
  
2. Klicken Sie auf der Customers-Tabelle aus, und ziehen Sie es in den linken Bereich des Designers.  
  
     Der Designer erstellt eine neue `Customer` Objekt für das Projekt. Sie können die Abfrageergebnisse als projizieren der `Customer` Typ oder als einen Typ, den Sie erstellen. In diesem Beispiel erstellen einen neuen Typ in einem späteren Verfahren und Projekts Abfrageergebnisse als dieses Typs.  
  
3. Speichern Sie die Änderungen zu und schließen Sie den Designer.  
  
4. Speichern Sie das Projekt.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Hinzufügen von Code aus, um die Datenbank abzufragen und die Ergebnisse werden angezeigt  
  
1. Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> Steuerelement auf das Standard-Windows-Formular für das Projekt, Form1.  
  
2. Doppelklicken Sie auf Form1, um die Form1-Klasse ändern.  
  
3. Nach der `End Class` Anweisung der Form1-Klasse, fügen Sie folgenden Code zum Erstellen einer `CustomerInfo` Datentyp, um die Ergebnisse der Abfrage für dieses Beispiel zu speichern.  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. Wenn Sie Tabellen in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt eine <xref:System.Data.Linq.DataContext> Objekt, das Ihr Projekt. Dieses Objekt enthält den Code, den auf diese Tabellen zugreifen und den Zugriff auf einzelne Objekte und Auflistungen für jede Tabelle erforderlich sind. Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit dem Namen wird anhand des Namens der DBML-Datei. Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt mit dem Namen `northwindDataContext`.  
  
     Sie können eine Instanz von erstellen die <xref:System.Data.Linq.DataContext> in Ihrem Code und die Abfrage der Tabellen, die vom O/R-Designer angegeben.  
  
     In der `Load` Ereignis der Form1-Klasse, fügen Sie folgenden Code zum Abfragen von Tabellen, die als Eigenschaften des Datenkontexts verfügbar gemacht werden. Die `Select` -Klausel der Abfrage erstellt eine neue `CustomerInfo` Typ anstelle eines anonymen Typs für die einzelnen Elemente des Abfrageergebnisses.  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. Drücken Sie F5, um das Projekt ausführen und die Ergebnisse anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
