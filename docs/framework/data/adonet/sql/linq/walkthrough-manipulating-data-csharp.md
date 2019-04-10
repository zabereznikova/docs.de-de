---
title: 'Exemplarische Vorgehensweise: Bearbeiten von Daten (C#)'
ms.date: 03/30/2017
ms.assetid: 24adfbe0-0ad6-449f-997d-8808e0770d2e
ms.openlocfilehash: 5418bdbdeee162bbc8c0abcb11fd39f2cc82ce73
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59330778"
---
# <a name="walkthrough-manipulating-data-c"></a>Exemplarische Vorgehensweise: Bearbeiten von Daten (C#)
Diese exemplarische Vorgehensweise stellt ein grundlegendes End-to-End-Szenario für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zum Hinzufügen, Ändern und Löschen von Daten in einer Datenbank bereit. Sie werden eine Kopie der Beispieldatenbank Northwind verwenden, um einen Kunden hinzuzufügen, den Namen des Kunden zu ändern und eine Bestellung zu löschen.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Diese exemplarische Vorgehensweise wurde mithilfe von Visual C#-Entwicklungseinstellungen geschrieben.  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:  
  
-   Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner ("c:\linqtest6") als Speicherort für Dateien. Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.  
  
-   Die Beispieldatenbank Northwind.  
  
     Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei northwnd.mdf in den Ordner c:\linqtest6.  
  
-   Eine von der Datenbank Northwind generierte C#-Codedatei.  
  
     Sie können diese Datei erzeugen, indem Sie entweder den [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] oder das SQLMetal-Tool verwenden. Diese exemplarische Vorgehensweise wurde mithilfe des SQLMetal-Tools mit der folgenden Befehlszeile geschrieben:  
  
     **sqlmetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" /pluralize**  
  
     Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Übersicht  
 Diese exemplarische Vorgehensweise umfasst sechs Hauptaufgaben:  
  
-   Erstellen der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projektmappe in Visual Studio.  
  
-   Hinzufügen der Datenbank-Codedatei zum Projekt.  
  
-   Erstellen eines neuen Kundenobjekts.  
  
-   Ändern des Kontaktnamens eines Kunden.  
  
-   Löschen einer Bestellung.  
  
-   Übergeben dieser Änderungen an der Datenbank Northwind.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Erstellen einer LINQ to SQL-Lösung  
 In dieser ersten Aufgabe erstellen Sie eine Visual Studio-Projektmappe, die die erforderlichen Verweise zur Erstellung und Ausführung enthält eine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekt.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>So erstellen Sie eine LINQ to SQL-Lösung  
  
1. Visual Studio **Datei** Startmenü **neu**, und klicken Sie dann auf **Projekt**.  
  
2. In der **Projekttypen** im Bereich der **neues Projekt** Dialogfeld klicken Sie auf **Visual C#** .  
  
3. Klicken Sie im Bereich **Vorlagen** auf **Konsolenanwendung**.  
  
4. In der **Namen** geben **LinqDataManipulationApp**.  
  
5. In der **Speicherort** Vergewissern Sie sich, in der Sie die Projektdateien speichern möchten.  
  
6. Klicken Sie auf **OK**.  
  
## <a name="adding-linq-references-and-directives"></a>Hinzufügen von LINQ-Verweisen und Anweisungen  
 Diese exemplarische Vorgehensweise verwendet Assemblys, die im Projekt u. U. nicht standardmäßig installiert sind. Wird System.Data.Linq in Ihrem Projekt nicht als Verweis aufgeführt, fügen Sie diesen wie nachfolgend beschrieben hinzu.  
  
#### <a name="to-add-systemdatalinq"></a>So fügen Sie System.Data.Linq hinzu  
  
1. In **Projektmappen-Explorer**, mit der rechten Maustaste **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.  
  
2. In der **Verweis hinzufügen** Dialogfeld klicken Sie auf **.NET**, klicken Sie auf die System.Data.Linq-Assembly, und klicken Sie dann auf **OK**.  
  
     Dem Projekt wird die Assembly hinzugefügt.  
  
3. Fügen Sie die folgenden Direktiven am oberen Rand von Program.cs hinzu:  
  
     [!code-csharp[DLinqWalk3CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Hinzufügen der Northwind-Codedatei zum Projekt.  
 Bei diesen Schritten wird davon ausgegangen, dass Sie das SQLMetal-Tool zum Erzeugen einer Codedatei aus der Beispieldatenbank Northwind verwendet haben. Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>So fügen Sie die Northwind-Codedatei dem Projekt hinzu.  
  
1. Auf der **Projekt** Menü klicken Sie auf **vorhandenes Element hinzufügen**.  
  
2. In der **vorhandenes Element hinzufügen** Dialogfeld, navigieren Sie zu c:\linqtest6\northwind.cs, und klicken Sie dann auf **hinzufügen**.  
  
     Die Datei northwind.cs wird dem Projekt hinzugefügt.  
  
## <a name="setting-up-the-database-connection"></a>Einrichten der Datenverbindungen  
 Testen Sie zuerst die Verbindung zur Datenbank. Beachten Sie vor allem, dass die Datenbank, Northwnd, kein i-Zeichen hat. Sollten im nächsten Schritt Fehler auftreten, prüfen Sie in der Datei northwind.cs die Schreibweise der partiellen Klasse Northwind.  
  
#### <a name="to-set-up-and-test-the-database-connection"></a>So richten Sie die Datenbankverbindung ein und testen diese  
  
1. Geben Sie den folgenden Code in die `Main`-Methode in der Programmklasse ein, oder fügen Sie ihn ein:  
  
     [!code-csharp[DLinqWalk3CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#2)]  
  
2. Drücken Sie die Taste F5, um die Anwendung an diesem Punkt zu testen.  
  
     Ein **Konsole** Fenster wird geöffnet.  
  
     Schließen Sie die Anwendung durch Drücken der EINGABETASTE in den **Konsole** Fenster oder durch Klicken auf **Debuggen beenden** auf der Visual Studio **Debuggen** Menü.  
  
## <a name="creating-a-new-entity"></a>Erstellen einer neuen Entität  
 Eine neue Entität zu erstellen, ist einfach. Sie können Objekte (z. B. `Customer`) erstellen, indem Sie das `new`-Schlüsselwort verwenden.  
  
 In diesem und den folgenden Abschnitten nehmen Sie Änderungen nur am lokalen Cache vor. Es werden keine Änderungen an die Datenbank gesendet, bis Sie zum Ende dieser exemplarischen Vorgehensweise <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen.  
  
#### <a name="to-add-a-new-customer-entity-object"></a>So fügen Sie ein neues Kundenentitätsobjekt hinzu  
  
1. Erstellen Sie einen neuen `Customer`, indem Sie den folgenden Code vor `Console.ReadLine();` in der `Main`-Methode hinzufügen:  
  
     [!code-csharp[DLinqWalk3CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#3)]  
  
2. Drücken Sie die Taste F5, um die Lösung zu Debuggen.  
  
3. Drücken Sie die EINGABETASTE in den **Konsole** Fenster aus, um den Debugvorgang unterbrechen und Fortsetzen der exemplarischen Vorgehensweise.  
  
## <a name="updating-an-entity"></a>Aktualisieren einer Entität  
 In den folgenden Schritten rufen Sie ein `Customer`-Objekt ab und ändern eine seiner Eigenschaften.  
  
#### <a name="to-change-the-name-of-a-customer"></a>So ändern Sie den Namen eines Kunden  
  
-   Fügen Sie den folgenden Code oberhalb von `Console.ReadLine();` ein:  
  
     [!code-csharp[DLinqWalk3CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#4)]  
  
## <a name="deleting-an-entity"></a>Löschen einer Entität  
 Unter Verwendung des gleichen Kundenobjekts können Sie die erste Bestellung löschen.  
  
 Der folgende Code zeigt, wie Beziehungen zwischen Zeilen getrennt werden und wie eine Zeile aus der Datenbank Northwind gelöscht wird. Fügen Sie den folgenden Code vor `Console.ReadLine` hinzu, um zu sehen, wie Objekte gelöscht werden können:  
  
#### <a name="to-delete-a-row"></a>So löschen Sie eine Zeile  
  
-   Fügen Sie den folgenden Code genau oberhalb von `Console.ReadLine();` ein.  
  
     [!code-csharp[DLinqWalk3CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#5)]  
  
## <a name="submitting-changes-to-the-database"></a>Übergeben von Änderungen an die Datenbank  
 Der letzte Schritt beim Erstellen, Aktualisieren und Löschen von Objekten besteht in der eigentlichen Übergabe der Änderungen an die Datenbank. Ohne diesen Schritt sind die Änderungen nur lokal und werden nicht in Abfrageergebnissen angezeigt.  
  
#### <a name="to-submit-changes-to-the-database"></a>So übergeben Sie die Änderungen an die Datenbank  
  
1. Fügen Sie den folgenden Code genau oberhalb von `Console.ReadLine` ein:  
  
     [!code-csharp[DLinqWalk3CS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#6)]  
  
2. Fügen Sie den folgenden Code (nach `SubmitChanges`) ein, um den Vorher-Nachher-Effekt der Änderungsübergabe zu zeigen:  
  
     [!code-csharp[DLinqWalk3CS#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#7)]  
  
3. Drücken Sie die Taste F5, um die Lösung zu Debuggen.  
  
4. Drücken Sie die EINGABETASTE in den **Konsole** Fenster aus, um die Anwendung zu schließen.  
  
> [!NOTE]
>  Wenn Sie den neuen Kunden durch Übergeben der Änderungen hinzugefügt haben, können Sie diese Lösung nicht einfach wieder ausführen. Um die Lösung erneut auszuführen, ändern Sie den Namen und die ID des hinzuzufügenden Kunden.  
  
## <a name="see-also"></a>Siehe auch

- [Lernen durch exemplarische Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
