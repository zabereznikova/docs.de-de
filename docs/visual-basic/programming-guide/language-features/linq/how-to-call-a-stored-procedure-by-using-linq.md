---
title: 'Vorgehensweise: Aufrufen einer gespeicherten Prozedur mithilfe von LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: 7e5fecf0c4c0d3a561ec7d0c4ac03c9d9ce7f759
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075134"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>Gewusst wie: Aufrufen einer gespeicherten Prozedur mithilfe von LINQ (Visual Basic)

Language-Integrated Query (LINQ) vereinfacht den Zugriff auf Datenbankinformationen, einschließlich Datenbankobjekten wie z. b. gespeicherter Prozeduren.  
  
 Im folgenden Beispiel wird gezeigt, wie eine Anwendung erstellt wird, die eine gespeicherte Prozedur in einer SQL Server Datenbank aufruft. Das Beispiel zeigt, wie zwei verschiedene gespeicherte Prozeduren in der Datenbank aufgerufen werden. Jede Prozedur gibt die Ergebnisse einer Abfrage zurück. Eine Prozedur übernimmt Eingabeparameter, und die andere Prozedur übernimmt keine Parameter.  
  
 In den Beispielen in diesem Thema wird die Beispieldatenbank Northwind verwendet. Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie sie aus dem Microsoft Download Center herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispiel Datenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>So erstellen Sie eine Verbindung mit einer Datenbank  
  
1. Öffnen Sie in Visual Studio **Server-Explorer** / **Datenbank-Explorer** , indem **Server Explorer**Sie / im Menü **Ansicht** auf Server-Explorer**Datenbank-Explorer** klicken.  
  
2. Klicken Sie in **Server-Explorer**Datenbank-Explorer mit der rechten Maustaste auf **Datenverbindungen** / **Database Explorer** und dann auf **Verbindung hinzufügen**.  
  
3. Geben Sie eine gültige Verbindung mit der Northwind-Beispieldatenbank an.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>So fügen Sie ein Projekt hinzu, das eine LINQ to SQL Datei enthält  
  
1. Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**. Wählen Sie Visual Basic **Windows Forms Anwendung** als Projekttyp aus.  
  
2. Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. Wählen Sie die Element Vorlage **LINQ to SQL Klassen** aus.  
  
3. Benennen Sie die Datei mit `northwind.dbml`. Klicken Sie auf **Hinzufügen**. Der objektrelationaler Designer (O/R-Designer) wird für die Datei Northwind. dbml geöffnet.  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>So fügen Sie dem O/R-Designer gespeicherte Prozeduren hinzu  
  
1. Erweitern Sie in **Server-Explorer** / **Datenbank-Explorer**die Verbindung mit der Northwind-Datenbank. Erweitern Sie den Ordner **Gespeicherte Prozeduren** .  
  
     Wenn Sie den O/R-Designer geschlossen haben, können Sie ihn erneut öffnen, indem Sie auf die Datei Northwind. dbml, die Sie zuvor hinzugefügt haben, doppelklicken.  
  
2. Klicken Sie auf die gespeicherte Prozedur **Sales by Year** , und ziehen Sie Sie in den rechten Bereich des Designers. Wenn Sie auf die gespeicherte Prozedur mit den **zehn teuersten Produkten** klicken, ziehen Sie Sie in den rechten Bereich des Designers.  
  
3. Speichern Sie die Änderungen, und schließen Sie den Designer.  
  
4. Speichern Sie das Projekt.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>So fügen Sie Code hinzu, um die Ergebnisse der gespeicherten Prozeduren anzuzeigen  
  
1. Ziehen Sie aus der **Toolbox**ein- <xref:System.Windows.Forms.DataGridView> Steuerelement auf das Windows-Standardformular für das Projekt, Form1.  
  
2. Doppelklicken Sie auf Form1, um dem Ereignis Code hinzuzufügen `Load` .  
  
3. Wenn Sie dem O/R-Designer gespeicherte Prozeduren hinzugefügt haben, hat der Designer ein- <xref:System.Data.Linq.DataContext> Objekt für das Projekt hinzugefügt. Dieses Objekt enthält den Code, den Sie für den Zugriff auf diese Prozeduren benötigen. Das- <xref:System.Data.Linq.DataContext> Objekt für das Projekt wird basierend auf dem Namen der DBML-Datei benannt. Für dieses Projekt hat das <xref:System.Data.Linq.DataContext> Objekt den Namen `northwindDataContext` .  
  
     Sie können eine Instanz von <xref:System.Data.Linq.DataContext> im Code erstellen und die im O/R-Designer angegebenen Methoden der gespeicherten Prozedur aufzurufen. Zum Binden an das- <xref:System.Windows.Forms.DataGridView> Objekt müssen Sie möglicherweise erzwingen, dass die Abfrage sofort ausgeführt wird, indem Sie die- <xref:System.Linq.Enumerable.ToList%2A> Methode für die Ergebnisse der gespeicherten Prozedur aufrufen.  
  
     Fügen Sie dem-Ereignis folgenden Code hinzu `Load` , um eine der gespeicherten Prozeduren aufzurufen, die als Methoden für den Datenkontext verfügbar gemacht werden.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ](index.md)
- [Abfragen](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
