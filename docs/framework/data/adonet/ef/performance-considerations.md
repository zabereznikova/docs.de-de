---
title: Überlegungen zur Leistung (Entity Framework)
description: Informieren Sie sich über die Leistungsmerkmale des ADO.NET-Entity Framework und Überlegungen, die zur Verbesserung der Leistung von Entity Framework-Anwendungen beitragen.
ms.date: 03/30/2017
ms.assetid: 61913f3b-4f42-4d9b-810f-2a13c2388a4a
ms.openlocfilehash: edf82e4db3e72fab1555eea9bfcd34cd34ddbba7
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286765"
---
# <a name="performance-considerations-entity-framework"></a>Überlegungen zur Leistung (Entity Framework)
In diesem Thema werden Leistungsmerkmale des ADO.NET Entity Framework beschrieben. Außerdem sind einige Vorschläge enthalten, die Sie zur Verbesserung der Leistung von Entity Framework-Anwendungen verwenden können.  
  
## <a name="stages-of-query-execution"></a>Phasen der Abfrageausführung  
 Zum besseren Verständnis der Abfrageleistung im Entity Framework ist es hilfreich zu verstehen, welche Vorgänge ablaufen, wenn eine Abfrage für ein konzeptionelles Modell ausgeführt wird und dabei Daten als Objekte zurückgegeben werden. Die folgende Tabelle beschreibt diese Reihe von Vorgängen.  
  
|Vorgang|Relative Kosten|Häufigkeit|Kommentare|  
|---------------|-------------------|---------------|--------------|  
|Laden von Metadaten|Moderat|Einmal pro Anwendungsdomäne.|Von Entity Framework verwendete Modell- und Zuordnungsmetadaten werden in eine <xref:System.Data.Metadata.Edm.MetadataWorkspace> geladen. Diese Metadaten werden global zwischengespeichert und stehen für weitere Instanzen von <xref:System.Data.Objects.ObjectContext> in der gleichen Anwendungsdomäne zur Verfügung.|  
|Öffnen der Datenbankverbindung|Mittel<sup>1</sup>|Nach Bedarf.|Da eine geöffnete Verbindung zur Datenbank eine wertvolle Ressource verbraucht, wird die-Entity Framework geöffnet und schließt die Datenbankverbindung nur nach Bedarf. Sie können die Verbindung auch explizit öffnen. Weitere Informationen finden Sie unter [Verwalten von Verbindungen und Transaktionen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100)).|  
|Generieren von Sichten|High|Einmal pro Anwendungsdomäne. (Kann zuvor generiert werden.)|Bevor von Entity Framework für ein konzeptionelles Modell eine Abfrage ausgeführt oder Änderungen an der Datenquelle gespeichert werden können, muss ein Satz lokaler Abfrageansichten für den Zugriff auf die Datenbank generiert werden. Aufgrund der hohen Kosten für die Generierung dieser Ansichten können Sie die Sichten zuvor generieren und dem Projekt zur Entwurfszeit hinzufügen. Weitere Informationen finden Sie unter Gewusst [wie: Vorgenerieren von Sichten, um die Abfrageleistung zu verbessern](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100)).|  
|Vorbereiten der Abfrage|Mittel<sup>2</sup>|Einmal für jede eindeutige Abfrage.|Schließt die Kosten für das Verfassen des Abfragebefehls, die Erstellung einer Befehlsstruktur auf Grundlage von Modell- und Zuordnungsmetadaten und die Definition der Form der zurückgegebenen Daten ein. Da jetzt sowohl Entity SQL-Abfragebefehle als auch LINQ-Abfragen zwischengespeichert werden, ist für spätere Ausführungen derselben Abfrage weniger Zeit erforderlich. Sie können weiterhin kompilierte LINQ-Abfragen verwenden, um diesen Aufwand in späteren Ausführungen zu reduzieren. Kompilierte Abfragen können effizienter als LINQ-Abfragen sein, die automatisch zwischengespeichert werden. Weitere Informationen finden Sie unter [kompilierte Abfragen (LINQ to Entities)](./language-reference/compiled-queries-linq-to-entities.md). Allgemeine Informationen zur LINQ-Abfrage Ausführung finden Sie unter [LINQ to Entities](./language-reference/linq-to-entities.md). **Hinweis:**  LINQ to Entities Abfragen, die den- `Enumerable.Contains` Operator auf Auflistungen im Arbeitsspeicher anwenden, werden nicht automatisch zwischengespeichert. Darüber hinaus ist das Parametrisieren von Auflistungen im Arbeitsspeicher in kompilierten LINQ-Abfragen nicht zulässig.|  
|Ausführen der Abfrage|Niedrig<sup>2</sup>|Einmal für jede Abfrage.|Die Kosten für das Ausführen des Befehls für die Datenquelle mithilfe des ADO.NET-Datenanbieters. Da von den meisten Datenquellen Abfragepläne zwischengespeichert werden, kann die gleiche Abfrage ggf. noch schneller ausgeführt werden.|  
|Laden und Überprüfen von Typen|Niedrig<sup>3</sup>|Einmal für jede <xref:System.Data.Objects.ObjectContext>-Instanz.|Typen werden geladen und gegen die Typen geprüft, die das konzeptionelle Modell definiert.|  
|Nachverfolgung|Niedrig<sup>3</sup>|Einmal für jedes Objekt, dass von einer Abfrage zurückgegeben wird. <sup>4</sup>|Verwendet eine Abfrage die <xref:System.Data.Objects.MergeOption.NoTracking>-Mergeoption, wird die Leistung in dieser Phase nicht beeinträchtigt.<br /><br /> Verwendet die Abfrage die <xref:System.Data.Objects.MergeOption.AppendOnly>-, <xref:System.Data.Objects.MergeOption.PreserveChanges>- oder <xref:System.Data.Objects.MergeOption.OverwriteChanges>-Mergeoption, werden Abfrageergebnisse in der <xref:System.Data.Objects.ObjectStateManager> nachverfolgt. Für jedes von der Abfrage zurückgegebene verfolgte Objekt wird ein <xref:System.Data.EntityKey> generiert, das für die Erstellung eines <xref:System.Data.Objects.ObjectStateEntry> im <xref:System.Data.Objects.ObjectStateManager> verwendet wird. Wenn ein <xref:System.Data.Objects.ObjectStateEntry> für den <xref:System.Data.EntityKey> vorhanden ist, wird das vorhandene Objekt zurückgegeben. Wir die <xref:System.Data.Objects.MergeOption.PreserveChanges>- oder <xref:System.Data.Objects.MergeOption.OverwriteChanges>-Option verwendet, wird das Objekt vor der Rückgabe aktualisiert.<br /><br /> Weitere Informationen finden Sie unter [Identitäts Auflösung, Zustands Verwaltung und Änderungsnachverfolgung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896269(v=vs.100)).|  
|Materialisieren der Objekte|Mittel<sup>3</sup>|Einmal für jedes Objekt, dass von einer Abfrage zurückgegeben wird. <sup>4</sup>|Der Prozess des Lesens des zurückgegebenen <xref:System.Data.Common.DbDataReader>-Objekts, des Erstellens von Objekten und des Festlegens von Eigenschaftswerten, die auf den Werten in jeder Instanz der <xref:System.Data.Common.DbDataRecord>-Klasse basieren. Ist das Objekt bereits im <xref:System.Data.Objects.ObjectContext> vorhanden und wird von der Abfrage die <xref:System.Data.Objects.MergeOption.AppendOnly>- oder <xref:System.Data.Objects.MergeOption.PreserveChanges>-Zusammenführungsoptionen verwendet, wird von dieser Phase die Leistung nicht beeinträchtigt. Weitere Informationen finden Sie unter [Identitäts Auflösung, Zustands Verwaltung und Änderungsnachverfolgung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896269(v=vs.100)).|  
  
 <sup>1</sup> wenn ein Datenquellen Anbieter das Verbindungspooling implementiert, werden die Kosten für das Öffnen einer Verbindung über den Pool verteilt. Der .NET-Anbieter für SQL Server unterstützt Verbindungspooling.  
  
 <sup>2</sup> die Kosten steigen mit erhöhter Abfrage Komplexität.  
  
 <sup>3</sup> Gesamtkosten steigen proportional zur Anzahl von Objekten, die von der Abfrage zurückgegeben werden.  
  
 <sup>4</sup> dieser mehr Aufwand ist für EntityClient-Abfragen nicht erforderlich, da EntityClient-Abfragen anstelle von-Objekten einen zurückgeben <xref:System.Data.EntityClient.EntityDataReader> . Weitere Informationen finden Sie unter [EntityClient-Anbieter für das Entity Framework](entityclient-provider-for-the-entity-framework.md).  
  
## <a name="additional-considerations"></a>Weitere Überlegungen  
 Die im Folgenden beschriebenen Vorgehensweisen wirken sich möglicherweise auf die Leistung von Entity Framework-Anwendungen aus.  
  
### <a name="query-execution"></a>Abfrageausführung  
 Da Abfragen ressourcenintensiv sein können, muss berücksichtigt werden, an welcher Stelle im Code und auf welchem Computer eine Abfrage ausgeführt wird.  
  
#### <a name="deferred-versus-immediate-execution"></a>Verzögerte und unmittelbare Ausführung  
 Bei der Erstellung einer <xref:System.Data.Objects.ObjectQuery%601>- oder einer LINQ-Abfrage wird die Abfrage möglicherweise nicht sofort ausgeführt. Die Abfrageausführung wird so lange verzögert, bis die Ergebnisse benötigt werden, z. B. während einer `foreach` (C#)-Enumeration, einer `For Each` (Visual Basic)-Enumeration oder wenn eine <xref:System.Collections.Generic.List%601>-Auflistung ausgefüllt werden soll. Die Abfrage wird ausgeführt, wenn Sie die <xref:System.Data.Objects.ObjectQuery%601.Execute%2A>-Methode für ein <xref:System.Data.Objects.ObjectQuery%601> aufrufen oder wenn Sie eine LINQ-Methode aufrufen, die eine Singleton-Abfrage zurückgibt, z. B. <xref:System.Linq.Enumerable.First%2A> oder <xref:System.Linq.Enumerable.Any%2A>. Weitere Informationen finden Sie unter [Objekt Abfragen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)) und [Abfrage Ausführung (LINQ to Entities)](./language-reference/query-execution.md).  
  
#### <a name="client-side-execution-of-linq-queries"></a>Clientseitige Ausführung von LINQ-Abfragen  
 Obwohl eine LINQ-Abfrage auf dem Computer ausgeführt wird, der die Datenquelle hostet, werden einige Teile der LINQ-Abfrage möglicherweise auf dem Clientcomputer ausgewertet. Weitere Informationen finden Sie im Abschnitt "Store Execution" der [Abfrage Ausführung (LINQ to Entities)](./language-reference/query-execution.md).  
  
### <a name="query-and-mapping-complexity"></a>Abfrage- und Zuordnungskomplexität  
 Die Komplexität einzelner Abfragen und der Zuordnung im Entitätsmodell wirkt sich entscheidend auf die Abfrageleistung aus.  
  
#### <a name="mapping-complexity"></a>Zuordnungskomplexität  
 Modelle, die komplexer als eine einfache 1:1-Zuordnung für Entitäten im konzeptionellen Modell und Tabellen im Speichermodell sind, generieren komplexere Befehle als Modelle mit 1:1-Zuordnung.  
  
#### <a name="query-complexity"></a>Abfragekomplexität  
 Abfragen, die eine große Anzahl von Joins für Befehle erfordern, die für die Datenquelle ausgeführt werden oder eine große Datenmenge zurückgeben, beeinträchtigen möglicherweise die Leistung auf die folgende Weise:  
  
- Scheinbar einfache Abfragen für ein konzeptionelles Modell führen möglicherweise zur Ausführung komplexerer Abfragen für die Datenquelle. Dies kann auftreten, da Entity Framework eine Abfrage für ein konzeptionelles Modell in eine entsprechende Abfrage für die Datenquelle übersetzt. Wenn ein einzelner Entitätssatz im konzeptionellen Modell mehr als einer Tabelle in der Datenquelle zugeordnet wird oder einer Jointabelle eine Beziehung zwischen Entitäten zugeordnet wird, sind für den Abfragebefehl für die Datenquellenabfrage möglicherweise Joins erforderlich.  
  
    > [!NOTE]
    > Verwenden Sie die <xref:System.Data.Objects.ObjectQuery.ToTraceString%2A>-Methode der <xref:System.Data.Objects.ObjectQuery%601>- oder <xref:System.Data.EntityClient.EntityCommand>-Klasse, um die Befehle anzuzeigen, die für die Datenquelle für eine angegebene Abfrage ausgeführt werden. Weitere Informationen finden Sie unter Gewusst [wie: Anzeigen der Speicher Befehle](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896348(v=vs.100)).  
  
- Geschachtelte Entity SQL-Abfragen erstellen möglicherweise Joins auf dem Server und geben eine große Anzahl von Zeilen zurück.  
  
     Im Folgenden sehen Sie ein Beispiel für eine geschachtelte Abfrage in einer Projektionsklausel:  
  
    ```sql  
    SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2
        FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1
        FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
    ```  
  
     Außerdem bewirken solche Abfragen, dass die Abfragepipeline eine einzelne Abfrage durch die Verdoppelung von Objekten in geschachtelten Abfragen generiert. Deswegen wird eine einzelne Spalte möglicherweise mehrmals dupliziert. In einigen Datenbanken, einschließlich SQL Server, kann hierdurch die TempDB-Tabelle stark vergrößert werden, wodurch die Serverleistung abnehmen kann. Bei der Ausführung geschachtelter Abfragen sollte also vorsichtig vorgegangen werden.  
  
- Alle Abfragen, die eine große Datenmenge zurückgeben, können einen Leistungsabfall verursachen, wenn vom Client Operationen ausgeführt werden, von denen Ressourcen in der Größenordnung des Resultsets verbraucht werden. In solchen Fällen sollten Sie erwägen, die von der Abfrage zurückgegebene Datenmenge zu beschränken. Weitere Informationen finden Sie unter Gewusst [wie: seitenweise durch Abfrageergebnisse](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)).  
  
 Alle automatisch vom Entity Framework generierten Befehle sind möglicherweise komplexer als ähnliche explizit von einem Datenbankentwickler geschriebenen Befehle. Wenn Sie explizite Kontrolle über die für die Datenquelle ausgeführten Befehle benötigen, erwägen Sie die Definition einer Zuordnung für eine Tabellenwertfunktion oder eine gespeicherte Prozedur.  
  
#### <a name="relationships"></a>Beziehungen  
 Für optimale Abfrageleistung müssen Beziehungen zwischen Entitäten als Zuordnungen im Entitätsmodell und als logische Beziehungen in der Datenquelle definiert werden.  
  
### <a name="query-paths"></a>Abfragepfade  
 Standardmäßig werden verknüpfte Objekte nicht zurückgegeben (obwohl dies für Objekte, die die Beziehungen selbst darstellen, zutrifft), wenn Sie einen <xref:System.Data.Objects.ObjectQuery%601> ausführen. Sie können auf eine von drei Arten verknüpfte Objekte laden:  
  
1. Legen Sie den Abfragepfad fest, bevor die <xref:System.Data.Objects.ObjectQuery%601>-Abfrage ausgeführt wird.  
  
2. Rufen Sie die `Load`-Methode für die Navigationseigenschaft auf, die das Objekt verfügbar macht.  
  
3. Legen Sie die <xref:System.Data.Objects.ObjectContextOptions.LazyLoadingEnabled%2A>-Option für das <xref:System.Data.Objects.ObjectContext>-Objekt auf `true` fest. Beachten Sie, dass dies automatisch erfolgt, wenn Sie Code auf Objektebene mit dem [Entity Data Model-Designer](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716685(v=vs.100))generieren. Weitere Informationen finden Sie unter [Übersicht über den generierten Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982041(v=vs.100)).  
  
 Denken Sie beim Auswählen der Option daran, dass zwischen der Anzahl der Abfragen der Datenbank und der in einer einzelnen Abfrage zurückgegebenen Datenmenge abgewogen werden sollte. Weitere Informationen finden Sie unter [Laden verwandter Objekte](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896272(v=vs.100)).  
  
#### <a name="using-query-paths"></a>Verwenden von Abfragepfaden  
 Abfragepfade definieren das Diagramm von Objekten, die von einer Abfrage zurückgegeben werden. Beim Definieren eines Abfragepfads ist nur eine einzige Abfrage der Datenbank erforderlich, um alle durch den Pfad definierten Objekte zurückzugeben. Durch die Verwendung von Abfragepfaden können aus scheinbar einfachen Objektabfragen komplexe Befehle werden, die in der Datenquelle ausgeführt werden. Der Grund hierfür ist, dass eine oder mehrere Joins erforderlich sind, um verbundene Objekte in einer einzelnen Abfrage zurückzugeben. Diese Komplexität nimmt bei Abfragen für ein komplexes Entitätsmodell (z. B. eine Entität mit Vererbung oder ein Pfad, der n:n-Beziehungen enthält) zu.  
  
> [!NOTE]
> Mit der <xref:System.Data.Objects.ObjectQuery.ToTraceString%2A>-Methode kann der von einer <xref:System.Data.Objects.ObjectQuery%601> generierte Befehl angezeigt werden. Weitere Informationen finden Sie unter Gewusst [wie: Anzeigen der Speicher Befehle](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896348(v=vs.100)).  
  
 Wenn ein Abfragepfad zu viele verbundene Objekte enthält oder die Objekte zu viele Zeilendaten enthalten, kann die Abfrage möglicherweise nicht von der Datenquelle abgeschlossen werden. Dies tritt auf, wenn die Abfrage temporäre Zwischenspeicherung erfordert, die die Kapazität der Datenquelle überschreitet. In diesem Fall kann die Komplexität der Datenquellenabfrage verringert werden, indem verbundene Objekte explizit geladen werden.  
  
#### <a name="explicitly-loading-related-objects"></a>Explizites Laden verbundener Objekte  
 Zum expliziten Laden verbundener Objekte muss die `Load`-Methode für eine Navigationseigenschaft aufgerufen werden, die eine <xref:System.Data.Objects.DataClasses.EntityCollection%601> oder <xref:System.Data.Objects.DataClasses.EntityReference%601> zurückgibt. Explizites Laden erfordert bei jedem Aufruf von `Load` einen Roundtrip zur Datenbank.  
  
> [!NOTE]
> Wenn Sie beim Durchlaufen einer Auflistung zurückgegebener Objekte `Load` aufrufen, z. B. wenn Sie die `foreach`-Anweisung (`For Each` in Visual Basic) verwenden, muss der datenquellenspezifische Anbieter mehrere aktive Resultsets für eine einzelne Verbindung unterstützen. Bei einer SQL Server-Datenbank muss in der Verbindungszeichenfolge des Anbieters der Wert `MultipleActiveResultSets = true` angegeben werden.  
  
 Sie können auch die <xref:System.Data.Objects.ObjectContext.LoadProperty%2A>-Methode verwenden, wenn die Entitäten nicht über die <xref:System.Data.Objects.DataClasses.EntityCollection%601>-Eigenschaft oder die <xref:System.Data.Objects.DataClasses.EntityReference%601>-Eigenschaft verfügen. Dies ist bei Verwendung von POCO-Entitäten nützlich.  
  
 Obwohl durch das explizite Laden von verwandten Objekten die Anzahl der Joins und die Menge von redundanten Daten reduziert wird, erfordert `Load` wiederholte Verbindungen zur Datenbank, was beim expliziten Laden einer großen Anzahl von Objekten kostenintensiv sein kann.  
  
### <a name="saving-changes"></a>Speichern von Änderungen  
 Wenn Sie die <xref:System.Data.Objects.ObjectContext.SaveChanges%2A>-Methode für einen <xref:System.Data.Objects.ObjectContext> aufrufen, wird für jedes hinzugefügte, aktualisierte oder gelöschte Objekt im Kontext jeweils ein eigener Befehl zum Erstellen, Aktualisieren oder Löschen generiert. Diese Befehle werden für die Datenquelle in einer einzelnen Transaktion ausgeführt. Wie bei Abfragen ist die Leistung von Vorgängen für die Erstellung, Aktualisierung und Löschung von der Komplexität der Zuordnung im konzeptionellen Modell abhängig.  
  
### <a name="distributed-transactions"></a>Verteilte Transaktionen  
 Operationen in einer expliziten Transaktion, die Ressourcen erfordern, die vom verteilten Transaktionskoordinator (DTC) verwaltet werden, sind viel teurer als eine ähnliche Operation, die DTC nicht erfordert. In den folgenden Situationen findet eine Höherstufung zum DTC statt:  
  
- Eine explizite Transaktion mit einem Vorgang für eine SQL Server 2000-Datenbank oder andere Datenquellen, die ständig explizite Transaktionen auf den DTC hochstufen.  
  
- Eine explizite Transaktion mit einem Vorgang für SQL Server 2005, wenn die Verbindung vom Entity Framework verwaltet wird. Dies liegt daran, dass SQL Server 2005 den DTC immer dann herauf stuft, wenn eine Verbindung geschlossen und innerhalb einer einzelnen Transaktion erneut geöffnet wird. Dies ist das Standardverhalten des Entity Framework. Beim SQL Server 2008 wird diese DTC-Höherstufung nicht durchgeführt. Öffnen und schließen Sie explizit die Verbindung innerhalb der Transaktion, um diese Höherstufung zu vermeiden, wenn Sie SQL Server 2005 verwenden. Weitere Informationen finden Sie unter [Verwalten von Verbindungen und Transaktionen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100)).  
  
 Eine explizite Transaktion wird verwendet, wenn eine oder mehrere Operationen in einer <xref:System.Transactions>-Transaktion ausgeführt werden. Weitere Informationen finden Sie unter [Verwalten von Verbindungen und Transaktionen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100)).  
  
## <a name="strategies-for-improving-performance"></a>Strategien zum Verbessern der Leistung  
 Sie können die Gesamtleistung von Abfragen in Entity Framework mit den folgenden Strategien verbessern.  
  
#### <a name="pre-generate-views"></a>Vorabgenerieren von Sichten  
 Führt eine Anwendung eine Abfrage zum ersten Mal aus, ist das Generieren von Sichten auf Grundlage eines Entitätsmodells kostenintensiv. Verwenden Sie das Hilfsprogramm EdmGen.exe, um Sichten als Visual Basic- oder C#-Codedatei vorzugenerieren, die dem Projekt während des Entwurfs hinzugefügt werden kann. Sie können auch mit dem Text Template Transformation Toolkit (Textvorlagentransformations-Toolkit) vorkompilierte Sichten generieren. Zur Wahrung der Konsistenz mit der aktuellen Version des angegebenen Entitätsmodells werden vorgenerierte Sichten zur Laufzeit überprüft. Weitere Informationen finden Sie unter Gewusst [wie: Vorgenerieren von Sichten, um die Abfrageleistung zu verbessern](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100)).
  
 Beim Arbeiten mit sehr umfangreichen Modellen ist Folgendes zu berücksichtigen:  
  
 Das .NET-Metadatenformat beschränkt die Anzahl der Zeichen in Benutzerzeichenfolgen in einer Binärdatei auf 16.777.215 (0xFFFFFF) Zeichen. Wenn Sie Ansichten für ein sehr großes Modell erzeugen und die Ansichts Datei diese Größenbeschränkung erreicht, erhalten Sie den "kein logischer Speicherplatz zum Erstellen von weiteren Benutzer Zeichenfolgen". Kompilierungsfehler. Diese Größenbeschränkung gilt für alle verwalteten Binärdateien. Weitere Informationen finden Sie im [Blog](https://docs.microsoft.com/archive/blogs/appfabriccat/solving-the-no-logical-space-left-to-create-more-user-strings-error-and-improving-performance-of-pre-generated-views-in-visual-studio-net4-entity-framework) , in dem veranschaulicht wird, wie der Fehler beim Arbeiten mit umfangreichen und komplexen Modellen vermieden wird.  
  
#### <a name="consider-using-the-notracking-merge-option-for-queries"></a>Verwenden der NoTracking-Mergeoption für Abfragen  
 Das Nachverfolgen von zurückgegebenen Objekten im Objektkontext bringt Kosten mit sich. Zur Ermittlung von Änderungen an Objekten und zur Gewährleistung, dass mehrere Anforderungen für die gleiche logische Entität die gleiche Objektinstanz zurückgeben, ist das Anfügen der Objekte an die <xref:System.Data.Objects.ObjectContext>-Instanz erforderlich. Wenn Sie nicht beabsichtigen, Objekte zu aktualisieren oder zu löschen, und keine Identitätsverwaltung erforderlich ist, sollten Sie die <xref:System.Data.Objects.MergeOption.NoTracking> Zusammenführungs Optionen beim Ausführen von Abfragen verwenden.  
  
#### <a name="return-the-correct-amount-of-data"></a>Zurückgeben der richtigen Datenmenge  
 In einigen Szenarien ist das Angeben eines Abfragepfads mithilfe der <xref:System.Data.Objects.ObjectQuery%601.Include%2A>-Methode viel schneller, da weniger Roundtrips zur Datenbank erforderlich sind. Allerdings sind in anderen Szenarien zusätzliche Roundtrips zur Datenbank zum Laden von verknüpften Objekten ggf. schneller, da die einfacheren Abfragen mit weniger Joins weniger redundante Daten liefern. Deswegen empfiehlt es sich, verschiedene Möglichkeiten zum Abrufen verknüpfter Objekte zu testen und so die leistungsfähigste Methode zu ermitteln. Weitere Informationen finden Sie unter [Laden verwandter Objekte](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896272(v=vs.100)).  
  
 Gliedern Sie die Abfrageergebnisse in überschaubare Gruppen, um zu vermeiden, dass zu viel Daten in einer einzelnen Abfrage zurückgegeben werden. Weitere Informationen finden Sie unter Gewusst [wie: seitenweise durch Abfrageergebnisse](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)).  
  
#### <a name="limit-the-scope-of-the-objectcontext"></a>Einschränken des Bereichs des ObjectContext  
 In den meisten Fällen sollten Sie eine <xref:System.Data.Objects.ObjectContext>-Instanz innerhalb einer `using`-Anweisung (`Using…End Using` in Visual Basic) erstellen. Dies kann die Leistung verbessern, da die dem Objektkontext zugeordneten Ressourcen automatisch freigegeben werden, wenn der Anweisungsblock vom Code beendet wird. Wenn Steuerelemente jedoch an vom Objektkontext verwaltete Objekte gebunden werden, sollte die <xref:System.Data.Objects.ObjectContext>-Instanz so lange beibehalten werden, bis die Bindung benötigt und manuell freigegeben wird. Weitere Informationen finden Sie unter [Verwalten von Verbindungen und Transaktionen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100)).  
  
#### <a name="consider-opening-the-database-connection-manually"></a>Manuelles Öffnen der Datenbankverbindung  
 Wenn Ihre Anwendung eine Reihe von Objekt Abfragen ausführt oder häufig aufruft, um Erstellungs- <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> , Aktualisierungs-und Löschvorgänge in der Datenquelle beizubehalten, muss der Entity Framework die Verbindung mit der Datenquelle fortlaufend öffnen und schließen. Erwägen Sie in diesem Fall, die Verbindung am Start dieser Operationen manuell zu öffnen und die Verbindung zu schließen bzw. freizugeben, wenn die Vorgänge abgeschlossen sind. Weitere Informationen finden Sie unter [Verwalten von Verbindungen und Transaktionen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100)).  
  
## <a name="performance-data"></a>Leistungsdaten  
 Einige Leistungsdaten für die Entity Framework werden in den folgenden Beiträgen im ADO.net- [Teamblog](https://docs.microsoft.com/archive/blogs/adonet/)veröffentlicht:  
  
- [Exploring the Performance of the ADO.NET Entity Framework - Part 1](https://docs.microsoft.com/archive/blogs/adonet/exploring-the-performance-of-the-ado-net-entity-framework-part-1)  
  
- [Exploring the Performance of the ADO.NET Entity Framework – Part 2](https://docs.microsoft.com/archive/blogs/adonet/exploring-the-performance-of-the-ado-net-entity-framework-part-2)  
  
- [ADO.NET Entity Framework-Leistungsvergleich](https://docs.microsoft.com/archive/blogs/adonet/ado-net-entity-framework-performance-comparison)  
  
## <a name="see-also"></a>Siehe auch

- [Überlegungen zur Entwicklung und Bereitstellung](development-and-deployment-considerations.md)
