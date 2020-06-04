---
title: 'Vorgehensweise: Sortieren von Abfrageergebnissen unter Verwendung von LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- sorting query results, multiple columns
- sorting data [Visual Basic]
- sorting data [LINQ in Visual Basic]
- sorting query results [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], sorting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 07a4584d-9fd8-4a1d-b7d9-ccf2efa5c84e
ms.openlocfilehash: c1bc6ab863f9de118d59e102d3d5d251d326f497
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404938"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a>Gewusst wie: Sortieren von Abfrageergebnissen unter Verwendung von LINQ (Visual Basic)
Language-Integrated Query (LINQ) vereinfacht den Zugriff auf Datenbankinformationen und das Ausführen von Abfragen.  
  
 Im folgenden Beispiel wird gezeigt, wie Sie eine neue Anwendung erstellen, die Abfragen für eine SQL Server Datenbank ausführt und die Ergebnisse nach mehreren Feldern sortiert, indem Sie die- `Order By` Klausel verwenden. Die Sortierreihenfolge für jedes Feld kann eine aufsteigende oder absteigende Reihenfolge sein. Weitere Informationen finden Sie unter [Order By-Klausel](../../../language-reference/queries/order-by-clause.md).  
  
 In den Beispielen in diesem Thema wird die Beispieldatenbank Northwind verwendet. Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie sie aus dem Microsoft Download Center herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispiel Datenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>So erstellen Sie eine Verbindung mit einer Datenbank  
  
1. Öffnen Sie in Visual Studio **Server-Explorer** / **Datenbank-Explorer** , indem **Server Explorer**Sie / im Menü **Ansicht** auf Server-Explorer**Datenbank-Explorer** klicken.  
  
2. Klicken Sie in **Server-Explorer**Datenbank-Explorer mit der rechten Maustaste auf **Datenverbindungen** / **Database Explorer** und dann auf **Verbindung hinzufügen**.  
  
3. Geben Sie eine gültige Verbindung mit der Northwind-Beispieldatenbank an.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>So fügen Sie ein Projekt hinzu, das eine LINQ to SQL Datei enthält  
  
1. Zeigen Sie in Visual Studio im Menü **Datei** auf **neu** , und klicken Sie dann auf **Projekt**. Wählen Sie Visual Basic **Windows Forms Anwendung** als Projekttyp aus.  
  
2. Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. Wählen Sie die Element Vorlage **LINQ to SQL Klassen** aus.  
  
3. Benennen Sie die Datei mit `northwind.dbml`. Klicken Sie auf **Hinzufügen**. Der objektrelationaler Designer (O/R-Designer) wird für die Datei Northwind. dbml geöffnet.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>So fügen Sie dem O/R-Designer abzufragende Tabellen hinzu  
  
1. Erweitern Sie in **Server-Explorer** / **Datenbank-Explorer**die Verbindung mit der Northwind-Datenbank. Erweitern Sie den Ordner **Tabellen** .  
  
     Wenn Sie den O/R-Designer geschlossen haben, können Sie ihn erneut öffnen, indem Sie auf die Datei Northwind. dbml, die Sie zuvor hinzugefügt haben, doppelklicken.  
  
2. Klicken Sie auf die Tabelle Customers, und ziehen Sie Sie in den linken Bereich des Designers. Klicken Sie auf die Tabelle Orders, und ziehen Sie Sie in den linken Bereich des Designers.  
  
     Der Designer erstellt neue `Customer` - `Order` Objekte und-Objekte für Ihr Projekt. Beachten Sie, dass der Designer automatisch Beziehungen zwischen den Tabellen erkennt und untergeordnete Eigenschaften für verbundene Objekte erstellt. IntelliSense zeigt beispielsweise, dass das- `Customer` Objekt über eine- `Orders` Eigenschaft für alle Bestellungen verfügt, die mit diesem Kunden verknüpft sind.  
  
3. Speichern Sie die Änderungen, und schließen Sie den Designer.  
  
4. Speichern Sie das Projekt.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>So fügen Sie Code hinzu, um die Datenbank abzufragen und die Ergebnisse anzuzeigen  
  
1. Ziehen Sie aus der **Toolbox**ein- <xref:System.Windows.Forms.DataGridView> Steuerelement auf das Windows-Standardformular für das Projekt, Form1.  
  
2. Doppelklicken Sie auf Form1, um dem- `Load` Ereignis des Formulars Code hinzuzufügen.  
  
3. Wenn Sie dem O/R-Designer Tabellen hinzugefügt haben, hat der Designer dem Projekt ein-Objekt hinzugefügt <xref:System.Data.Linq.DataContext> . Dieses Objekt enthält den Code, den Sie für den Zugriff auf diese Tabellen benötigen, und für den Zugriff auf einzelne Objekte und Auflistungen für jede Tabelle. Das- <xref:System.Data.Linq.DataContext> Objekt für das Projekt wird basierend auf dem Namen der DBML-Datei benannt. Für dieses Projekt hat das <xref:System.Data.Linq.DataContext> Objekt den Namen `northwindDataContext` .  
  
     Sie können eine Instanz von <xref:System.Data.Linq.DataContext> im Code erstellen und die im O/R-Designer angegebenen Tabellen Abfragen.  
  
     Fügen Sie dem-Ereignis den folgenden Code hinzu `Load` , um die Tabellen abzufragen, die als Eigenschaften des Daten Kontexts verfügbar gemacht werden, und die Ergebnisse zu sortieren. Die Abfrage sortiert die Ergebnisse nach der Anzahl der Kunden Bestellungen in absteigender Reihenfolge. Kunden, die über die gleiche Anzahl von Bestellungen verfügen, werden nach Firmenname in aufsteigender Reihenfolge sortiert (Standard).  
  
     [!code-vb[VbLINQToSQLHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form4.vb#10)]  
  
4. Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.  
  
## <a name="see-also"></a>Weitere Informationen

- [LINQ](index.md)
- [Abfragen](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
