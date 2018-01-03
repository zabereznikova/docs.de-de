---
title: Typische Schritte bei der Verwendung von LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ba49a4394d2a52b199edab88b977d2322bff945f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="typical-steps-for-using-linq-to-sql"></a>Typische Schritte bei der Verwendung von LINQ to SQL
Zur Implementierung einer [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendung führen Sie die weiter unten beschriebenen Schritte aus. Beachten Sie, dass viele Schritte optional sind. Es ist gut möglich, dass Sie das Objektmodell in seinem Standardzustand verwenden können.  
  
 Verwenden Sie für einen schnellen Einstieg [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] zur Erstellung des Objektmodells, und beginnen Sie dann mit dem Codieren Ihrer Abfragen.  
  
## <a name="creating-the-object-model"></a>Erstellen des Objektmodells  
 Der erste Schritt besteht in der Erstellung eines Objektmodells aus den Metadaten einer vorhandenen relationalen Datenbank. Das Objektmodell stellt die Datenbank nach der Programmiersprache des Entwicklers dar. Weitere Informationen finden Sie unter [das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
### <a name="1-select-a-tool-to-create-the-model"></a>1. Wählen Sie ein Tool aus, um das Modell zu erstellen.  
 Für die Erstellung des Modells stehen drei Tools zur Verfügung.  
  
-   Der [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]  
  
     Dieser Designer stellt eine umfangreiche Benutzeroberfläche zum Erstellen eines Objektmodells aus einer vorhandenen Datenbank bereit. Dieses Tool ist Bestandteil der [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]-IDE und eignet sich am besten für kleine oder mittelgroße Datenbanken.  
  
-   Das SQLMetal-Tool zur Codeerstellung  
  
     Dieses Befehlszeilenhilfsprogramm stellt einen Optionssatz bereit, der leicht von [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] abweicht. Dieses Tool eignet sich vor allem für die Modellierung großer Datenbanken. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
-   Ein Code-Editor  
  
     Sie können Ihren eigenen Code schreiben, indem Sie entweder den [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]-Code-Editor oder einen anderen Editor verwenden. Dieser Ansatz wird nicht empfohlen, da hierbei Fehler auftreten können. Wenn Sie über eine Datenbank verfügen, verwenden Sie entweder [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] oder das SQLMetal-Tool . Der Code-Editor kann sich jedoch beim Verfeinern und Ändern von bereits erzeugtem Code als nützlich erweisen. Weitere Informationen finden Sie unter [wie: Anpassen von Entitätsklassen mithilfe des Code-Editors](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md).  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a>2. Wählen Sie die Art von Code aus, die Sie erzeugen möchten.  
  
-   Eine C#-Quellcodedatei oder eine [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]-Quellcodedatei für attributbasierte Zuordnung.  
  
     Sie schließen dann diese Codedatei ins [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]-Projekt ein. Weitere Informationen finden Sie unter [attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
-   Eine XML-Datei für externe Zuordnung.  
  
     Sie können bei diesem Ansatz die Zuordnungsmetadaten vom Anwendungscode fernhalten. Weitere Informationen finden Sie unter [externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
    > [!NOTE]
    >  Der [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] unterstützt die Erzeugung externer Zuordnungsdateien nicht. Sie müssen das SQLMetal-Tool verwenden, um diese Funktion zu implementieren.  
  
-   Eine DBML-Datei, die Sie vor dem Erzeugen einer abschließenden Codedatei ändern können.  
  
     Dies ist eine erweiterte Funktion.  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a>3. Verfeinern Sie die Codedatei, um die Anforderungen der Anwendung zu reflektieren.  
 Für diesen Zweck können Sie entweder den [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] oder den Code-Editor verwenden.  
  
## <a name="using-the-object-model"></a>Verwenden des Objektmodells.  
 Die folgende Abbildung zeigt die Beziehung zwischen dem Entwickler und den Daten in einem Szenario mit zwei Ebenen. Weitere Szenarien finden Sie unter [N-schichtige und Remoteanwendungen mit LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md).  
  
 ![DLinqObjectModel](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinqobjectmodel.png "DLinqObjectModel")  
  
 Mit dem gewählten Objektmodell beschreiben Sie Informationsanforderungen und bearbeiten Daten innerhalb des Modells. Bei Ihrem Objektmodell geht es um Objekte und Eigenschaften, nicht um die Zeilen und Spalten der Datenbank. Sie beschäftigen sich nicht direkt mit der Datenbank.  
  
 Wenn Sie festlegen, dass [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] entweder führen Sie eine Abfrage, die von Ihnen beschriebene oder einen Aufruf `SubmitChanges()` für Daten, die Sie bearbeitet haben, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] kommuniziert mit der Datenbank in der Sprache der Datenbank.  
  
 Es folgen die typischen Schritte zum Verwenden des von Ihnen erstellen Objektmodells.  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a>1. Erstellen Sie Abfragen, um Informationen aus der Datenbank abzurufen.  
 Weitere Informationen finden Sie unter [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md) und [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md).  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a>2. Überschreiben Sie Standardverhalten für das Einfügen, Aktualisieren und Löschen.  
 Dieser Schritt ist optional. Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a>3. Legen Sie entsprechende Optionen fest, um Parallelitätskonflikte zu erkennen und zu melden.  
 Sie können Ihr Modell im Standardzustand belassen, um Parallelitätskonflikte zu beheben. Sie können das Modell auch ändern, um es an Ihre Zwecke anzupassen. Weitere Informationen finden Sie unter [Vorgehensweise: die Elemente angeben Parallelitätskonflikte getestet werden](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) und [wie: Geben Sie bei der Parallelitätsausnahmen ausgelöst werden](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md).  
  
### <a name="4-establish-an-inheritance-hierarchy"></a>4. Richten Sie eine Vererbungshierarchie ein.  
 Dieser Schritt ist optional. Weitere Informationen finden Sie unter [Unterstützung von Vererbung](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md).  
  
### <a name="5-provide-an-appropriate-user-interface"></a>5. Stellen Sie eine entsprechende Benutzeroberfläche bereit.  
 Dieser Schritt ist optional und hängt davon ab, wie die Anwendung verwendet wird.  
  
### <a name="6-debug-and-test-your-application"></a>6. Debuggen und testen Sie die Anwendung.  
 Weitere Informationen finden Sie unter [Debugunterstützung](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 [Erstellen des Objektmodells](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [Gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
