---
title: Typische Schritte bei der Verwendung von LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
ms.openlocfilehash: 26b88e4d45365bbaac986ce8751e1d3b5383909b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946996"
---
# <a name="typical-steps-for-using-linq-to-sql"></a>Typische Schritte bei der Verwendung von LINQ to SQL
Zur Implementierung einer [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendung führen Sie die weiter unten beschriebenen Schritte aus. Beachten Sie, dass viele Schritte optional sind. Es ist gut möglich, dass Sie das Objektmodell in seinem Standardzustand verwenden können.  
  
 Verwenden Sie für einen schnellen Start die objektrelationaler Designer, um das Objektmodell zu erstellen und mit dem Codieren Ihrer Abfragen zu beginnen.  
  
## <a name="creating-the-object-model"></a>Erstellen des Objektmodells  
 Der erste Schritt besteht in der Erstellung eines Objektmodells aus den Metadaten einer vorhandenen relationalen Datenbank. Das Objektmodell stellt die Datenbank nach der Programmiersprache des Entwicklers dar. Weitere Informationen finden Sie [unter LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
### <a name="1-select-a-tool-to-create-the-model"></a>1. Wählen Sie ein Tool aus, um das Modell zu erstellen.  
 Für die Erstellung des Modells stehen drei Tools zur Verfügung.  
  
- Der objektrelationaler Designer  
  
     Dieser Designer stellt eine umfangreiche Benutzeroberfläche zum Erstellen eines Objektmodells aus einer vorhandenen Datenbank bereit. Dieses Tool ist Teil der Visual Studio-IDE und eignet sich am besten für kleine oder mittlere Datenbanken.  
  
- Das SQLMetal-Tool zur Codeerstellung  
  
     Dieses Befehlszeilen-Hilfsprogramm bietet eine etwas andere Gruppe von Optionen aus dem O/R-Designer. Dieses Tool eignet sich vor allem für die Modellierung großer Datenbanken. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
- Ein Code-Editor  
  
     Sie können eigenen Code schreiben, indem Sie entweder den Visual Studio Code-Editor oder einen anderen Editor verwenden. Diese Vorgehensweise wird nicht empfohlen, da Sie fehleranfällig sein kann, wenn Sie über eine vorhandene Datenbank verfügen und entweder den O/R-Designer oder das SQLMetal-Tool verwenden können. Der Code-Editor kann sich jedoch beim Verfeinern und Ändern von bereits erzeugtem Code als nützlich erweisen. Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)-Editor.  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a>2. Wählen Sie die Art von Code aus, die Sie erzeugen möchten.  
  
- Ein C# oder Visual Basic Quell Code Datei für die Attribut basierte Zuordnung.  
  
     Dann fügen Sie diese Codedatei in das Visual Studio-Projekt ein. Weitere Informationen finden Sie unter [Attribut basierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
- Eine XML-Datei für externe Zuordnung.  
  
     Sie können bei diesem Ansatz die Zuordnungsmetadaten vom Anwendungscode fernhalten. Weitere Informationen finden Sie unter [externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
    > [!NOTE]
    > Der O/R-Designer unterstützt die Generierung externer Mapping-Dateien nicht. Sie müssen das SQLMetal-Tool verwenden, um diese Funktion zu implementieren.  
  
- Eine DBML-Datei, die Sie vor dem Erzeugen einer abschließenden Codedatei ändern können.  
  
     Dies ist eine erweiterte Funktion.  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a>3. Verfeinern Sie die Codedatei, um die Anforderungen der Anwendung zu reflektieren.  
 Zu diesem Zweck können Sie entweder den O/R-Designer oder den Code-Editor verwenden.  
  
## <a name="using-the-object-model"></a>Verwenden des Objektmodells.  
 Die folgende Abbildung zeigt die Beziehung zwischen dem Entwickler und den Daten in einem Szenario mit zwei Ebenen. Weitere Szenarios finden Sie unter [N-Tier-und Remote Anwendungen mit LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md).  
  
 ![Screenshot, der das LINQ-Objektmodell zeigt.](./media/the-linq-to-sql-object-model/linq-object-model-two-tier.png)  
  
 Mit dem gewählten Objektmodell beschreiben Sie Informationsanforderungen und bearbeiten Daten innerhalb des Modells. Bei Ihrem Objektmodell geht es um Objekte und Eigenschaften, nicht um die Zeilen und Spalten der Datenbank. Sie beschäftigen sich nicht direkt mit der Datenbank.  
  
 Wenn Sie anweisen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , eine Abfrage auszuführen, die Sie `SubmitChanges()` für die von Ihnen bearbeiteten Daten beschrieben oder aufgerufen haben [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , kommuniziert mit der Datenbank in der Sprache der Datenbank.  
  
 Es folgen die typischen Schritte zum Verwenden des von Ihnen erstellen Objektmodells.  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a>1. Erstellen Sie Abfragen, um Informationen aus der Datenbank abzurufen.  
 Weitere Informationen finden Sie unter [Abfrage Konzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md) und [Abfrage Beispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md).  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a>2. Überschreiben Sie Standardverhalten für das Einfügen, Aktualisieren und Löschen.  
 Dieser Schritt ist optional. Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update-und DELETE-Vorgängen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a>3. Legen Sie entsprechende Optionen fest, um Parallelitätskonflikte zu erkennen und zu melden.  
 Sie können Ihr Modell im Standardzustand belassen, um Parallelitätskonflikte zu beheben. Sie können das Modell auch ändern, um es an Ihre Zwecke anzupassen. Weitere Informationen finden Sie unter [Vorgehensweise: Geben Sie an, welche Member auf Parallelitäts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) Konflikte [getestet werden und wie Sie Folgendes ausführen: Geben Sie an, wann Parallelitäts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md)Ausnahmen ausgelöst werden.  
  
### <a name="4-establish-an-inheritance-hierarchy"></a>4. Richten Sie eine Vererbungshierarchie ein.  
 Dieser Schritt ist optional. Weitere Informationen finden Sie [unter Vererbungs Unterstützung](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md).  
  
### <a name="5-provide-an-appropriate-user-interface"></a>5. Stellen Sie eine entsprechende Benutzeroberfläche bereit.  
 Dieser Schritt ist optional und hängt davon ab, wie die Anwendung verwendet wird.  
  
### <a name="6-debug-and-test-your-application"></a>6. Debuggen und testen Sie die Anwendung.  
 Weitere Informationen finden Sie [unter Debuggingunterstützung](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
- [Erstellen des Objektmodells](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [Gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
