---
title: Sicherheitsüberlegungen (Entity Framework)
ms.date: 03/30/2017
ms.assetid: 84758642-9b72-4447-86f9-f831fef46962
ms.openlocfilehash: 47dbf800852e149f541c512e90a8bafef2077672
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65879921"
---
# <a name="security-considerations-entity-framework"></a>Sicherheitsüberlegungen (Entity Framework)
In diesem Thema werden spezielle Sicherheitsaspekte hinsichtlich der Entwicklung, der Bereitstellung und der Ausführung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Anwendungen beschrieben. Sie sollten auch Empfehlungen für das Erstellen sicherer Anwendungen für .NET Framework ausführen. Weitere Informationen finden Sie unter [Sicherheitsübersicht](../../../../../docs/framework/data/adonet/security-overview.md).  
  
## <a name="general-security-considerations"></a>Allgemeine Überlegungen zur Sicherheit  
 Die folgenden Sicherheitsaspekte gelten für alle Anwendungen, die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verwenden.  
  
#### <a name="use-only-trusted-data-source-providers"></a>Verwenden Sie nur vertrauenswürdige Datenquellenanbieter.  
 Um mit der Datenquelle zu kommunizieren, muss ein Anbieter wie folgt vorgehen:  
  
- Empfangen der Verbindungszeichenfolge von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]  
  
- Übersetzen der Befehlsstruktur in die native Abfragesprache der Datenquelle  
  
- Zusammenstellen und Zurückgeben von Resultsets  
  
 Während des Anmeldevorgangs werden Informationen auf der Grundlage des Benutzerkennworts über die Netzwerkbibliotheken der zugrunde liegenden Datenquelle an den Server übertragen. Ein böswilliger Anbieter kann Benutzeranmeldeinformationen stehlen, böswillige Abfragen generieren oder das Resultset manipulieren.  
  
#### <a name="encrypt-your-connection-to-protect-sensitive-data"></a>Verschlüsseln Sie die Verbindung, um vertrauliche Daten zu schützen.  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] behandelt die Datenverschlüsselung nicht direkt. Wenn Benutzer über ein öffentliches Netzwerk auf Daten zugreifen, sollte die Anwendung eine verschlüsselte Verbindung mit der Datenquelle herstellen, um die Sicherheit zu erhöhen. Weitere Informationen finden Sie in der die Sicherheit betreffenden Dokumentation für die Datenquelle. Eine SQL Server-Datenquelle finden Sie unter [Verschlüsseln von Verbindungen zu SQL Server](https://go.microsoft.com/fwlink/?LinkId=119544).  
  
#### <a name="secure-the-connection-string"></a>Sichern Sie die Verbindungszeichenfolge ab.  
 Eines der wichtigsten Ziele beim Sichern einer Anwendung besteht darin, den Zugriff auf die Datenquelle zu schützen. Eine Verbindungszeichenfolge stellt ein potenzielles Sicherheitsrisiko dar, wenn sie nicht gesichert wird oder nicht ordnungsgemäß aufgebaut ist. Das Speichern von Verbindungsinformationen als Klartext oder das Aufbewahren dieser Informationen im Arbeitsspeicher gefährdet das gesamte System. Folgende Methoden werden zum Sichern von Verbindungszeichenfolgen empfohlen:  
  
- Verwenden Sie die Windows-Authentifizierung bei einer SQL Server-Datenquelle.  
  
     Wenn Sie die Windows-Authentifizierung verwenden, um eine Verbindung mit einer SQL Server-Datenquelle herzustellen, enthält die Verbindungszeichenfolge keine Anmelde- und Kennwortinformationen.  
  
- Verschlüsseln Sie Konfigurationsdateiabschnitte mithilfe der geschützten Konfiguration.  
  
     ASP.NET bietet ein als geschützte Konfiguration bezeichnetes Feature, mit dem Sie sicherheitsrelevante Informationen in einer Konfigurationsdatei verschlüsseln können. Die geschützte Konfiguration wurde zwar primär für ASP.NET entwickelt, sie kann jedoch auch zum Verschlüsseln von Konfigurationsdateiabschnitten in Windows-Anwendungen verwendet werden. Eine ausführliche Beschreibung der neuen Funktionen für die geschützte Konfiguration, finden Sie unter [Encrypting Configuration Information mithilfe von geschützten Configuration](https://docs.microsoft.com/previous-versions/aspnet/53tyfkaw(v=vs.100)).  
  
- Speichern Sie Verbindungszeichenfolgen in gesicherten Konfigurationsdateien.  
  
     Sie sollten Verbindungszeichenfolgen niemals in den Quellcode aufnehmen. Sie können die Verbindungszeichenfolgen in Konfigurationsdateien speichern. Damit erübrigt sich die Notwendigkeit, sie in den Code der Anwendung einzubetten. Standardmäßig speichert der Assistent für Entity Data Model Verbindungszeichenfolgen in der Anwendungskonfigurationsdatei. Sie müssen diese Datei sichern, um den nicht autorisierten Zugriff zu verhindern.  
  
- Verwenden Sie Verbindungszeichenfolgen-Generatoren, wenn Sie Verbindungen dynamisch erstellen.  
  
     Wenn Sie Verbindungszeichenfolgen zur Laufzeit erstellen müssen, verwenden Sie die <xref:System.Data.EntityClient.EntityConnectionStringBuilder>-Klasse. Diese Zeichenfolgen-Generator-Klasse hilft durch Überprüfen und Versehen von ungültigen Eingabeinformationen mit Escapezeichen, Angriffe durch Einschleusen von Verbindungszeichenfolgen zu verhindern. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md). Auch die entsprechende Zeichenfolgengenerator-Klasse verwenden, um die Datenquellen-Verbindungszeichenfolge zu erstellen, die Teil ist die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Verbindungszeichenfolge. Weitere Informationen zu Verbindungszeichenfolgen-Generatoren für ADO.NET-Anbieter finden Sie unter [Verbindungszeichenfolgen-Generatoren](../../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
 Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
#### <a name="do-not-expose-an-entityconnection-to-untrusted-users"></a>Machen Sie keine EntityConnection für nicht vertrauenswürdige Benutzer verfügbar.  
 Ein <xref:System.Data.EntityClient.EntityConnection>-Objekt macht die Verbindungszeichenfolge der zugrunde liegenden Verbindung verfügbar. Ein Benutzer mit Zugriff auf ein <xref:System.Data.EntityClient.EntityConnection>-Objekt kann auch den <xref:System.Data.ConnectionState> der zugrunde liegenden Verbindung ändern. Die <xref:System.Data.EntityClient.EntityConnection>-Klasse ist nicht threadsicher.  
  
#### <a name="do-not-pass-connections-outside-the-security-context"></a>Übergeben Sie Verbindungen nicht außerhalb des Sicherheitskontexts.  
 Nachdem eine Verbindung hergestellt wurde, dürfen Sie diese nicht außerhalb des Sicherheitskontexts übergeben. Ein Thread, der über die Berechtigung zum Öffnen einer Verbindung verfügt, sollte die Verbindung nicht an einem globalen Speicherort speichern. Wenn die Verbindung an einem globalen Speicherort zur Verfügung steht, kann ein bösartiger Thread die offene Verbindung verwenden, ohne dass diesem die Berechtigung dazu explizit gewährt wurde.  
  
#### <a name="be-aware-that-logon-information-and-passwords-may-be-visible-in-a-memory-dump"></a>Beachten Sie, dass Anmeldeinformationen und Kennwörter möglicherweise in einem Speicherabbild sichtbar sind.  
 Wenn Anmelde- und Kennwortinformationen für die Datenquelle in der Verbindungszeichenfolge übergeben werden, bleiben diese Informationen im Arbeitsspeicher erhalten, bis die Garbage Collection die Ressourcen wieder freigibt. Dies macht es unmöglich, festzustellen, wann sich eine Kennwortzeichenfolge nicht mehr im Arbeitsspeicher befindet. Wenn eine Anwendung abstürzt, kann eine Speicherabbilddatei vertrauliche Informationen enthalten, die der Benutzer der Anwendung und jeder Benutzer mit Administratorzugriffsrechten für den Computer anzeigen kann. Verwenden Sie die Windows-Authentifizierung für Verbindungen mit Microsoft SQL Server.  
  
#### <a name="grant-users-only-the-necessary-permissions-in-the-data-source"></a>Gewähren Sie Benutzern nur die notwendigen Berechtigungen für die Datenquelle.  
 Ein Datenquellenadministrator sollte Benutzern nur die notwendigen Berechtigungen gewähren. Auch wenn [!INCLUDE[esql](../../../../../includes/esql-md.md)] DML-Anweisungen zum Ändern von Daten, wie beispielsweise INSERT, UPDATE oder DELETE, nicht unterstützt, können Benutzer dennoch auf die Verbindung zur Datenquelle zugreifen. Ein böswilliger Benutzer könnte diese Verbindung verwenden, um DML-Anweisungen in der systemeigenen Sprache der Datenquelle auszuführen.  
  
#### <a name="run-applications-with-the-minimum-permissions"></a>Führen Sie Anwendungen mit den minimalen Berechtigungen aus.  
 Wenn Sie eine verwaltete Anwendung, mit der Berechtigung mit vollständiger Vertrauenswürdigkeit ausgeführt werden können, wird .NET Framework nicht der Anwendung Zugriff auf Ihren Computer beschränkt. Dies kann zu einer Sicherheitslücke in der Anwendung führen, durch die das gesamte System gefährdet werden kann. Um Codezugriffssicherheit und andere Sicherheitsmechanismen in .NET Framework zu verwenden, sollten Sie Anwendungen ausführen, mit der Berechtigungen für teilweise Vertrauenswürdigkeit und mit der Minimalsatz an Berechtigungen, die erforderlich sind, um die Anwendung ordnungsgemäß zu aktivieren. Die folgenden Codezugriffsberechtigungen sind die minimalen Berechtigungen, die eine [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Anwendung benötigt:  
  
- <xref:System.Security.Permissions.FileIOPermission>: <xref:System.Security.Permissions.FileIOPermissionAccess.Write>, um die angegebenen Metadatendateien zu öffnen, oder <xref:System.Security.Permissions.FileIOPermissionAccess.PathDiscovery>, um in einem Verzeichnis nach Metadatendateien zu suchen.  
  
- <xref:System.Security.Permissions.ReflectionPermission>: <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess>, um "LINQ to Entities"-Abfragen zu unterstützen.  
  
- <xref:System.Transactions.DistributedTransactionPermission>: <xref:System.Security.Permissions.PermissionState.Unrestricted>, um einen Eintrag in einer <xref:System.Transactions><xref:System.Transactions.Transaction> vorzunehmen.  
  
- <xref:System.Security.Permissions.SecurityPermission>: <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>, um Ausnahmen mithilfe der <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle zu serialisieren.  
  
- Berechtigung zum Öffnen einer datenbankverbindung und führen Sie Befehle für die Datenbank, z. B. <xref:System.Data.SqlClient.SqlClientPermission> für eine SQL Server-Datenbank.  
  
 Weitere Informationen finden Sie unter [Code Access Security and ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md).  
  
#### <a name="do-not-install-untrusted-applications"></a>Installieren Sie keine nicht vertrauenswürdigen Anwendungen.  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] erzwingt keinerlei Sicherheitsberechtigungen und ruft jeden vom Benutzer übergebenen Datenobjektcode während der Verarbeitung auf, unabhängig davon, ob dieser vertrauenswürdig ist oder nicht. Stellen Sie sicher, dass die Authentifizierung und die Autorisierung des Clients durch den Datenspeicher und Ihre Anwendung erfolgen.  
  
#### <a name="restrict-access-to-all-configuration-files"></a>Schränken Sie den Zugriff auf alle Konfigurationsdateien ein.  
 Ein Administrator muss den Schreibzugriff auf alle Dateien, in denen Konfigurationsinformationen für eine Anwendung, einschließlich der Dateien "enterprisesec.config", "security.config", "Machine.conf" und der Anwendungskonfigurationsdatei beschränken \< *Anwendung* >. exe.config.  
  
 Der invariante Name des Anbieters kann in app.config geändert werden. Die Clientanwendung ist für den Zugriff auf den zugrunde liegenden Anbieter über das Anbieterfactory-Standardmodell unter Verwendung eines starken Namens zuständig.  
  
#### <a name="restrict-permissions-to-the-model-and-mapping-files"></a>Schränken Sie die Zugriffsberechtigungen auf die Modell- und Zuordnungsdateien ein.  
 Ein Administrator muss den Schreibzugriff auf die Modell- und Zuordnungsdateien (EDMX-, CSDL-, SSDL- und MSL-Dateien) auf die Benutzer beschränken, die das Modell oder die Zuordnungen ändern. Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] muss über Lesezugriff auf diese Dateien nur zur Laufzeit. Ein Administrator sollte außerdem den Zugriff auf Quellcodedateien der Objektebene und vorkompilierter Sichten, die durch die [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]-Tools erzeugt werden, einschränken.  
  
## <a name="security-considerations-for-queries"></a>Sicherheitsaspekte bei Abfragen  
 Folgende Sicherheitsaspekte sollten beim Abfragen eines konzeptionellen Modells beachtet werden. Diese Aspekte gelten für [!INCLUDE[esql](../../../../../includes/esql-md.md)]-Abfragen, die EntityClient verwenden, und für Objektabfragen mithilfe von LINQ, [!INCLUDE[esql](../../../../../includes/esql-md.md)] und Abfrage-Generator-Methoden.  
  
#### <a name="prevent-sql-injection-attacks"></a>Verhindern Sie Angriffe durch Einschleusung von SQL-Befehlen.  
 Anwendungen verwenden häufig externe Eingaben (eines Benutzers oder eines anderen externen Agenten) und führen entsprechend dieser Eingaben Aktionen aus. Jede direkt oder indirekt vom Benutzer oder einem externen Agenten stammende Eingabe kann über Inhalt verfügen, der die Syntax der Zielsprache nutzt, um nicht autorisierte Aktionen auszuführen. Wenn es sich bei der Zielsprache um eine strukturierte Abfragesprache (Structured Query Language, SQL), wie beispielsweise [!INCLUDE[tsql](../../../../../includes/tsql-md.md)], handelt, wird diese Manipulation als Angriff durch Einschleusung von SQL-Befehlen (SQL Injection) bezeichnet. Ein böswilliger Benutzer kann Befehle direkt in Abfragen einschleusen und eine Datenbanktabelle löschen, einen Denial-of-Service-Angriff verursachen oder auf andere Art und Weise die auszuführende Operation ändern.  
  
- Angriffe durch Einschleusen von [!INCLUDE[esql](../../../../../includes/esql-md.md)]:  
  
     Angriffe durch Einschleusung von SQL-Befehlen können in [!INCLUDE[esql](../../../../../includes/esql-md.md)] ausgeführt werden, indem böswillige Eingaben für Werte vorgenommen werden, die in Abfrageprädikaten und Parameternamen verwendet werden. Um das Risiko von Angriffen durch Einschleusung von SQL-Befehlen zu vermeiden, sollten Sie niemals Benutzereingaben mit [!INCLUDE[esql](../../../../../includes/esql-md.md)]-Befehlstext kombinieren.  
  
     [!INCLUDE[esql](../../../../../includes/esql-md.md)]-Abfragen akzeptieren Parameter an allen Stellen, an denen Literale akzeptiert werden. Sie sollten parametrisierte Abfragen verwenden, anstatt Literale von einem externen Agenten direkt in die Abfrage einzufügen. Sie sollten auch berücksichtigen, mit [Abfrage-Generator-Methoden](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896238(v=vs.100)) zur sicheren Erstellung von Entity SQL.  
  
- Angriffe durch Einschleusen von [!INCLUDE[linq_entities](../../../../../includes/linq-entities-md.md)]:  
  
     Obwohl das Zusammensetzen von Abfragen in [!INCLUDE[linq_entities](../../../../../includes/linq-entities-md.md)] möglich ist, wird dieser Vorgang über die Objektmodell-API ausgeführt. Im Gegensatz zu [!INCLUDE[esql](../../../../../includes/esql-md.md)]-Abfragen werden [!INCLUDE[linq_entities](../../../../../includes/linq-entities-md.md)]-Abfragen nicht durch Zeichenfolgenbearbeitung oder -verkettung erstellt und sind nicht anfällig gegenüber herkömmlichen Angriffen durch Einschleusung von SQL-Befehlen.  
  
#### <a name="prevent-very-large-result-sets"></a>Verhindern Sie sehr umfangreiche Resultsets.  
 Ein sehr umfangreiches Resultset kann dazu führen, dass das Clientsystem heruntergefahren wird, wenn der Client Vorgänge ausführt, die Ressourcen proportional zum Umfang des Resultsets ausführt. Unerwartet große Resultsets können unter den folgenden Bedingungen auftreten:  
  
- In Abfragen an eine große Datenbank, die keine entsprechenden Filterbedingungen enthalten.  
  
- In Abfragen, die kartesische Verknüpfungen auf dem Server erstellen.  
  
- In geschachtelten [!INCLUDE[esql](../../../../../includes/esql-md.md)]-Abfragen.  
  
 Wenn Sie Benutzereingaben akzeptieren, müssen Sie sicherstellen, dass die Eingaben keine Resultsets verursachen können, die umfangreicher sind als die Datenmengen, die das System verarbeiten kann. Können Sie auch die <xref:System.Linq.Queryable.Take%2A> -Methode in der [!INCLUDE[linq_entities](../../../../../includes/linq-entities-md.md)] oder [Grenzwert](../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) -Operator in [!INCLUDE[esql](../../../../../includes/esql-md.md)] auf die Größe des Resultsets zu begrenzen.  
  
#### <a name="avoid-returning-iqueryable-results-when-exposing-methods-to-potentially-untrusted-callers"></a>Vermeiden Sie es, IQueryable-Ergebnisse zurückzugeben, wenn Sie Methoden für potenziell nicht vertrauenswürdige Aufrufer verfügbar machen.  
 Vermeiden Sie es aus den folgenden Gründen, <xref:System.Linq.IQueryable%601>-Typen von Methoden zurückzugeben, die für potenziell nicht vertrauenswürdige Aufrufer verfügbar gemacht wurden:  
  
- Der Consumer einer Abfrage, die einen <xref:System.Linq.IQueryable%601>-Typ verfügbar macht, könnte mit dem Ergebnis Methoden aufrufen, die sichere Daten verfügbar machen oder die Größe des Resultsets erhöhen. Betrachten Sie beispielsweise die folgende Methodensignatur:  
  
    ```  
    public IQueryable<Customer> GetCustomer(int customerId)  
    ```  
  
     Ein Consumer dieser Abfrage könnte `.Include("Orders")` für den zurückgegebenen `IQueryable<Customer>` aufrufen, um Daten abrufen, die durch die Abfrage nicht verfügbar gemacht werden sollten. Dies kann vermieden werden, indem der Rückgabetyp der Methode in <xref:System.Collections.Generic.IEnumerable%601> geändert und eine Methode aufgerufen wird (beispielsweise `.ToList()`), die die Ergebnisse materialisiert.  
  
- Da <xref:System.Linq.IQueryable%601>-Abfragen ausgeführt werden, während die Ergebnisse durchlaufen werden, könnte der Consumer einer Abfrage, die einen <xref:System.Linq.IQueryable%601>-Typ verfügbar macht, eventuell ausgelöste Ausnahmen abfangen. Ausnahmen könnten Informationen enthalten, die nicht für den Consumer bestimmt sind.  
  
## <a name="security-considerations-for-entities"></a>Sicherheitsaspekte bei Entitäten  
 Die folgenden Sicherheitsaspekte gelten, wenn Sie Entitätstypen generieren und mit Entitätstypen arbeiten.  
  
#### <a name="do-not-share-an-objectcontext-across-application-domains"></a>Geben Sie einen ObjectContext nicht über Anwendungsdomänen hinweg frei.  
 Einen <xref:System.Data.Objects.ObjectContext> für mehr als eine Anwendungsdomäne freizugeben macht möglicherweise Informationen in der Verbindungszeichenfolge verfügbar. Stattdessen sollten Sie serialisierte Objekte oder Objektdiagramme an die andere Anwendungsdomäne übertragen und dann diese Objekte einem <xref:System.Data.Objects.ObjectContext> in der Anwendungsdomäne anfügen. Weitere Informationen finden Sie unter [Serialisieren von Objekten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738446(v=vs.100)).  
  
#### <a name="prevent-type-safety-violations"></a>Verhindern Sie Verletzungen der Typsicherheit.  
 Wenn die Typsicherheit verletzt wird, kann [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] die Integrität der Daten in Objekten nicht garantieren. Verletzungen der Typsicherheit könnten auftreten, wenn Sie zulassen, dass nicht vertrauenswürdige Anwendungen mit voll vertrauenswürdiger Codezugriffssicherheit ausgeführt werden.  
  
#### <a name="handle-exceptions"></a>Behandeln von Ausnahmen  
 Greifen Sie auf die Methoden und Eigenschaften von <xref:System.Data.Objects.ObjectContext> innerhalb eines try-catch-Blocks zu. Das Abfangen von Ausnahmen verhindert, dass nicht behandelte Ausnahmen Benutzern der Anwendung Einträge im <xref:System.Data.Objects.ObjectStateManager> oder Modellinformationen (beispielsweise Tabellennamen), verfügbar machen.  
  
## <a name="security-considerations-for-aspnet-applications"></a>Sicherheitsaspekte für ASP.NET-Anwendungen  

Sie sollten die folgende, beim Arbeiten mit Pfaden in ASP.NET-Anwendungen.  
  
#### <a name="verify-whether-your-host-performs-path-checks"></a>Überprüfen Sie, ob der Host Pfadprüfungen ausführt.  
 Wenn die `|DataDirectory|` (zwischen pipesymbolen) verwendet wird, die ADO.NET stellt sicher, dass der aufgelöste Pfad unterstützt wird. Beispielsweise ist ".." hinter `DataDirectory` nicht zulässig. Dieselbe Überprüfung für das Auflösen von der Web Application-Stamm-Operators (`~`) erfolgt durch den Prozess, der ASP.NET hostet. IIS führt diese Überprüfung aus. Andere Hosts als IIS können möglicherweise nicht überprüfen, ob der aufgelöste Pfad unterstützt wird. Sie sollten das Verhalten des Hosts kennen, auf dem Sie eine [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Anwendung bereitstellen.  
  
#### <a name="do-not-make-assumptions-about-resolved-path-names"></a>Gehen Sie nicht von Annahmen über aufgelöste Pfadnamen aus.  
 Obwohl die Werte, in die der Stamm-Operator (`~`) und die `DataDirectory`-Ersatzzeichenfolge aufgelöst werden, während der Laufzeit der Anwendung konstant bleiben sollten, wird der Host durch [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] nicht daran gehindert, diese Werte zu ändern.  
  
#### <a name="verify-the-path-length-before-deployment"></a>Überprüfen Sie die Pfadlänge vor der Bereitstellung.  
 Stellen Sie vor der Bereitstellung einer [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Anwendung sicher, dass die Werte des Stammoperators (~) und der `DataDirectory`-Ersatzzeichenfolge nicht die Pfadlängengrenze des Betriebssystems überschreiten. ADO.NET-Datenanbieter gewährleisten nicht, dass die Länge des Pfads zulässigen Begrenzungen entspricht.  
  
## <a name="security-considerations-for-adonet-metadata"></a>Sicherheitsaspekte für ADO.NET-Metadaten  
 Wenn Sie Modell- und Zuordnungsdateien erzeugen und mit ihnen arbeiten, berücksichtigen Sie Folgendes hinsichtlich der Sicherheit:  
  
#### <a name="do-not-expose-sensitive-information-through-logging"></a>Machen Sie vertrauliche Informationen nicht durch Protokollierung verfügbar.  
ADO.NET Metadaten-Dienstkomponenten protokollieren keine private Informationen. Wenn Ergebnisse aufgrund von Zugriffsbeschränkungen nicht zurückgegeben werden können, sollten Datenbankmanagementsysteme und Dateisysteme Ergebnisse mit dem Wert Null zurückgeben, statt eine Ausnahme auszulösen, die vertrauliche Informationen enthalten könnte.  
  
#### <a name="do-not-accept-metadataworkspace-objects-from-untrusted-sources"></a>Akzeptieren Sie keine "MetadataWorkspace"-Objekte von nicht vertrauenswürdigen Quellen.  
 Anwendungen sollten keine Instanzen der <xref:System.Data.Metadata.Edm.MetadataWorkspace>-Klasse von nicht vertrauenswürdigen Quellen akzeptieren. Stattdessen sollten Sie einen Arbeitsbereich explizit erstellen und aus so einer Quelle füllen.  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [Überlegungen zur Bereitstellung](../../../../../docs/framework/data/adonet/ef/deployment-considerations.md)
- [Migrationsüberlegungen](../../../../../docs/framework/data/adonet/ef/migration-considerations.md)
