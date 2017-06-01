---
title: "H&#228;ufig gestellte Fragen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 252ed666-0679-4eea-b71b-2f14117ef443
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# H&#228;ufig gestellte Fragen
In den folgenden Abschnitten werden einige allgemeine Probleme behandelt, die bei der Implementierung von [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] auftreten können.  
  
 Weitere Probleme werden in [Problembehandlung](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md) behandelt.  
  
## Es kann keine Verbindung hergestellt werden  
 F.  Es kann keine Verbindung mit meiner Datenbank hergestellt werden.  
  
 A.  Stellen Sie sicher, dass Ihre Verbindungszeichenfolge richtig ist und dass die [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)]\-Instanz ausgeführt wird.  Beachten Sie auch, dass für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] das Named Pipes\-Protokoll aktiviert sein muss.  Weitere Informationen finden Sie unter [Lernen mit exemplarischen Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).  
  
## Änderungen an der Datenbank sind nicht vorhanden  
 F.  Änderungen an den Daten in der Datenbank sind nicht mehr vorhanden, nachdem meine Anwendung erneut ausgeführt wurde.  
  
 A.  Stellen Sie sicher, dass Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen, um Ergebnisse in der Datenbank zu speichern.  
  
## Wie lange kann die Datenbankverbindung geöffnet bleiben?  
 F.  Wie lange bleibt meine Datenbankverbindung geöffnet?  
  
 A.  Eine Verbindung bleibt normalerweise geöffnet, bis Sie die Abfrageergebnisse verwenden.  Wenn Sie erwarten, dass die Verarbeitung sämtlicher Ergebnisse länger dauert und nichts dagegen spricht, die Ergebnisse zwischenzuspeichern, wenden Sie <xref:System.Linq.Enumerable.ToList%2A> auf die Abfrage an.  In gängigen Szenarien, in denen jedes Objekt nur einmal verarbeitet wird, ist das Streamingmodell sowohl in `DataReader` als auch in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die bevorzugte Lösung.  
  
 Die genauen Details der Verbindungsnutzung hängen von folgenden Faktoren ab:  
  
-   Verbindungsstatus, wenn <xref:System.Data.Linq.DataContext> mit einem Verbindungsobjekt erstellt wird.  
  
-   Verbindungszeichenfolgen\-Einstellungen \(z. B. Aktivieren von MARS \(Multiple Active Result Sets\)\).  Weitere Informationen finden Sie unter [MARS \(Multiple Active Result Sets\)](../../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md).  
  
## Ausführen von Updates ohne Abfrage  
 F.  Können Tabellendaten aktualisiert werden, ohne zuerst eine Datenbankabfrage auszuführen?  
  
 A.  Obwohl [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] keine mengenbasierten Updatebefehle bereitstellt, können Sie mithilfe einer der folgenden Techniken ohne vorherige Abfrage ein Update ausführen:  
  
-   Verwenden Sie <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>, um SQL\-Code zu senden.  
  
-   Erstellen Sie eine neue Instanz des Objekts, und initialisieren Sie alle aktuellen Werte \(Felder\), die sich auf das Update auswirken.  Fügen Sie das Objekt anschließend mithilfe von <xref:System.Data.Linq.DataContext> an <xref:System.Data.Linq.Table%601.Attach%2A> an, und ändern Sie das gewünschte Feld.  
  
## Unerwartete Abfrageergebnisse  
 F.  Meine Abfrage gibt unerwartete Ergebnisse zurück.  Wie kann der Fehler festgestellt werden?  
  
 A.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] stellt mehrere Tools zum Überprüfen des generierten SQL\-Codes bereit.  Eines der wichtigsten Tools ist <xref:System.Data.Linq.DataContext.Log%2A>.  Weitere Informationen finden Sie unter [Debuggingunterstützung](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md).  
  
## Gespeicherte Prozedur gibt unerwartete Ergebnisse zurück  
 F.  Der Rückgabewert einer gespeicherten Prozedur wird durch `MAX()` berechnet.  Wenn die gespeicherte Prozedur auf die [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]\-Oberfläche gezogen wird, ist der Rückgabewert nicht richtig.  
  
 A.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bietet zwei Möglichkeiten, von der Datenbank generierte Werte mithilfe gespeicherter Prozeduren zurückzugeben:  
  
-   Durch Benennen des Ausgabeergebnisses.  
  
-   Durch explizites Festlegen eines Ausgabeparameters.  
  
 Im Folgenden ein Beispiel für eine fehlerhafte Ausgabe.  Da die Ergebnisse von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht zugeordnet werden können, wird immer 0 zurückgegeben:  
  
 `create procedure proc2`  
  
 `as`  
  
 `begin`  
  
 `select max(i) from t where name like 'hello'`  
  
 `end`  
  
 Im Folgenden ein Beispiel für eine richtige Ausgabe, bei der ein Ausgabeparameter verwendet wird:  
  
 `create procedure proc2`  
  
 `@result int OUTPUT`  
  
 `as`  
  
 `select @result = MAX(i) from t where name like 'hello'`  
  
 `go`  
  
 Im Folgenden ein Beispiel für eine richtige Ausgabe, bei der das Ausgabeergebnis benannt wird:  
  
 `create procedure proc2`  
  
 `as`  
  
 `begin`  
  
 `select nax(i) AS MaxResult from t where name like 'hello'`  
  
 `end`  
  
 Weitere Informationen finden Sie unter [Anpassen von Operationen durch Verwenden gespeicherter Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
  
## Serialisierungsfehler  
 F.   Beim Versuch, eine Serialisierung auszuführen, wird folgender Fehler ausgegeben: "Typ 'System.Data.Linq.ChangeTracker\+StandardChangeTracker' ...   ist nicht als serialisierbar gekennzeichnet."  
  
 A.  Die Codegenerierung in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bietet Unterstützung für die <xref:System.Runtime.Serialization.DataContractSerializer>\-Serialisierung.  <xref:System.Xml.Serialization.XmlSerializer> oder <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> wird nicht unterstützt.  Weitere Informationen finden Sie unter [Serialisierung](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md).  
  
## Mehrere DBML\-Dateien  
 F.  Bei Verwendung mehrerer DBML\-Dateien, die einige Tabellen gemeinsam nutzen, wird ein Compilerfehler ausgegeben.  
  
 A.  Legen Sie die **Context Namespace**\-Eigenschaft und die **Entity Namespace**\-Eigenschaft von [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] für jede DBML\-Datei auf einen unterschiedlichen Wert fest.  Durch diese Lösung werden Konflikte zwischen Namen und Namespace vermieden.  
  
## Vermeiden, dass von der Datenbank generierte Werte bei Einfüge\- oder Updatevorgängen explizit festgelegt werden  
 F.  Bei einer Datenbanktabelle mit einer `DateCreated`\-Spalte wird die Spalte standardmäßig auf SQL `Getdate()` festgelegt.  Beim Versuch, mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] einen neuen Datensatz einzufügen, wird der Wert auf `NULL` festgelegt.  Erwartungsgemäß sollte der Wert auf den Datenbankstandard festgelegt werden.  
  
 A.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] behandelt diese Situation bei ID\- \(automatisch inkrementierten\), ROWGUID\- \(von der Datenbank generierte GUID\) und Timestamp\-Spalten automatisch.  In anderen Fällen sollten Sie die Eigenschaften <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>\=`true` und <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>\=<xref:System.Data.Linq.Mapping.AutoSync>\/<xref:System.Data.Linq.Mapping.AutoSync>\/<xref:System.Data.Linq.Mapping.AutoSync> manuell festlegen.  
  
## Mehrere DataLoadOptions  
 F.  Können zusätzliche Ladeoptionen angegeben werden, ohne die erste zu überschreiben?  
  
 A.  Ja.  Die erste Option wird nicht überschrieben, wie im folgenden Beispiel veranschaulicht:  
  
```vb  
Dim dlo As New DataLoadOptions()  
dlo.LoadWith(Of Order)(Function(o As Order) o.Customer)  
dlo.LoadWith(Of Order)(Function(o As Order) o.OrderDetails)  
```  
  
```csharp  
DataLoadOptions dlo = new DataLoadOptions();  
dlo.LoadWith<Order>(o => o.Customer);  
dlo.LoadWith<Order>(o => o.OrderDetails);  
```  
  
## Fehler bei der Verwendung von SQL Compact 3.5  
 F.  Beim Ziehen von Tabellen aus einer [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)]\-Datenbank wird ein Fehler ausgegeben.  
  
 A.  Obwohl [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] von der [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)]\-Laufzeit unterstützt wird, bietet [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] keine entsprechende Unterstützung.  In dieser Situation müssen Sie eigene Entitätsklassen erstellen und die entsprechenden Attribute hinzufügen.  
  
## Fehler in Vererbungsbeziehungen  
 F.  Wenn die Vererbungsform aus der Toolbox in [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] zum Verbinden von zwei Entitäten verwendet wird, treten Fehler auf.  
  
 A.  Es reicht nicht aus, die Beziehung zu erstellen.  Sie müssen Informationen wie Unterscheidungsspalte, Basisklassen\-Diskriminatorwert und Diskriminatorwert der abgeleiteten Klasse angeben.  
  
## Anbietermodell  
 F.  Ist ein öffentliches Anbietermodell verfügbar?  
  
 A.  Es ist kein öffentliches Anbietermodell verfügbar.  Derzeit unterstützt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nur [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] und [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)].  
  
## SQL\-Injection\-Angriffe  
 F.  Wie wird [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vor SQL\-Injection\-Angriffen geschützt?  
  
 A.  In herkömmlichen SQL\-Abfragen, die durch die Verkettung der Benutzereingabe erzeugt wurden, stellte die SQL\-Injection ein bedeutendes Risiko dar.  In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] werden solche Einfügungen durch die Verwendung von <xref:System.Data.SqlClient.SqlParameter> in Abfragen vermieden.  Die Benutzereingabe wird in Parameterwerte umgewandelt.  Auf diese Weise wird verhindert, dass böswillige Befehle aus Kundeneingaben verwendet werden.  
  
## Ändern des Schreibschutzflags in DBML\-Dateien  
 F.  Wie können Setter aus einigen Eigenschaften entfernt werden, wenn ein Objektmodell aus einer DBML\-Datei erstellt wird?  
  
 A.  Führen Sie für dieses erweiterte Szenario die folgenden Schritte aus:  
  
1.  Ändern Sie in der DBML\-Datei die Eigenschaft, indem Sie das <xref:System.Data.Linq.ITable.IsReadOnly%2A>\-Flag in `True` ändern.  
  
2.  Fügen Sie eine partielle Klasse hinzu.  Erstellen Sie einen Konstruktor mit Parametern für die schreibgeschützten Member.  
  
3.  Überprüfen Sie den <xref:System.Data.Linq.Mapping.UpdateCheck>\-Standardwert \(<xref:System.Data.Linq.Mapping.UpdateCheck>\), um zu bestimmen, ob dieses der richtige Wert für die Anwendung ist.  
  
    > [!CAUTION]
    >  Wenn Sie [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] in [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] verwenden, können Ihre Änderungen überschrieben werden.  
  
## APTCA  
 F.  Ist System.Data.Linq für die Verwendung durch teilweise vertrauenswürdigen Code markiert?  
  
 A.  Ja, die System.Data.Linq.dll\-Assembly gehört zu den [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]\-Assemblys, die mit dem <xref:System.Security.AllowPartiallyTrustedCallersAttribute>\-Attribut markiert sind.  Assemblys in [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)], die diese Markierung nicht aufweisen, sind nur für die Verwendung durch voll vertrauenswürdigen Code vorgesehen.  
  
 Das Hauptszenario zum Zulassen teilweise vertrauenswürdiger Aufrufe in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sieht wie folgt aus: Webanwendungen, deren [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Vertrauenswürdigkeit mit einem mittleren Wert konfiguriert ist, muss der Zugriff auf die *\-Assembly gewährt werden.*  
  
## Zuordnen von Daten aus mehreren Tabellen  
 F.  Die Daten in meiner Entität stammen aus mehreren Tabellen.  Wie werden sie zugeordnet?  
  
 A.  Sie können eine Ansicht in einer Datenbank erstellen und die Entität der Ansicht zuordnen.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generiert für Ansichten dieselbe SQL wie für Tabellen.  
  
> [!NOTE]
>  Die Verwendung von Ansichten in diesem Szenario unterliegt Einschränkungen.  Dieser Ansatz funktioniert am sichersten, wenn die für <xref:System.Data.Linq.Table%601> ausgeführten Vorgänge von der zugrunde liegenden Ansicht unterstützt werden.  Nur Sie wissen, welche Vorgänge beabsichtigt sind.  Beispiel: Die meisten Anwendungen sind schreibgeschützt, und eine weitere große Anzahl von Anwendungen führt `Create`\-\/`Update`\-\/`Delete`\-Vorgänge für Ansichten ausschließlich unter Verwendung gespeicherter Prozeduren aus.  
  
## Verbindungspooling  
 F.  Gibt es ein Konstrukt, das das <xref:System.Data.Linq.DataContext>\-Pooling unterstützt?  
  
 A.  Sie sollten nicht versuchen, Instanzen von <xref:System.Data.Linq.DataContext> wiederzuverwenden.  Jeder <xref:System.Data.Linq.DataContext> behält den Zustand \(einschließlich eines Identitätscaches\) für eine bestimmte Bearbeitungs\-\/Abfragesitzung bei.  Um neue Instanzen auf Grundlage des aktuellen Zustands der Datenbank zu erhalten, verwenden Sie einen neuen <xref:System.Data.Linq.DataContext>.  
  
 Sie können weiterhin das zugrunde liegende Verbindungspooling von [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] verwenden.  Weitere Informationen finden Sie unter [SQL Server\-Verbindungspooling \(ADO.NET\)](../../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).  
  
## Zweiter DataContext wird nicht aktualisiert  
 F.  Zum Speichern von Werten in der Datenbank wurde eine Instanz von <xref:System.Data.Linq.DataContext> verwendet.  Die aktualisierten Werte werden aber von einem zweiten <xref:System.Data.Linq.DataContext> in derselben Datenbank nicht angezeigt.  Die zweite <xref:System.Data.Linq.DataContext>\-Instanz scheint zwischengespeicherte Werte zurückzugeben.  
  
 A.  Dieses Verhalten ist vorgesehen.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] gibt weiterhin dieselben Instanzen\/Werte zurück, die in der ersten Instanz angezeigt wurden.  Wenn Sie Updates vornehmen, verwenden Sie vollständige Parallelität.  Die ursprünglichen Daten werden verwendet, um den aktuellen Datenbankzustand zu überprüfen und zu bestätigen, dass der Zustand weiterhin unverändert ist.  Wenn er sich geändert hat, tritt ein Konflikt auf, der von der Anwendung gelöst werden muss.  Eine Möglichkeit für die Anwendung besteht darin, den ursprünglichen Zustand auf den aktuellen Datenbankzustand zurückzusetzen und den Updateversuch zu wiederholen.  Weitere Informationen finden Sie unter [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).  
  
 Sie können auch <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> auf false festlegen, wodurch das Zwischenspeichern und Nachverfolgen von Änderungen deaktiviert wird.  Anschließend können Sie bei jeder Abfrage die neuesten Werte abrufen.  
  
## SubmitChanges kann nicht im schreibgeschützten Modus aufgerufen werden  
 F.  Beim Versuch, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im schreibgeschützten Modus aufzurufen, tritt ein Fehler auf.  
  
 A.  Im schreibgeschützten Modus ist der Kontext nicht mehr in der Lage, Änderungen nachzuverfolgen.  
  
## Siehe auch  
 [Verweis](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)   
 [Problembehandlung](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md)   
 [Sicherheit in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md)