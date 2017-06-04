---
title: "Lernen mit exemplarischen Vorgehensweisen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a8ae2965-6a49-4155-89b0-7fab2c488ab1
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Lernen mit exemplarischen Vorgehensweisen
Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Dokumentation stellt mehrere exemplarische Vorgehensweisen bereit.  Dieser Abschnitt behandelt allgemeine Aspekte der exemplarischen Vorgehensweisen \(einschließlich Fehlerbehebung\) und bietet Links zu Vorgehensweisen für Einsteiger, die mehr über [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erfahren möchten.  
  
> [!NOTE]
>  Die exemplarischen Vorgehensweisen in diesem Abschnitt zu den ersten Schritten machen Sie mit dem grundlegenden Code vertraut, der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Technologie unterstützt.  In der Praxis verwenden Sie in der Regel [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] und Windows Forms\-Projekte, um Ihre [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Anwendungen zu implementieren.  Die [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]\-Dokumentation stellt Beispiele und exemplarische Vorgehensweisen für diesen Zweck bereit.  
  
## Exemplarische Vorgehensweisen zu den ersten Schritten  
 In diesem Abschnitt sind mehrere exemplarische Vorgehensweisen verfügbar.  Diese exemplarischen Vorgehensweisen basieren auf der Beispieldatenbank Northwind und präsentieren [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Funktionen umfassend und mit minimaler Komplexität.  
  
 Ein typischer Ansatz lautet wie folgt:  
  
|Ziel|Visual Basic|C\#|  
|----------|------------------|---------|  
|Erstellen einer Entitätsklasse und Ausführen einer einfachen Abfrage|[Exemplarische Vorgehensweise: Einfaches Objektmodell und Abfrage \(Visual Basic\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-visual-basic.md)|[Exemplarische Vorgehensweise: Einfaches Objektmodell und Abfrage \(C\#\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-csharp.md)|  
|Hinzufügen einer zweiten Klasse und Ausführen einer komplexeren Abfrage<br /><br /> \(Erfordert den Abschluss der vorherigen exemplarischen Vorgehensweise.\)|[Exemplarische Vorgehensweise: Beziehungsübergreifende Abfragen \(Visual Basic\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md)|[Exemplarische Vorgehensweise: Beziehungsübergreifende Abfragen \(C\#\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-csharp.md)|  
|Hinzufügen, Ändern und Löschen von Elementen in der Datenbank|[Exemplarische Vorgehensweise: Bearbeiten von Daten \(Visual Basic\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-visual-basic.md)|[Exemplarische Vorgehensweise: Bearbeiten von Daten \(C\#\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-csharp.md)|  
|Verwenden von gespeicherten Prozeduren|[Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren \(Visual Basic\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)|[Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren \(C\#\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)|  
  
## Allgemein  
 Die folgenden Informationen betreffen diese exemplarischen Vorgehensweisen im Allgemeinen:  
  
-   Umgebung: Jede exemplarische Vorgehensweise in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwendet [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] als integrierte Entwicklungsumgebung \(IDE\).  
  
-   SQL\-Module: Diese exemplarischen Vorgehensweisen werden für die Implementierung mit SQL Server Express geschrieben.  Wenn Sie nicht über SQL Server Express verfügen, können Sie diese Lösung kostenlos herunterladen.  Weitere Informationen finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
    > [!NOTE]
    >  Exemplarische Vorgehensweisen für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwenden einen Dateinamen als Verbindungszeichenfolge.  Einfach einen Dateinamen anzugeben ist eine Annehmlichkeit, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für SQL Server Express\-Benutzer bereitstellt.  Achten Sie stets auf Sicherheitsprobleme.  Weitere Informationen finden Sie unter [Sicherheit in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md).  
  
-   Exemplarische Vorgehensweisen für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erfordern in der Regel die Beispieldatenbank Northwind.  Weitere Informationen finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
-   Die Dialogfelder und Befehle in exemplarischen Vorgehensweisen können von jenen in der Online\-Hilfe abweichen \(je nach Ihren aktiven Einstellungen oder der [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]\-Edition\).  Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren**, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
-   Für exemplarische Vorgehensweisen, die sich auf Szenarien mit mehreren Ebenen beziehen, muss sich ein Server auf einem Computer befinden, der sich vom Entwicklungscomputer unterscheidet. Außerdem müssen Sie über die entsprechenden Zugriffsrechte für den Server verfügen.  
  
-   Der Name der Klasse, die in der Regel für die Orders\-Tabelle in der Beispieldatenbank Northwind steht, lautet `[Order]`.  Das Escaping ist erforderlich, da `Order` ein Schlüsselwort in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] ist.  
  
## Problembehandlung  
 Laufzeitfehler können auftreten, da Sie nicht über ausreichende Berechtigungen für den Zugriff auf die Datenbanken verfügen, die in diesen exemplarischen Vorgehensweisen verwendet werden.  Die folgenden Schritte unterstützen Sie bei der Behebung der gängigsten Probleme.  
  
### Probleme mit der Anmeldung  
 Möglicherweise versucht Ihre Anwendung, über eine nicht akzeptierte Anmeldung auf die Datenbank zuzugreifen.  
  
##### So prüfen oder ändern Sie die Datenbankanmeldung  
  
1.  Zeigen Sie im Windows\-Menü **Start** auf **Programme**, **Microsoft SQL Server 2005**, **Konfigurations\-Tools**, und klicken Sie dann auf **SQL Server Configuration Manager**.  
  
2.  Klicken Sie im linken Bereich des **SQL Server\-Konfigurations\-Managers** auf **SQL Server 2005\-Dienste**.  
  
3.  Klicken Sie im rechten Bereich mit der rechten Maustaste auf **SQL Server \(SQLEXPRESS\)** und dann auf **Eigenschaften**.  
  
4.  Klicken Sie auf die Registerkarte **Log On**, und prüfen Sie, wie die Anmeldung am Server erfolgt.  
  
     In den meisten Fällen funktioniert die Einstellung **lokales System**.  
  
     Wenn Sie eine Änderung vornehmen, klicken Sie auf **Neustart**, um den Dienst neu zu starten.  
  
### Protokolle  
 Unter Umständen wurden die Protokolle für den Anwendungszugriff auf die Datenbank nicht ordnungsgemäß festgelegt.  Beispielsweise ist das **Named Pipes**\-Protokoll, das für exemplarische Vorgehensweisen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erforderlich ist, standardmäßig nicht aktiviert.  
  
##### So aktivieren Sie das Named Pipes\-Protokoll  
  
1.  Erweitern Sie im linken Bereich von **SQL Server Configuration Manager** den Eintrag **SQL Server 2005\-Netzwerkkonfiguration**, und klicken Sie dann auf **Protokolle für SQLEXPRESS**.  
  
2.  Stellen Sie im rechten Bereich sicher, dass das **Named Pipes**\-Protokoll aktiviert wird.  Ist dies nicht der Fall, klicken Sie mit der rechten Maustaste auf **Name Pipes**, und klicken Sie dann auf **Aktivieren**.  
  
     Sie müssen den Dienst beenden und neu starten.  Führen Sie die Schritte im nächsten Block aus.  
  
### Beenden und Neustarten des Diensts  
 Sie müssen Dienste beenden und neu starten, damit die Änderungen wirksam werden.  
  
##### So beenden Sie den Dienst und starten ihn neu  
  
1.  Klicken Sie im linken Bereich des **SQL Server\-Konfigurations\-Managers** auf **SQL Server 2005\-Dienste**.  
  
2.  Klicken Sie im rechten Bereich mit der rechten Maustaste auf **SQL Server \(SQLEXPRESS\)** und dann auf **Beenden**.  
  
3.  Klicken Sie mit der rechten Maustaste auf **SQL Server \(SQLEXPRESS\)**, und klicken Sie dann auf  **Neu starten**.  
  
## Siehe auch  
 [Erste Schritte](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)