---
title: Lernen durch exemplarische Vorgehensweisen
ms.date: 03/30/2017
ms.assetid: a8ae2965-6a49-4155-89b0-7fab2c488ab1
ms.openlocfilehash: 1386d0e8fadddab5cd15818cb616bf331262e654
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43872490"
---
# <a name="learning-by-walkthroughs"></a>Lernen durch exemplarische Vorgehensweisen
Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] -Dokumentation stellt mehrere exemplarische Vorgehensweisen bereit. Dieser Abschnitt behandelt allgemeine Aspekte der exemplarischen Vorgehensweisen (einschließlich Fehlerbehebung) und bietet Links zu Vorgehensweisen für Einsteiger, die mehr über [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erfahren möchten.  
  
> [!NOTE]
>  Die exemplarischen Vorgehensweisen in diesem Abschnitt zu den ersten Schritten machen Sie mit dem grundlegenden Code vertraut, der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Technologie unterstützt. In der Praxis verwenden Sie in der Regel [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] und Windows Forms-Projekte, um Ihre [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendungen zu implementieren. Die [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]-Dokumentation stellt Beispiele und exemplarische Vorgehensweisen für diesen Zweck bereit.  
  
## <a name="getting-started-walkthroughs"></a>Exemplarische Vorgehensweisen zu den ersten Schritten  
 In diesem Abschnitt sind mehrere exemplarische Vorgehensweisen verfügbar. Diese exemplarischen Vorgehensweisen basieren auf der Beispieldatenbank Northwind und präsentieren [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Funktionen umfassend und mit minimaler Komplexität.  
  
 Ein typischer Ansatz lautet wie folgt:  
  
|Ziel|Visual Basic|C#|  
|---------------|------------------|---------|  
|Erstellen einer Entitätsklasse und Ausführen einer einfachen Abfrage|[Exemplarische Vorgehensweise: Einfaches Objektmodell und Abfrage (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-visual-basic.md)|[Exemplarische Vorgehensweise: Einfaches Objektmodell und Abfrage (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-csharp.md)|  
|Hinzufügen einer zweiten Klasse und Ausführen einer komplexeren Abfrage<br /><br /> (Erfordert den Abschluss der vorherigen exemplarischen Vorgehensweise.)|[Exemplarische Vorgehensweise: Beziehungsübergreifendes Abfragen (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md)|[Exemplarische Vorgehensweise: Beziehungsübergreifendes Abfragen (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-csharp.md)|  
|Hinzufügen, Ändern und Löschen von Elementen in der Datenbank|[Exemplarische Vorgehensweise: Bearbeiten von Daten (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-visual-basic.md)|[Exemplarische Vorgehensweise: Bearbeiten von Daten (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-csharp.md)|  
|Verwenden von gespeicherten Prozeduren|[Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)|[Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)|  
  
## <a name="general"></a>Allgemein  
 Die folgenden Informationen betreffen diese exemplarischen Vorgehensweisen im Allgemeinen:  
  
-   Umgebung: Jede [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] exemplarischen Vorgehensweise wird Visual Studio verwendet, als die integrierte Entwicklungsumgebung (IDE).  
  
-   SQL-Engines: Diese exemplarischen Vorgehensweisen werden für die Implementierung mit SQL Server Express geschrieben. Wenn Sie nicht über SQL Server Express verfügen, können Sie diese Lösung kostenlos herunterladen. Weitere Informationen finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
    > [!NOTE]
    >  Exemplarische Vorgehensweisen für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwenden einen Dateinamen als Verbindungszeichenfolge. Einfach einen Dateinamen anzugeben ist eine Annehmlichkeit, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für SQL Server Express-Benutzer bereitstellt. Achten Sie stets auf Sicherheitsprobleme. Weitere Informationen finden Sie unter [Sicherheit in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md).  
  
-   [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Exemplarische Vorgehensweisen erfordern in der Regel die Beispieldatenbank Northwind. Weitere Informationen finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
-   Die angezeigten Dialogfelder und Menübefehle, die Sie in den exemplarischen Vorgehensweisen finden Sie möglicherweise je nach den aktiven Einstellungen oder Visual Studio-Edition in der Hilfe beschriebenen unterscheiden. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
-   Für exemplarische Vorgehensweisen, die sich auf Szenarien mit mehreren Ebenen beziehen, muss sich ein Server auf einem Computer befinden, der sich vom Entwicklungscomputer unterscheidet. Außerdem müssen Sie über die entsprechenden Zugriffsrechte für den Server verfügen.  
  
-   Der Name der Klasse, die in der Regel für die Orders-Tabelle in der Beispieldatenbank Northwind steht, lautet `[Order]`. Das escaping ist erforderlich, da `Order` ist ein Schlüsselwort in Visual Basic.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Laufzeitfehler können auftreten, da Sie nicht über ausreichende Berechtigungen für den Zugriff auf die Datenbanken verfügen, die in diesen exemplarischen Vorgehensweisen verwendet werden. Die folgenden Schritte unterstützen Sie bei der Behebung der gängigsten Probleme.  
  
### <a name="log-on-issues"></a>Probleme mit der Anmeldung  
 Möglicherweise versucht Ihre Anwendung, über eine nicht akzeptierte Anmeldung auf die Datenbank zuzugreifen.  
  
##### <a name="to-verify-or-change-the-database-log-on"></a>So prüfen oder ändern Sie die Datenbankanmeldung  
  
1.  Klicken Sie auf der Windows **starten** , zeigen Sie auf **Programme**, **Microsoft SQL Server 2005**, zeigen Sie auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.  
  
2.  Klicken Sie im linken Bereich die **SQL Server-Konfigurations-Manager**, klicken Sie auf **SQL Server 2005 Services**.  
  
3.  Klicken Sie im rechten Bereich mit der Maustaste **SQL Server (SQLEXPRESS)**, und klicken Sie dann auf **Eigenschaften**.  
  
4.  Klicken Sie auf die **anmelden** Registerkarte, und überprüfen Sie, wie Sie möchten melden Sie sich an den Server.  
  
     In den meisten Fällen **Lokales System** funktioniert.  
  
     Wenn Sie eine Änderung vornehmen, klicken Sie auf **Neustart** den Dienst neu starten.  
  
### <a name="protocols"></a>Protokolle  
 Unter Umständen wurden die Protokolle für den Anwendungszugriff auf die Datenbank nicht ordnungsgemäß festgelegt. Z. B. die **Named Pipes** Protokoll, das für die exemplarischen Vorgehensweisen in erforderlich ist [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], ist nicht standardmäßig aktiviert.  
  
##### <a name="to-enable-the-named-pipes-protocol"></a>So aktivieren Sie das Named Pipes-Protokoll  
  
1.  Im linken Bereich die **SQL Server-Konfigurations-Manager**, erweitern Sie **SQL Server 2005-Netzwerkkonfiguration**, und klicken Sie dann auf **Protokolle für SQLEXPRESS**.  
  
2.  Stellen Sie im rechten Bereich sicher, dass die **Named Pipes** -Protokoll aktiviert ist. Wenn sie nicht der Fall ist, mit der rechten Maustaste **Namenspipes** , und klicken Sie dann auf **aktivieren**.  
  
     Sie müssen den Dienst beenden und neu starten. Führen Sie die Schritte im nächsten Block aus.  
  
### <a name="stopping-and-restarting-the-service"></a>Beenden und Neustarten des Diensts  
 Sie müssen Dienste beenden und neu starten, damit die Änderungen wirksam werden.  
  
##### <a name="to-stop-and-restart-the-service"></a>So beenden Sie den Dienst und starten ihn neu  
  
1.  Klicken Sie im linken Bereich die **SQL Server-Konfigurations-Manager**, klicken Sie auf **SQL Server 2005 Services**.  
  
2.  Klicken Sie im rechten Bereich mit der Maustaste **SQL Server (SQLEXPRESS)**, und klicken Sie dann auf **beenden**.  
  
3.  Mit der rechten Maustaste **SQL Server (SQLEXPRESS)**, und klicken Sie dann auf **Neustart**.  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
