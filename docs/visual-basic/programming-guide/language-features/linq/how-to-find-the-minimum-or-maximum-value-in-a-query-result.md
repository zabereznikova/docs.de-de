---
title: 'Vorgehensweise: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis mithilfe von LINQ'
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
ms.openlocfilehash: a148d8b726da78261eda152fcaafdd64ea01bb24
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404977"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a>Gewusst wie: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis mithilfe von LINQ (Visual Basic)
Language-Integrated Query (LINQ) vereinfacht den Zugriff auf Datenbankinformationen und das Ausführen von Abfragen.  
  
 Im folgenden Beispiel wird gezeigt, wie eine neue Anwendung erstellt wird, die Abfragen für eine SQL Server Datenbank ausführt. Im Beispiel werden die Mindest-und Maximalwerte für die Ergebnisse mithilfe der `Aggregate` -Klausel und der- `Group By` Klausel bestimmt. Weitere Informationen finden Sie unter [Aggregat Klausel](../../../language-reference/queries/aggregate-clause.md) und [Group By-Klausel](../../../language-reference/queries/group-by-clause.md).  
  
 In den Beispielen in diesem Thema wird die Beispieldatenbank Northwind verwendet. Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie sie aus dem Microsoft Download Center herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispiel Datenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a>Herstellen einer Verbindung mit einer Datenbank  
  
1. Öffnen Sie in Visual Studio **Server-Explorer** / **Datenbank-Explorer** , indem **Server Explorer**Sie / im Menü **Ansicht** auf Server-Explorer**Datenbank-Explorer** klicken.  
  
2. Klicken Sie in **Server-Explorer**Datenbank-Explorer mit der rechten Maustaste auf **Datenverbindungen** / **Database Explorer** und dann auf **Verbindung hinzufügen**.  
  
3. Geben Sie eine gültige Verbindung mit der Northwind-Beispieldatenbank an.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>So fügen Sie ein Projekt hinzu, das eine LINQ to SQL Datei enthält  
  
1. Zeigen Sie in Visual Studio im Menü **Datei** auf **neu** , und klicken Sie dann auf **Projekt**. Wählen Sie Visual Basic **Windows Forms Anwendung** als Projekttyp aus.  
  
2. Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. Wählen Sie die Element Vorlage **LINQ to SQL Klassen** aus.  
  
3. Benennen Sie die Datei mit `northwind.dbml`. Klicken Sie auf **Hinzufügen**. Der objektrelationaler Designer (O/R-Designer) wird für die Datei Northwind. dbml geöffnet.  
  
## <a name="add-tables-to-query-to-the-or-designer"></a>Hinzufügen von Tabellen zum Abfragen an den O/R-Designer  
  
1. Erweitern Sie in **Server-Explorer** / **Datenbank-Explorer**die Verbindung mit der Northwind-Datenbank. Erweitern Sie den Ordner **Tabellen** .  
  
     Wenn Sie den O/R-Designer geschlossen haben, können Sie ihn erneut öffnen, indem Sie auf die Datei Northwind. dbml, die Sie zuvor hinzugefügt haben, doppelklicken.  
  
2. Klicken Sie auf die Tabelle Customers, und ziehen Sie Sie in den linken Bereich des Designers. Klicken Sie auf die Tabelle Orders, und ziehen Sie Sie in den linken Bereich des Designers.  
  
     Der Designer erstellt neue `Customer` - `Order` Objekte und-Objekte für Ihr Projekt. Beachten Sie, dass der Designer automatisch Beziehungen zwischen den Tabellen erkennt und untergeordnete Eigenschaften für verbundene Objekte erstellt. IntelliSense zeigt beispielsweise, dass das- `Customer` Objekt über eine- `Orders` Eigenschaft für alle Bestellungen verfügt, die mit diesem Kunden verknüpft sind.  
  
3. Speichern Sie die Änderungen, und schließen Sie den Designer.  
  
4. Speichern Sie das Projekt.  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a>Hinzufügen von Code zum Abfragen der Datenbank und Anzeigen der Ergebnisse  
  
1. Ziehen Sie aus der **Toolbox**ein- <xref:System.Windows.Forms.DataGridView> Steuerelement auf das Windows-Standardformular für das Projekt, Form1.  
  
2. Doppelklicken Sie auf Form1, um dem- `Load` Ereignis des Formulars Code hinzuzufügen.  
  
3. Wenn Sie dem O/R-Designer Tabellen hinzugefügt haben, hat der Designer ein- <xref:System.Data.Linq.DataContext> Objekt für das Projekt hinzugefügt. Dieses Objekt enthält den Code, den Sie für den Zugriff auf diese Tabellen benötigen, zusätzlich zu den einzelnen Objekten und Auflistungen für jede Tabelle. Das- <xref:System.Data.Linq.DataContext> Objekt für das Projekt wird basierend auf dem Namen der DBML-Datei benannt. Für dieses Projekt hat das <xref:System.Data.Linq.DataContext> Objekt den Namen `northwindDataContext` .  
  
     Sie können eine Instanz von <xref:System.Data.Linq.DataContext> im Code erstellen und die im O/R-Designer angegebenen Tabellen Abfragen.  
  
     Fügen Sie dem-Ereignis den folgenden Code hinzu `Load` . Dieser Code fragt die Tabellen ab, die als Eigenschaften des Daten Kontexts verfügbar gemacht werden, und bestimmt die minimalen und maximalen Werte für die Ergebnisse. Das Beispiel verwendet die `Aggregate` -Klausel, um ein einzelnes Ergebnis abzufragen, und die- `Group By` Klausel, um einen Durchschnitt für gruppierte Ergebnisse anzuzeigen.  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. Drücken Sie **F5** , um das Projekt auszuführen und die Ergebnisse anzuzeigen.  
  
## <a name="see-also"></a>Weitere Informationen

- [LINQ](index.md)
- [Abfragen](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
