---
title: Neues in ADO.NET
ms.date: 03/30/2017
ms.assetid: 3bb65d38-cce2-46f5-b979-e5c505e95e10
ms.openlocfilehash: 2acbd6a766d91e31db71ce193bcc4081e5f32c9d
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092513"
---
# <a name="whats-new-in-adonet"></a>Neues in ADO.NET
Die folgenden Funktionen sind neu in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].  
  
## <a name="sqlclient-data-provider"></a>SqlClient Data Provider  
 Die folgenden Features sind neu in der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für SQL Server auf [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]:  
  
-   Mit den Verbindungszeichenfolgen von ConnectRetryCount und ConnectRetryInterval (<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>) können Sie die resiliente Verbindungsfunktion im Leerlauf steuern.  
  
-   Unterstützung des Streamings von SQL Server zu einer Anwendung unterstützt Szenarien, in denen Daten auf dem Server unstrukturiert ist.  Finden Sie unter [SqlClient-Streamingunterstützung](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md) für Weitere Informationen.  
  
-   Es wurde Unterstützung für asynchrone Programmierung hinzugefügt.  Finden Sie unter [der asynchronen Programmierung](../../../../docs/framework/data/adonet/asynchronous-programming.md) für Weitere Informationen.  
  
-   Verbindungsfehler werden jetzt im Protokoll für erweiterte Ereignisse protokolliert. Weitere Informationen finden Sie unter [Datenablaufverfolgung in ADO.NET](../../../../docs/framework/data/adonet/data-tracing.md).  
  
-   SqlClient verfügt jetzt über Unterstützung für SQL Server hohe Verfügbarkeit, Notfallwiederherstellungsfunktion voraussetzt, AlwaysOn. Weitere Informationen finden Sie unter [SqlClient-Unterstützung für hohe Verfügbarkeit, Notfallwiederherstellung](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).  
  
-   Ein Kennwort übergeben werden kann, als eine <xref:System.Security.SecureString> bei Verwendung von SQL Server-Authentifizierung. Weitere Informationen finden Sie unter <xref:System.Data.SqlClient.SqlCredential>.  
  
-   Wenn `TrustServerCertificate` ist "false" und `Encrypt` "true", den Servernamen (oder die IP-Adresse) in einem SQL Server-SSL-Zertifikat muss genau übereinstimmen, die Server Name (oder IP-Adresse) in der Verbindungszeichenfolge angegeben ist. Andernfalls schlägt die Verbindung fehl. Weitere Informationen finden Sie in der Beschreibung der `Encrypt`-Verbindungsoption in <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
     Wenn diese Änderung dazu führt, dass eine vorhandene Anwendung keine Verbindung mehr herstellen kann, können Sie das Problem mithilfe eines der folgenden Verfahren beheben:  
  
    -   Geben Sie ein Zertifikat aus, bei dem im Feld für den allgemeinen Namen (Common Name, CN) oder für den alternativen Antragstellernamen (Subject Alternative Name, SAN) der Kurzname angegeben ist. Diese Lösung funktioniert für die Datenbankspiegelung.  
  
    -   Fügen Sie einen Alias hinzu, der den Kurznamen dem vollqualifizierten Domänennamen zuordnet.  
  
    -   Verwenden Sie den vollqualifizierten Domänennamen in der Verbindungszeichenfolge.  
  
-   SqlClient unterstützt den erweiterten Schutz. Weitere Informationen zu erweitertem Schutz finden Sie unter [Herstellen einer Verbindung mit der Datenbank-Engine mithilfe eines erweiterten Schutzes](https://go.microsoft.com/fwlink/?LinkId=219978).  
  
-   SqlClient unterstützt Verbindungen mit LocalDB-Datenbanken. Weitere Informationen finden Sie unter [SqlClient-Unterstützung für LocalDB](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-localdb.md).  
  
-   `Type System Version=SQL Server 2012;` ist der neue Wert, der an die `Type System Version`-Verbindungseigenschaft übergeben wird. Der `Type System Version=Latest;`-Wert ist jetzt veraltet und wurde `Type System Version=SQL Server 2008;` angeglichen. Weitere Informationen finden Sie unter <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
-   SqlClient bietet zusätzliche Unterstützung für Spalten mit geringer Dichte, eine Funktion, die in SQL Server 2008 hinzugefügt wurde. Wenn die Anwendung bereits auf Daten in einer Tabelle zugreift, die Spalten mit geringer Dichte verwendet, sollten Sie eine Leistungsverbesserung feststellen. Die IsColumnSet-Spalte von <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> gibt an, ob eine Spalte eine Sparsespalte ist und einem Spaltensatz angehört. <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> Gibt an, ob eine Spalte eine sparsespalte ist (siehe [SQL Server-Schemaauflistungen](../../../../docs/framework/data/adonet/sql-server-schema-collections.md) Informationen). Weitere Informationen zu sparsespalten finden Sie unter [Verwenden von Sparsespalten](https://go.microsoft.com/fwlink/?LinkId=224244).  
  
-   Für die Microsoft.SqlServer.Types.dll-Assembly, die die räumlichen Datentypen enthält, wurde ein Upgrade von Version 10.0 auf Version 11.0 vorgenommen. Anwendungen, die auf diese Assembly verweisen, schlagen möglicherweise fehl. Weitere Informationen finden Sie unter [wichtige Änderungen an Funktionen der Datenbank-Engine](https://go.microsoft.com/fwlink/?LinkId=224367).  
  
## <a name="adonet-entity-framework"></a>ADO.NET Entity Framework  
 Durch [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] werden APIs hinzugefügt, die bei Verwendung von Entity Framework 5.0 neue Szenarien ermöglichen. Weitere Informationen zu Verbesserungen und Funktionen, die Entity Framework 5.0 hinzugefügt wurden, finden Sie unter den folgenden Themen: [Neues](https://go.microsoft.com/fwlink/?LinkID=251106) und [Entity Framework-Versionen und Versionsverwaltung](https://go.microsoft.com/fwlink/?LinkId=234899).  
  
## <a name="see-also"></a>Siehe auch
- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
- [Übersicht über ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [SQL Server und ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)
- [Neues in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
