---
title: Lernen durch exemplarische Vorgehensweisen
ms.date: 03/30/2017
ms.assetid: a8ae2965-6a49-4155-89b0-7fab2c488ab1
ms.openlocfilehash: f3d313fd50108420b631cff783708191f97a8b04
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158239"
---
# <a name="learning-by-walkthroughs"></a>Lernen durch exemplarische Vorgehensweisen

Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Dokumentation enthält mehrere exemplarische Vorgehensweisen. Dieser Abschnitt behandelt allgemeine Aspekte der exemplarischen Vorgehensweisen (einschließlich Fehlerbehebung) und bietet Links zu Vorgehensweisen für Einsteiger, die mehr über [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erfahren möchten.  
  
> [!NOTE]
> Die exemplarischen Vorgehensweisen in diesem Abschnitt zu den ersten Schritten machen Sie mit dem grundlegenden Code vertraut, der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Technologie unterstützt. In der Praxis verwenden Sie in der Regel die Projekte objektrelationaler Designer und Windows Forms, um Ihre [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Anwendungen zu implementieren. Die O/R-Designer-Dokumentation enthält Beispiele und Exemplarische Vorgehensweisen zu diesem Zweck.  
  
## <a name="getting-started-walkthroughs"></a>Exemplarische Vorgehensweisen zu den ersten Schritten  

 In diesem Abschnitt sind mehrere exemplarische Vorgehensweisen verfügbar. Diese exemplarischen Vorgehensweisen basieren auf der Beispieldatenbank Northwind und präsentieren [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Funktionen umfassend und mit minimaler Komplexität.  
  
 Ein typischer Ansatz lautet wie folgt:  
  
|Ziel|Visual Basic|C#|  
|---------------|------------------|---------|  
|Erstellen einer Entitätsklasse und Ausführen einer einfachen Abfrage|[Exemplarische Vorgehensweise: Einfaches Objektmodell und Abfrage (Visual Basic)](walkthrough-simple-object-model-and-query-visual-basic.md)|[Exemplarische Vorgehensweise: Einfaches Objektmodell und Abfrage (C#)](walkthrough-simple-object-model-and-query-csharp.md)|  
|Hinzufügen einer zweiten Klasse und Ausführen einer komplexeren Abfrage<br /><br /> (Erfordert den Abschluss der vorherigen exemplarischen Vorgehensweise.)|[Exemplarische Vorgehensweise: Beziehungsübergreifendes Abfragen (Visual Basic)](walkthrough-querying-across-relationships-visual-basic.md)|[Exemplarische Vorgehensweise: Beziehungsübergreifendes Abfragen (C#)](walkthrough-querying-across-relationships-csharp.md)|  
|Hinzufügen, Ändern und Löschen von Elementen in der Datenbank|[Exemplarische Vorgehensweise: Bearbeiten von Daten (Visual Basic)](walkthrough-manipulating-data-visual-basic.md)|[Exemplarische Vorgehensweise: Bearbeiten von Daten (C#)](walkthrough-manipulating-data-csharp.md)|  
|Verwenden von gespeicherten Prozeduren|[Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (Visual Basic)](walkthrough-using-only-stored-procedures-visual-basic.md)|[Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (C#)](walkthrough-using-only-stored-procedures-csharp.md)|  
  
## <a name="general"></a>Allgemein  

 Die folgenden Informationen betreffen diese exemplarischen Vorgehensweisen im Allgemeinen:  
  
- Umgebung: in jeder exemplarischen Vorgehens [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Weise wird Visual Studio als integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) verwendet.  
  
- SQL-Engines: Diese exemplarischen Vorgehensweisen werden für die Implementierung mit SQL Server Express geschrieben. Wenn Sie nicht über SQL Server Express verfügen, können Sie diese Lösung kostenlos herunterladen. Weitere Informationen finden Sie unter [Herunterladen von Beispiel Datenbanken](downloading-sample-databases.md).  
  
    > [!NOTE]
    > Exemplarische Vorgehensweisen für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwenden einen Dateinamen als Verbindungszeichenfolge. Einfach einen Dateinamen anzugeben ist eine Annehmlichkeit, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für SQL Server Express-Benutzer bereitstellt. Achten Sie stets auf Sicherheitsprobleme. Weitere Informationen finden Sie unter [Security in LINQ to SQL](security-in-linq-to-sql.md).  
  
- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Exemplarische Vorgehensweisen erfordern in der Regel die Beispieldatenbank Northwind. Weitere Informationen finden Sie unter [Herunterladen von Beispiel Datenbanken](downloading-sample-databases.md).  
  
- Die Dialogfelder und Menübefehle, die in exemplarischen Vorgehensweisen angezeigt werden, können sich von den in der Hilfe beschriebenen unterscheiden, abhängig von den aktiven Einstellungen oder der Visual Studio-Edition. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
- Für exemplarische Vorgehensweisen, die sich auf Szenarien mit mehreren Ebenen beziehen, muss sich ein Server auf einem Computer befinden, der sich vom Entwicklungscomputer unterscheidet. Außerdem müssen Sie über die entsprechenden Zugriffsrechte für den Server verfügen.  
  
- Der Name der Klasse, die in der Regel für die Orders-Tabelle in der Beispieldatenbank Northwind steht, lautet `[Order]`. Der Escapezeichen ist erforderlich, da `Order` ein Schlüsselwort in Visual Basic ist.  
  
## <a name="troubleshooting"></a>Problembehandlung  

 Laufzeitfehler können auftreten, da Sie nicht über ausreichende Berechtigungen für den Zugriff auf die Datenbanken verfügen, die in diesen exemplarischen Vorgehensweisen verwendet werden. Die folgenden Schritte unterstützen Sie bei der Behebung der gängigsten Probleme.  
  
### <a name="log-on-issues"></a>Probleme mit der Anmeldung  

 Möglicherweise versucht Ihre Anwendung, über eine nicht akzeptierte Anmeldung auf die Datenbank zuzugreifen.  
  
##### <a name="to-verify-or-change-the-database-log-on"></a>So prüfen oder ändern Sie die Datenbankanmeldung  
  
1. Zeigen Sie im Windows- **Startmenü** auf **Alle Programme**, **Microsoft SQL Server 2005**, zeigen Sie auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.  
  
2. Klicken Sie im linken Bereich des **SQL Server-Konfigurations-Manager**auf **SQL Server 2005-Dienste**.  
  
3. Klicken Sie im rechten Bereich mit der rechten Maustaste auf **SQL Server (SQLExpress)**, und klicken Sie dann auf **Eigenschaften**.  
  
4. Klicken Sie auf die Registerkarte **Anmelden** , und überprüfen Sie, wie Sie versuchen, sich beim Server anzumelden.  
  
     In den meisten Fällen funktioniert das **lokale System** .  
  
     Wenn Sie eine Änderung vornehmen, klicken Sie auf **neu starten** , um den Dienst neu zu starten.  
  
### <a name="protocols"></a>Protokolle  

 Unter Umständen wurden die Protokolle für den Anwendungszugriff auf die Datenbank nicht ordnungsgemäß festgelegt. Beispielsweise ist das **Named Pipes** -Protokoll, das für Exemplarische Vorgehensweisen in erforderlich ist, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht standardmäßig aktiviert.  
  
##### <a name="to-enable-the-named-pipes-protocol"></a>So aktivieren Sie das Named Pipes-Protokoll  
  
1. Erweitern Sie im linken Bereich des **SQL Server-Konfigurations-Manager**den Eintrag **SQL Server 2005-Netzwerkkonfiguration**, und klicken Sie dann auf **Protokolle für SQLExpress**.  
  
2. Stellen Sie im rechten Bereich sicher, dass das **Named Pipes** -Protokoll aktiviert ist. Wenn dies nicht der Fall ist, klicken Sie mit der rechten Maustaste auf **namens Pipes** und dann auf **aktivieren**.  
  
     Sie müssen den Dienst beenden und neu starten. Führen Sie die Schritte im nächsten Block aus.  
  
### <a name="stopping-and-restarting-the-service"></a>Beenden und Neustarten des Diensts  

 Sie müssen Dienste beenden und neu starten, damit die Änderungen wirksam werden.  
  
##### <a name="to-stop-and-restart-the-service"></a>So beenden Sie den Dienst und starten ihn neu  
  
1. Klicken Sie im linken Bereich des **SQL Server-Konfigurations-Manager**auf **SQL Server 2005-Dienste**.  
  
2. Klicken Sie im rechten Bereich mit der rechten Maustaste auf **SQL Server (SQLExpress)**, und klicken Sie dann auf " **Abbrechen**".  
  
3. Klicken Sie mit der rechten Maustaste auf **SQL Server (SQLExpress)**, und klicken Sie dann auf **neu starten**.  
  
## <a name="see-also"></a>Weitere Informationen

- [Erste Schritte](getting-started.md)
