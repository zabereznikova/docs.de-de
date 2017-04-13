---
title: "Neues in ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3bb65d38-cce2-46f5-b979-e5c505e95e10
caps.latest.revision: 25
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 25
---
# Neues in ADO.NET
Die folgenden Funktionen sind neu in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].  
  
## SqlClient Data Provider  
 Die folgenden Funktionen sind im [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbieter für [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] neu:  
  
-   Mit den Verbindungszeichenfolgen von ConnectRetryCount und ConnectRetryInterval \(<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>\) können Sie die resiliente Verbindungsfunktion im Leerlauf steuern.  
  
-   Die Streamingunterstützung von [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] für eine Anwendung unterstützt Szenarien, in denen Daten auf dem Server unstrukturiert sind.  Weitere Informationen finden Sie unter [SqlClient\-Streamingunterstützung](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md).  
  
-   Es wurde Unterstützung für asynchrone Programmierung hinzugefügt.  Weitere Informationen finden Sie unter [Asynchrone Programmierung](../../../../docs/framework/data/adonet/asynchronous-programming.md).  
  
-   Verbindungsfehler werden jetzt im Protokoll für erweiterte Ereignisse protokolliert.  Weitere Informationen finden Sie unter [Datenablaufverfolgung in ADO.NET](../../../../docs/framework/data/adonet/data-tracing.md).  
  
-   SqlClient bietet jetzt Unterstützung für die AlwaysOn\-Funktion für hohe Verfügbarkeit und Notfallwiederherstellung von [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].  Weitere Informationen finden Sie unter [SqlClient\-Unterstützung für hohe Verfügbarkeit, Notfallwiederherstellung](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).  
  
-   Bei Verwendung der [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]\-Authentifizierung kann ein Kennwort als <xref:System.Security.SecureString> übergeben werden.  Weitere Informationen finden Sie unter <xref:System.Data.SqlClient.SqlCredential>.  
  
-   Wenn `TrustServerCertificate` FALSE und `Encrypt` TRUE sind, müssen der Servername \(oder die IP\-Adresse\) in einem [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]\-SSL\-Zertifikat genau dem Servernamen \(oder der IP\-Adresse\) entsprechen, die in der Verbindungszeichenfolge angegeben werden.  Andernfalls schlägt die Verbindung fehl.  Weitere Informationen finden Sie in der Beschreibung der `Encrypt`\-Verbindungsoption in <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
     Wenn diese Änderung dazu führt, dass eine vorhandene Anwendung keine Verbindung mehr herstellen kann, können Sie das Problem mithilfe eines der folgenden Verfahren beheben:  
  
    -   Geben Sie ein Zertifikat aus, bei dem im Feld für den allgemeinen Namen \(Common Name, CN\) oder für den alternativen Antragstellernamen \(Subject Alternative Name, SAN\) der Kurzname angegeben ist.  Diese Lösung funktioniert für die Datenbankspiegelung.  
  
    -   Fügen Sie einen Alias hinzu, der den Kurznamen dem vollqualifizierten Domänennamen zuordnet.  
  
    -   Verwenden Sie den vollqualifizierten Domänennamen in der Verbindungszeichenfolge.  
  
-   SqlClient unterstützt den erweiterten Schutz.  Weitere Informationen zum erweiterten Schutz finden Sie unter [Verbindung mit der Datenbank\-Engine mithilfe eines erweiterten Schutzes](http://go.microsoft.com/fwlink/?LinkId=219978).  
  
-   SqlClient unterstützt Verbindungen mit LocalDB\-Datenbanken.  Weitere Informationen finden Sie unter [SqlClient\-Unterstützung für LocalDB](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-localdb.md).  
  
-   `Type System Version=SQL Server 2012;` ist der neue Wert, der an die `Type System Version`\-Verbindungseigenschaft übergeben wird.  Der `Type System Version=Latest;`\-Wert ist jetzt veraltet und wurde `Type System Version=SQL Server 2008;` angeglichen.  Weitere Informationen finden Sie unter <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
-   SqlClient bietet zusätzliche Unterstützung für Spalten mit geringer Dichte, eine Funktion, die in SQL Server 2008 hinzugefügt wurde.  Wenn die Anwendung bereits auf Daten in einer Tabelle zugreift, die Spalten mit geringer Dichte verwendet, sollten Sie eine Leistungsverbesserung feststellen.  Die IsColumnSet\-Spalte von <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> gibt an, ob eine Spalte eine Spalte mit geringer Dichte ist und einem Spaltensatz angehört.  <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> gibt an, ob eine Spalte eine Spalte mit geringer Dichte ist \(weitere Informationen finden Sie unter [SQL Server\-Schemaauflistungen](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)\).  Weitere Informationen über Spalten mit geringer Dichte finden Sie unter [Verwendung von Spalten mit geringer Dichte](http://go.microsoft.com/fwlink/?LinkId=220037).  
  
-   Für die Microsoft.SqlServer.Types.dll\-Assembly, die die räumlichen Datentypen enthält, wurde ein Upgrade von Version 10.0 auf Version 11.0 vorgenommen.  Anwendungen, die auf diese Assembly verweisen, schlagen möglicherweise fehl.  Weitere Informationen finden Sie unter [Fehlerhafte Änderungen an Funktionen des Datenbankmoduls](http://go.microsoft.com/fwlink/?LinkId=224367).  
  
## ADO.NET Entity Framework  
 Durch [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] werden APIs hinzugefügt, die bei Verwendung von Entity Framework 5.0 neue Szenarien ermöglichen.  Weitere Informationen zu Verbesserungen und Features, die zum Entity Framework 5.0 hinzugefügt wurden, finden Sie unter den folgenden Themen: [Neues](http://go.microsoft.com/fwlink/?LinkID=251106) und [Entity Framework\-Versionen und Versionsverwaltung](http://go.microsoft.com/fwlink/?LinkId=234899).  
  
## Siehe auch  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)   
 [Übersicht über ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)   
 [SQL Server und ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)   
 [What's New in WCF Data Services](http://msdn.microsoft.com/de-de/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)