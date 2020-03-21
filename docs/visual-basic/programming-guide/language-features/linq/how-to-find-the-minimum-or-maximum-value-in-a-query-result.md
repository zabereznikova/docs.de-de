---
title: 'Gewusst wie: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis mithilfe von LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause [Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
ms.openlocfilehash: ef5f218cdcc7275f616486110825ad0b9df11cc3
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112361"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a>Gewusst wie: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis mithilfe von LINQ (Visual Basic)
Language-Integrated Query (LINQ) erleichtert den Zugriff auf Datenbankinformationen und das Ausführen von Abfragen.  
  
 Das folgende Beispiel zeigt, wie Sie eine neue Anwendung erstellen, die Abfragen für eine SQL Server-Datenbank ausführt. Die Stichprobe bestimmt die minimalen und maximalen `Aggregate` `Group By` Werte für die Ergebnisse mithilfe der und-Klauseln. Weitere Informationen finden Sie unter [Aggregatklausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md) und [Gruppenklausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
 In den Beispielen in diesem Thema wird die Northwind-Beispieldatenbank verwendet. Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie sie aus dem Microsoft Download Center herunterladen. Anweisungen finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a>Erstellen einer Verbindung zu einer Datenbank  
  
1. Öffnen Sie in Visual Studio den/Server**Explorer-Datenbank-Explorer,** **Server Explorer**/indem Sie im Menü **Ansicht** auf den **Server-Explorer-Datenbank-Explorer**klicken.**Database Explorer**  
  
2. Klicken Sie im **Server**/**Explorer-Datenbank-Explorer** mit der rechten Maustaste auf **Datenverbindungen,** und klicken Sie dann auf **Verbindung hinzufügen**.  
  
3. Geben Sie eine gültige Verbindung zur Northwind-Beispieldatenbank an.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>So fügen Sie ein Projekt hinzu, das eine LINQ zu SQL-Datei enthält  
  
1. Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu,** und klicken Sie dann auf **Projekt**. Wählen Sie Visual Basic **Windows Forms Application** als Projekttyp aus.  
  
2. Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. Wählen Sie die Elementvorlage **LINQ zu SQL Classes** aus.  
  
3. Benennen Sie die Datei `northwind.dbml`. Klicken Sie auf **Hinzufügen**. Der Object Relational Designer (O/R Designer) wird für die Datei northwind.dbml geöffnet.  
  
## <a name="add-tables-to-query-to-the-or-designer"></a>Hinzufügen von Tabellen zur Abfrage zum O/R-Designer  
  
1. Erweitern Sie im Server/**Explorer-Datenbank-Explorer**die Verbindung zur Northwind-Datenbank. **Server Explorer** Erweitern Sie den Ordner **Tabellen** .  
  
     Wenn Sie den O/R-Designer geschlossen haben, können Sie ihn erneut öffnen, indem Sie auf die Datei northwind.dbml doppelklicken, die Sie zuvor hinzugefügt haben.  
  
2. Klicken Sie auf die Tabelle Kunden, und ziehen Sie sie in den linken Bereich des Designers. Klicken Sie auf die Tabelle Aufträge, und ziehen Sie sie in den linken Bereich des Designers.  
  
     Der Designer `Customer` erstellt `Order` neue Objekte und Objekte für Ihr Projekt. Beachten Sie, dass der Designer automatisch Beziehungen zwischen den Tabellen erkennt und untergeordnete Eigenschaften für verwandte Objekte erstellt. IntelliSense zeigt beispielsweise an, `Customer` dass `Orders` das Objekt über eine Eigenschaft für alle Aufträge verfügt, die sich auf diesen Kunden beziehen.  
  
3. Speichern Sie Ihre Änderungen, und schließen Sie den Designer.  
  
4. Speichern Sie das Projekt.  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a>Hinzufügen von Code zum Abfragen der Datenbank und Anzeigen der Ergebnisse  
  
1. Ziehen **Toolbox**Sie aus <xref:System.Windows.Forms.DataGridView> der Toolbox ein Steuerelement auf das Standard-Windows-Formular für Ihr Projekt, Form1.  
  
2. Doppelklicken Sie auf Form1, `Load` um code zum Ereignis des Formulars hinzuzufügen.  
  
3. Beim Hinzugefügt von Tabellen zum O/R-Designer <xref:System.Data.Linq.DataContext> hat der Designer ein Objekt für Ihr Projekt hinzugefügt. Dieses Objekt enthält den Code, auf den Sie für diese Tabellen zugreifen müssen, zusätzlich zu einzelnen Objekten und Auflistungen für jede Tabelle. Das <xref:System.Data.Linq.DataContext> Objekt für Ihr Projekt wird basierend auf dem Namen Ihrer DBml-Datei benannt. Für dieses Projekt <xref:System.Data.Linq.DataContext> heißt `northwindDataContext`das Objekt .  
  
     Sie können eine Instanz <xref:System.Data.Linq.DataContext> des in Ihrem Code erstellen und die vom O/R-Designer angegebenen Tabellen abfragen.  
  
     Fügen Sie dem `Load` Ereignis den folgenden Code hinzu. Dieser Code fragt die Tabellen ab, die als Eigenschaften des Datenkontexts verfügbar gemacht werden, und bestimmt die minimalen und maximalen Werte für die Ergebnisse. Das Beispiel `Aggregate` verwendet die Klausel, um ein `Group By` einzelnes Ergebnis abzufragen, und die Klausel, um einen Durchschnitt für gruppierte Ergebnisse anzuzeigen.  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. Drücken Sie **F5,** um das Projekt auszuführen und die Ergebnisse anzuzeigen.  
  
## <a name="see-also"></a>Weitere Informationen

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
