---
title: 'Exemplarische Vorgehensweise: Bearbeiten von Daten (Visual Basic)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- vb
ms.assetid: 1f6a54f6-ec33-452a-a37d-48122207bf14
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: b4bc7baee8e95243cf05a52f49c37aa2d8916666
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="walkthrough-manipulating-data-visual-basic"></a>Exemplarische Vorgehensweise: Bearbeiten von Daten (Visual Basic)
Diese exemplarische Vorgehensweise stellt ein grundlegendes End-to-End-Szenario für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zum Hinzufügen, Ändern und Löschen von Daten in einer Datenbank bereit. Sie werden eine Kopie der Beispieldatenbank Northwind verwenden, um einen Kunden hinzuzufügen, den Namen des Kunden zu ändern und eine Bestellung zu löschen.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Diese exemplarische Vorgehensweise wurde mithilfe von Visual Basic-Entwicklungseinstellungen geschrieben.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für diese exemplarische Vorgehensweise wird Folgendes vorausgesetzt:  
  
-   Diese exemplarische Vorgehensweise verwendet einen dedizierten Ordner ("c:\linqtest2") als Speicherort für Dateien. Erstellen Sie diesen Ordner, bevor Sie die exemplarische Vorgehensweise starten.  
  
-   Die Beispieldatenbank Northwind.  
  
     Befindet sich diese Datenbank nicht auf Ihrem Entwicklungscomputer, können Sie diese von der Microsoft Downloadsite herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). Nachdem Sie die Datenbank heruntergeladen haben, kopieren Sie die Datei northwnd.mdf in den Ordner c:\linqtest2.  
  
-   Eine von der Datenbank Northwind generierte Visual Basic-Codedatei.  
  
     Sie können diese Datei erzeugen, indem Sie entweder den [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] oder das SQLMetal-Tool verwenden. Diese exemplarische Vorgehensweise wurde mithilfe des SQLMetal-Tools mit der folgenden Befehlszeile geschrieben:  
  
     **sqlmetal /code:"c:\linqtest2\northwind.vb" /language:vb "C:\linqtest2\northwnd.mdf" /pluralize**  
  
     Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Übersicht  
 Diese exemplarische Vorgehensweise umfasst sechs Hauptaufgaben:  
  
-   Erstellen der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Lösung in [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].  
  
-   Hinzufügen der Datenbank-Codedatei zum Projekt.  
  
-   Erstellen eines neuen Kundenobjekts.  
  
-   Ändern des Kontaktnamens eines Kunden.  
  
-   Löschen einer Bestellung.  
  
-   Übergeben dieser Änderungen an der Datenbank Northwind.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Erstellen einer LINQ to SQL-Lösung  
 In dieser ersten Aufgabe erstellen Sie eine [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]-Lösung, die die erforderlichen Verweise zur Erstellung und Ausführung eines [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Projekts enthält.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>So erstellen Sie eine LINQ to SQL-Lösung  
  
1.  Auf der [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **Datei** Menü klicken Sie auf **neues Projekt**.  
  
2.  In der **-Projekttypen** im Bereich der **neues Projekt** (Dialogfeld), klicken Sie auf **Visual Basic**.  
  
3.  Klicken Sie im Bereich **Vorlagen** auf **Konsolenanwendung**.  
  
4.  In der **Namen** geben **LinqDataManipulationApp**.  
  
5.  Klicken Sie auf **OK**.  
  
## <a name="adding-linq-references-and-directives"></a>Hinzufügen von LINQ-Verweisen und Anweisungen  
 Diese exemplarische Vorgehensweise verwendet Assemblys, die im Projekt u. U. nicht standardmäßig installiert sind. Wenn `System.Data.Linq` nicht als Verweis im Projekt aufgeführt (klicken Sie auf **alle Dateien anzeigen** in **Projektmappen-Explorer** und erweitern Sie die **Verweise** Knoten), fügen Sie es, wie beschrieben die folgenden Schritte aus.  
  
#### <a name="to-add-systemdatalinq"></a>So fügen Sie System.Data.Linq hinzu  
  
1.  In **Projektmappen-Explorer**, mit der rechten Maustaste **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.  
  
2.  In der **Verweis hinzufügen** (Dialogfeld), klicken Sie auf **.NET**, klicken Sie auf die System.Data.Linq-Assembly, und klicken Sie dann auf **OK**.  
  
     Dem Projekt wird die Assembly hinzugefügt.  
  
3.  Fügen Sie im Code-Editor die folgenden Direktiven oberhalb **Module1**:  
  
     [!code-vb[DLinqWalk3VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Hinzufügen der Northwind-Codedatei zum Projekt.  
 Bei diesen Schritten wird davon ausgegangen, dass Sie das SQLMetal-Tool zum Erzeugen einer Codedatei aus der Beispieldatenbank Northwind verwendet haben. Weitere Informationen finden Sie im Abschnitt zu Voraussetzungen weiter oben in dieser exemplarischen Vorgehensweise.  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>So fügen Sie die Northwind-Codedatei dem Projekt hinzu.  
  
1.  Auf der **Projekt** Menü klicken Sie auf **vorhandenes Element hinzufügen**.  
  
2.  In der **vorhandenes Element hinzufügen** (Dialogfeld), navigieren Sie zu c:\linqtest2\northwind.vb, und klicken Sie dann auf **hinzufügen**.  
  
     Die Datei northwind.vb wird dem Projekt hinzugefügt.  
  
## <a name="setting-up-the-database-connection"></a>Einrichten der Datenverbindungen  
 Testen Sie zuerst die Verbindung zur Datenbank. Beachten Sie vor allem, dass der Name der Datenbank, Northwnd, kein i-Zeichen hat. Sollten im nächsten Schritt Fehler auftreten, prüfen Sie in der Datei northwind.vb die Schreibweise der partiellen Klasse Northwind.  
  
#### <a name="to-set-up-and-test-the-database-connection"></a>So richten Sie die Datenbankverbindung ein und testen diese  
  
1.  Geben Sie den folgenden Code in `Sub Main` ein, oder fügen Sie ihn ein:  
  
     [!code-vb[DLinqWalk3VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#2)]  
  
2.  Drücken Sie die Taste F5, um die Anwendung an diesem Punkt zu testen.  
  
     Ein **Konsole** Fenster wird geöffnet.  
  
     Schließen Sie die Anwendung durch Drücken der EINGABETASTE in der **Konsole** Fenster, oder indem Sie auf **Debuggen beenden** auf die [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **Debuggen** Menü.  
  
## <a name="creating-a-new-entity"></a>Erstellen einer neuen Entität  
 Eine neue Entität zu erstellen, ist einfach. Sie können Objekte (z. B. `Customer`) erstellen, indem Sie das `New`-Schlüsselwort verwenden.  
  
 In diesem und den folgenden Abschnitten nehmen Sie Änderungen nur am lokalen Cache vor. Es werden keine Änderungen an die Datenbank gesendet, bis Sie zum Ende dieser exemplarischen Vorgehensweise <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen.  
  
#### <a name="to-add-a-new-customer-entity-object"></a>So fügen Sie ein neues Kundenentitätsobjekt hinzu  
  
1.  Erstellen Sie einen neuen `Customer`, indem Sie den folgenden Code vor `Console.ReadLine` in `Sub Main` hinzufügen:  
  
     [!code-vb[DLinqWalk3VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#3)]  
  
2.  Drücken Sie die Taste F5, um die Lösung zu Debuggen.  
  
     Im Konsolenfenster werden die folgenden Ergebnisse angezeigt:  
  
     `Customers matching CA before insert:`  
  
     `Customer ID: CACTU`  
  
     `Customer ID: RICAR`  
  
     Beachten Sie, dass die neue Zeile nicht in den Ergebnissen angezeigt wird. Die neuen Daten wurden noch nicht an die Datenbank übergeben.  
  
3.  Drücken Sie die EINGABETASTE in den **Konsole** Fenster zum Beenden des Debuggens.  
  
## <a name="updating-an-entity"></a>Aktualisieren einer Entität  
 In den folgenden Schritten rufen Sie ein `Customer`-Objekt ab und ändern eine seiner Eigenschaften.  
  
#### <a name="to-change-the-name-of-a-customer"></a>So ändern Sie den Namen eines Kunden  
  
-   Fügen Sie den folgenden Code oberhalb von `Console.ReadLine()` ein:  
  
     [!code-vb[DLinqWalk3VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#4)]  
  
## <a name="deleting-an-entity"></a>Löschen einer Entität  
 Unter Verwendung des gleichen Kundenobjekts können Sie die erste Bestellung löschen.  
  
 Der folgende Code zeigt, wie Beziehungen zwischen Zeilen getrennt werden und wie eine Zeile aus der Datenbank Northwind gelöscht wird.  
  
#### <a name="to-delete-a-row"></a>So löschen Sie eine Zeile  
  
-   Fügen Sie den folgenden Code genau oberhalb von `Console.ReadLine()` ein.  
  
     [!code-vb[DLinqWalk3VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#5)]  
  
## <a name="submitting-changes-to-the-database"></a>Übergeben von Änderungen an die Datenbank  
 Der letzte Schritt beim Erstellen, Aktualisieren und Löschen von Objekten besteht in der eigentlichen Übergabe der Änderungen an die Datenbank. Ohne diesen Schritt sind die Änderungen nur lokal und werden nicht in Abfrageergebnissen angezeigt.  
  
#### <a name="to-submit-changes-to-the-database"></a>So übergeben Sie die Änderungen an die Datenbank  
  
1.  Fügen Sie den folgenden Code genau oberhalb von `Console.ReadLine` ein:  
  
     [!code-vb[DLinqWalk3VB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#6)]  
  
2.  Fügen Sie den folgenden Code (nach `SubmitChanges`) ein, um den Vorher-Nachher-Effekt der Änderungsübergabe zu zeigen:  
  
     [!code-vb[DLinqWalk3VB#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#7)]  
  
3.  Drücken Sie die Taste F5, um die Lösung zu Debuggen.  
  
     Das Konsolenfenster wird wie folgt angezeigt:  
  
    ```  
    Customers matching CA before update:  
    Customer ID: CACTU  
    Customer ID: RICAR  
  
    The Order Detail to be deleted is: OrderID = 10643  
  
    Customers matching CA after update:  
    Customer ID: A3VCA  
    Customer ID: CACTU  
    Customer ID: RICAR  
    ```  
  
4.  Drücken Sie die EINGABETASTE in den **Konsole** Fenster zum Beenden des Debuggens.  
  
> [!NOTE]
>  Wenn Sie den neuen Kunden durch Übergeben der Änderungen hinzugefügt haben, können Sie diese Lösung nicht einfach wieder ausführen, da Sie den gleichen Kunden nicht erneut hinzufügen können. Um die Lösung erneut auszuführen, ändern Sie den Wert der hinzuzufügenden Kunden-ID.  
  
## <a name="see-also"></a>Siehe auch  
 [Lernen durch exemplarische Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
