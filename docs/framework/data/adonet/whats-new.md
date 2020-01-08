---
title: Neues in ADO.NET
ms.date: 03/30/2017
ms.assetid: 3bb65d38-cce2-46f5-b979-e5c505e95e10
ms.openlocfilehash: db903f801994202ac50ac72ad5352f20367efed7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337023"
---
# <a name="whats-new-in-adonet"></a>Neues in ADO.NET

Die folgenden Features sind neu in ADO.net im .NET Framework 4,5.

## <a name="sqlclient-data-provider"></a>SqlClient Data Provider

Die folgenden Features sind neu in den .NET Framework Datenanbieter für SQL Server in .NET Framework 4,5:

- Mit den Verbindungszeichenfolgen von ConnectRetryCount und ConnectRetryInterval (<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>) können Sie die resiliente Verbindungsfunktion im Leerlauf steuern.

- Die Streamingunterstützung von SQL Server zu einer Anwendung unterstützt Szenarien, in denen Daten auf dem Server nicht strukturiert sind.  Weitere Informationen finden Sie [unter SqlClient-Streamingunterstützung](sqlclient-streaming-support.md) .

- Es wurde Unterstützung für asynchrone Programmierung hinzugefügt.  Weitere Informationen finden Sie unter [asynchrone Programmierung](asynchronous-programming.md) .

- Verbindungsfehler werden jetzt im Protokoll für erweiterte Ereignisse protokolliert. Weitere Informationen finden Sie unter [Datenablaufverfolgung in ADO.NET](data-tracing.md).

- SqlClient bietet jetzt Unterstützung für die Hochverfügbarkeit, die Notfall Wiederherstellung (AlwaysOn) SQL Server. Weitere Informationen finden Sie [unter SqlClient-Unterstützung für hohe Verfügbarkeit, Notfall Wiederherstellung](./sql/sqlclient-support-for-high-availability-disaster-recovery.md).

- Ein Kennwort kann bei Verwendung SQL Server Authentifizierung als <xref:System.Security.SecureString> übermittelt werden. Weitere Informationen finden Sie unter <xref:System.Data.SqlClient.SqlCredential>.

- Wenn `TrustServerCertificate` false ist und `Encrypt` true ist, muss der Servername (oder die IP-Adresse) in einem SQL Server SSL-Zertifikat genau mit dem in der Verbindungs Zeichenfolge angegebenen Servernamen (oder der IP-Adresse) übereinstimmen. Andernfalls schlägt die Verbindung fehl. Weitere Informationen finden Sie in der Beschreibung der `Encrypt`-Verbindungsoption in <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.

  Wenn diese Änderung dazu führt, dass eine vorhandene Anwendung keine Verbindung mehr herstellen kann, können Sie das Problem mithilfe eines der folgenden Verfahren beheben:

  - Geben Sie ein Zertifikat aus, bei dem im Feld für den allgemeinen Namen (Common Name, CN) oder für den alternativen Antragstellernamen (Subject Alternative Name, SAN) der Kurzname angegeben ist. Diese Lösung funktioniert für die Datenbankspiegelung.

  - Fügen Sie einen Alias hinzu, der den Kurznamen dem vollqualifizierten Domänennamen zuordnet.

  - Verwenden Sie den vollqualifizierten Domänennamen in der Verbindungszeichenfolge.

- SqlClient unterstützt den erweiterten Schutz. Weitere Informationen zum erweiterten Schutz finden Sie unter [Herstellen einer Verbindung mit dem Datenbank-Engine mit erweitertem Schutz](/sql/database-engine/configure-windows/connect-to-the-database-engine-using-extended-protection).

- SqlClient unterstützt Verbindungen mit LocalDB-Datenbanken. Weitere Informationen finden Sie [unter SqlClient-Unterstützung für localdb](./sql/sqlclient-support-for-localdb.md).

- `Type System Version=SQL Server 2012;` ist der neue Wert, der an die `Type System Version`-Verbindungseigenschaft übergeben wird. Der `Type System Version=Latest;`-Wert ist jetzt veraltet und wurde `Type System Version=SQL Server 2008;` angeglichen. Weitere Informationen finden Sie unter <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.

- SqlClient bietet zusätzliche Unterstützung für Sparsespalten, eine Funktion, die in SQL Server 2008 hinzugefügt wurde. Wenn Ihre Anwendung bereits auf Daten in einer Tabelle zugreift, die Sparsespalten verwendet, sollten Sie einen Leistungszuwachs feststellen können. Die IsColumnSet-Spalte von <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> gibt an, ob eine Spalte eine Sparsespalte ist und einem Spaltensatz angehört. <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> gibt an, ob eine Spalte eine sparsespalte ist (Weitere Informationen finden Sie unter [SQL Server Schema](sql-server-schema-collections.md) Auflistungen). Weitere Informationen zu sparsespalten finden Sie unter [Verwenden von sparsespalten](/sql/relational-databases/tables/use-sparse-columns).

- Die Assembly Microsoft.SqlServer.Types.dll, die räumliche Datentypen enthält, wurde von Version 10.0 auf Version 11.0 aktualisiert. Anwendungen, die auf diese Assembly verweisen, schlagen möglicherweise fehl. Weitere Informationen finden Sie unter [Breaking Changes to Datenbank-Engine Features](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/ms143179(v=sql.110)).

## <a name="adonet-entity-framework"></a>ADO.NET Entity Framework

Der .NET Framework 4,5 fügt APIs hinzu, die bei der Arbeit mit Entity Framework 5,0 neue Szenarien ermöglichen. Weitere Informationen zu Verbesserungen und Features, die dem Entity Framework 5,0 hinzugefügt wurden, finden Sie in den folgenden Themen: [Neuerungen](https://docs.microsoft.com/previous-versions/gg696190(v=vs.103)) und [Entity Framework Releases und Versions](/ef/ef6/what-is-new/past-releases)Verwaltung.

## <a name="see-also"></a>Siehe auch

- [ADO.NET](index.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
- [SQL Server und ADO.NET](./sql/index.md)
- [Neues in WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))
