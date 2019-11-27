---
title: 'Gewusst wie: zählen, Summen oder durchschnittliche Daten mithilfe von LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- average operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- queries [LINQ in Visual Basic], sum results
- Aggregate clause [Visual Basic]
- sum operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], counting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- count operator [LINQ in Visual Basic]
ms.assetid: 51ca1f59-7770-4884-8b76-113002e54fc0
ms.openlocfilehash: 7e105c75653f979f53567ef49f1f4cdeafaa4d0f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345009"
---
# <a name="how-to-count-sum-or-average-data-by-using-linq-visual-basic"></a>Gewusst wie: Bestimmen von Zahlen, Summen oder Durchschnittswerten von Daten mithilfe von LINQ (Visual Basic)
Language-Integrated Query (LINQ) vereinfacht den Zugriff auf Datenbankinformationen und das Ausführen von Abfragen.  
  
 Im folgenden Beispiel wird gezeigt, wie eine neue Anwendung erstellt wird, die Abfragen für eine SQL Server Datenbank ausführt. Im Beispiel werden die Ergebnisse mit den `Aggregate`-und `Group By`-Klauseln gezählt, addiert und in den Mittelwerten angegeben. Weitere Informationen finden Sie unter [Aggregat Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md) und [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
 In den Beispielen in diesem Thema wird die Beispieldatenbank Northwind verwendet. Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese aus dem Microsoft Download Center herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispiel Datenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>So erstellen Sie eine Verbindung mit einer Datenbank  
  
1. Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** , indem Sie im Menü **Ansicht** auf **Server-Explorer** **/Datenbank-Explorer** klicken.  
  
2. Klicken Sie in **Server-Explorer** **Datenbank-Explorer**/mit der rechten Maustaste auf **Datenverbindungen** , und klicken Sie dann auf **Verbindung hinzufügen**.  
  
3. Geben Sie eine gültige Verbindung mit der Northwind-Beispieldatenbank an.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>So fügen Sie ein Projekt hinzu, das eine LINQ to SQL Datei enthält  
  
1. Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**. Wählen Sie Visual Basic **Windows Forms Anwendung** als Projekttyp aus.  
  
2. Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. Wählen Sie die Element Vorlage **LINQ to SQL Klassen** aus.  
  
3. Nennen Sie die Datei `northwind.dbml`. Klicken Sie auf **Hinzufügen**. Der objektrelationaler Designer (O/R-Designer) wird für die Datei Northwind. dbml geöffnet.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>So fügen Sie dem O/R-Designer abzufragende Tabellen hinzu  
  
1. Erweitern Sie in **Server-Explorer**/**Datenbank-Explorer**die Verbindung mit der Northwind-Datenbank. Erweitern Sie den Ordner **Tabellen** .  
  
     Wenn Sie den O/R-Designer geschlossen haben, können Sie ihn erneut öffnen, indem Sie auf die Datei Northwind. dbml, die Sie zuvor hinzugefügt haben, doppelklicken.  
  
2. Klicken Sie auf die Tabelle Customers, und ziehen Sie Sie in den linken Bereich des Designers. Klicken Sie auf die Tabelle Orders, und ziehen Sie Sie in den linken Bereich des Designers.  
  
     Der Designer erstellt neue `Customer` und `Order` Objekte für Ihr Projekt. Beachten Sie, dass der Designer automatisch Beziehungen zwischen den Tabellen erkennt und untergeordnete Eigenschaften für verbundene Objekte erstellt. IntelliSense zeigt z. b. an, dass das `Customer` Objekt über eine `Orders`-Eigenschaft für alle Bestellungen verfügt, die mit diesem Kunden verknüpft sind.  
  
3. Speichern Sie die Änderungen, und schließen Sie den Designer.  
  
4. Speichern Sie das Projekt.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>So fügen Sie Code hinzu, um die Datenbank abzufragen und die Ergebnisse anzuzeigen  
  
1. Ziehen Sie aus der **Toolbox**ein <xref:System.Windows.Forms.DataGridView>-Steuerelement auf das standardmäßige Windows Form für Ihr Projekt, Form1.  
  
2. Doppelklicken Sie auf Form1, um dem `Load`-Ereignis des Formulars Code hinzuzufügen.  
  
3. Wenn Sie dem O/R-Designer Tabellen hinzugefügt haben, hat der Designer ein <xref:System.Data.Linq.DataContext>-Objekt für das Projekt hinzugefügt. Dieses Objekt enthält den Code, den Sie für den Zugriff auf diese Tabellen benötigen, und für den Zugriff auf einzelne Objekte und Auflistungen für jede Tabelle. Das <xref:System.Data.Linq.DataContext>-Objekt für das Projekt wird basierend auf dem Namen der DBML-Datei benannt. Für dieses Projekt wird das <xref:System.Data.Linq.DataContext> Objekt `northwindDataContext`benannt.  
  
     Sie können eine Instanz des <xref:System.Data.Linq.DataContext> in Ihrem Code erstellen und die im O/R-Designer angegebenen Tabellen Abfragen.  
  
     Fügen Sie dem `Load`-Ereignis den folgenden Code hinzu, um die Tabellen abzufragen, die als Eigenschaften ihrer <xref:System.Data.Linq.DataContext> verfügbar gemacht werden, sowie die Anzahl, Summe und den Durchschnitt der Ergebnisse. Das Beispiel verwendet die `Aggregate`-Klausel, um ein einzelnes Ergebnis abzufragen, und die `Group By`-Klausel, um einen Durchschnitt für gruppierte Ergebnisse anzuzeigen.  
  
     [!code-vb[VbLINQToSQLHowTos#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form6.vb#13)]  
  
4. Drücken Sie F5, um das Projekt auszuführen und die Ergebnisse anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md)
