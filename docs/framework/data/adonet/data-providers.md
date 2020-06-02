---
title: .NET Framework-Datenanbieter
description: Erfahren Sie, wie ein .NET Framework Datenanbieter zum Herstellen einer Verbindung mit einer Datenbank, zum Ausführen von Befehlen und zum Abrufen von Ergebnissen in ADO.NET verwendet wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 03a9fc62-2d24-491a-9fe6-d6bdb6dcb131
ms.openlocfilehash: 2d4c513b7a4b0e111f2b7e7384c6ee4970d5665f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286998"
---
# <a name="net-framework-data-providers"></a>.NET Framework-Datenanbieter
Ein .NET Framework Datenanbieter wird zum Herstellen einer Verbindung mit einer Datenbank, zum Ausführen von Befehlen und zum Abrufen von Ergebnissen verwendet. Diese Ergebnisse werden entweder direkt verarbeitet und in einem <xref:System.Data.DataSet> -Objekt platziert, um sie dem Benutzer, kombiniert mit Daten aus mehreren Quellen, bei Bedarf verfügbar zu machen, oder sie werden an eine andere Ebene übergeben. .NET Framework Datenanbieter sind einfach, und Sie erstellen eine minimale Ebene zwischen der Datenquelle und dem Code und erhöhen so die Leistung, ohne die Funktionalität zu beeinträchtigen.  
  
 In der folgenden Tabelle sind die Datenanbieter aufgelistet, die in der .NET Framework enthalten sind.  
  
|.NET Framework-Datenanbieter|BESCHREIBUNG|  
|-------------------------------------------------------------------------------|-----------------|  
|.NET Framework-Datenanbieter für SQL Server|Ermöglicht den Datenzugriff für Microsoft SQL Server. Verwendet den <xref:System.Data.SqlClient> -Namespace.|  
|.NET Framework-Datenanbieter für OLE DB|Für Datenquellen, die mit OLE DB verfügbar gemacht werden. Verwendet den <xref:System.Data.OleDb> -Namespace.|  
|.NET Framework-Datenanbieter für ODBC|Für Datenquellen, die mit ODBC verfügbar gemacht werden. Verwendet den <xref:System.Data.Odbc> -Namespace.|  
|.NET Framework-Datenanbieter für Oracle|Für Oracle-Datenquellen. Die .NET Framework Datenanbieter für Oracle unterstützt Oracle-Client Softwareversion 8.1.7 und höher und verwendet den- <xref:System.Data.OracleClient> Namespace.|  
|EntityClient-Anbieter|Stellt Datenzugriff für Entity Data Model (EDM)-Anwendungen bereit. Verwendet den <xref:System.Data.EntityClient> -Namespace.|  
|.NET Framework Datenanbieter für SQL Server Compact 4,0.|Bietet Datenzugriff für Microsoft SQL Server Compact 4,0. Verwendet den Namespace [System.Data.SqlServerCe](https://docs.microsoft.com/previous-versions/sql/compact/sql-server-compact-4.0/ec4st0e3(v=vs.100)) .|  
  
## <a name="core-objects-of-net-framework-data-providers"></a>Hauptobjekte von .NET Framework-Datenanbietern  
 In der folgenden Tabelle werden die vier Hauptobjekte, aus denen ein .NET Framework Datenanbieter besteht, beschrieben.  
  
|Object|BESCHREIBUNG|  
|------------|-----------------|  
|`Connection`|Stellt eine Verbindung mit einer bestimmten Datenquelle her. Die Basisklasse für alle `Connection` -Objekte ist die <xref:System.Data.Common.DbConnection> -Klasse.|  
|`Command`|Führt einen Befehl für eine Datenquelle aus. Macht `Parameters` verfügbar und kann im Rahmen einer `Transaction` von einer `Connection`aus ausgeführt werden. Die Basisklasse für alle `Command` -Objekte ist die <xref:System.Data.Common.DbCommand> -Klasse.|  
|`DataReader`|Liest einen schreibgeschützten Vorwärtsstream von Daten aus einer Datenquelle. Die Basisklasse für alle `DataReader` -Objekte ist die <xref:System.Data.Common.DbDataReader> -Klasse.|  
|`DataAdapter`|Füllt ein `DataSet` auf und löst Aktualisierungen mit der Datenquelle auf. Die Basisklasse für alle `DataAdapter` -Objekte ist die <xref:System.Data.Common.DbDataAdapter> -Klasse.|  
  
 Zusätzlich zu den in der Tabelle weiter oben in diesem Dokument aufgeführten Kernklassen enthält ein .NET Framework Datenanbieter auch die in der folgenden Tabelle aufgeführten Klassen.  
  
|Object|BESCHREIBUNG|  
|------------|-----------------|  
|`Transaction`|Trägt Befehle in Transaktionen an der Datenquelle ein. Die Basisklasse für alle `Transaction` -Objekte ist die <xref:System.Data.Common.DbTransaction> -Klasse. ADO.NET unterstützt auch Transaktionen mit Klassen im <xref:System.Transactions> -Namespace.|  
|`CommandBuilder`|Hilfsobjekt, das automatisch Befehlseigenschaften eines `DataAdapter` erstellt oder Parameterinformationen aus einer gespeicherten Prozedur ableitet und die `Parameters` -Auflistung eines `Command` -Objekts auffüllt. Die Basisklasse für alle `CommandBuilder` -Objekte ist die <xref:System.Data.Common.DbCommandBuilder> -Klasse.|  
|`ConnectionStringBuilder`|Hilfsobjekt, das eine einfache Möglichkeit bietet, den Inhalt von Verbindungszeichenfolgen zu erstellen und zu verwalten, die von den `Connection` -Objekten verwendet werden. Die Basisklasse für alle `ConnectionStringBuilder` -Objekte ist die <xref:System.Data.Common.DbConnectionStringBuilder> -Klasse.|  
|`Parameter`|Definiert Eingabe-, Ausgabe- und Rückgabewertparameter für Befehle und gespeicherte Prozeduren. Die Basisklasse für alle `Parameter` -Objekte ist die <xref:System.Data.Common.DbParameter> -Klasse.|  
|`Exception`|Wird zurückgegeben, wenn in der Datenquelle ein Fehler auftritt. Für einen Fehler, der auf dem Client aufgetreten ist, lösen .NET Framework Datenanbieter eine .NET Framework-Ausnahme aus. Die Basisklasse für alle `Exception` -Objekte ist die <xref:System.Data.Common.DbException> -Klasse.|  
|`Error`|Macht die Informationen aus einer von einer Datenquelle zurückgegebenen Warnung bzw. einem von einer Datenquelle zurückgegebenen Fehler verfügbar.|  
|`ClientPermission`|Wird für .NET Framework-Datenanbieter Code Zugriffs-Sicherheits Attribute bereitgestellt. Die Basisklasse für alle `ClientPermission` -Objekte ist die <xref:System.Data.Common.DBDataPermission> -Klasse.|  
  
## <a name="net-framework-data-provider-for-sql-server-sqlclient"></a>.NET Framework-Datenanbieter für SQL Server (SqlClient)  
 Die .NET Framework Datenanbieter für SQL Server (SqlClient) verwendet für die Kommunikation mit SQL Server ein eigenes Protokoll. Es ist einfach und führt eine gute Leistung aus, da es für den direkten Zugriff auf eine SQL Server optimiert ist, ohne eine OLE DB oder Open Database Connectivity (ODBC)-Ebene hinzuzufügen. In der folgenden Abbildung wird der .NET Framework Datenanbieter für SQL Server mit dem .NET Framework Datenanbieter für OLE DB gegen überstehen. Die .NET Framework Datenanbieter für OLE DB über die OLE DB-Dienst Komponente, die Verbindungspooling und Transaktionsdienste bereitstellt, und den OLE DB Anbieter für die Datenquelle mit einer OLE DB Datenquelle kommuniziert.  
  
> [!NOTE]
> Der .NET Framework Datenanbieter für ODBC verfügt über eine ähnliche Architektur wie der .NET Framework Datenanbieter für OLE DB. Beispielsweise wird eine ODBC-Dienst Komponente aufgerufen.  
  
 ![Datenanbieter](./media/netdataproviders-bpuedev11.gif "NETDataProviders_bpuedev11")  
Vergleich des .NET Framework-Datenanbieters für SQL Server und des .NET Framework-Datenanbieters für OLE DB  
  
 Die .NET Framework Datenanbieter für SQL Server-Klassen befinden sich im- <xref:System.Data.SqlClient> Namespace.  
  
 Der .NET Framework Datenanbieter für SQL Server unterstützt sowohl lokale als auch verteilte Transaktionen. Bei verteilten Transaktionen trägt die .NET Framework Datenanbieter für SQL Server standardmäßig automatisch in eine Transaktion ein und ruft Transaktionsdetails von den Windows-Komponenten Diensten oder ab <xref:System.Transactions> . Weitere Informationen finden Sie unter [Transaktionen und](transactions-and-concurrency.md)Parallelität.  
  
 Im folgenden Codebeispiel wird gezeigt, wie Sie den `System.Data.SqlClient` -Namespace in Anwendungen einbinden können.  
  
```vb  
Imports System.Data.SqlClient  
```  
  
```csharp  
using System.Data.SqlClient;  
```  
  
## <a name="net-framework-data-provider-for-ole-db"></a>.NET Framework-Datenanbieter für OLE DB  
 Der .NET Framework Datenanbieter für OLE DB (OleDb) verwendet Native OLE DB durch COM-Interop, um den Datenzugriff zu ermöglichen. Der .NET Framework Datenanbieter für OLE DB unterstützt sowohl lokale als auch verteilte Transaktionen. Bei verteilten Transaktionen trägt die .NET Framework Datenanbieter für OLE DB standardmäßig automatisch in eine Transaktion ein und ruft Transaktionsdetails von den Windows-Komponenten Diensten ab. Weitere Informationen finden Sie unter [Transaktionen und](transactions-and-concurrency.md)Parallelität.  
  
 In der folgenden Tabelle sind die Anbieter aufgeführt, die mit ADO.net getestet wurden.  
  
|Treiber|Anbieter|  
|------------|--------------|  
|SQLOLEDB|Microsoft OLE DB-Anbieter für SQL Server|  
|MSDAORA|Microsoft OLE DB-Anbieter für Oracle|  
|Microsoft.Jet.OLEDB.4.0|OLE DB-Anbieter für Microsoft Jet|  
  
> [!NOTE]
> Die Verwendung einer Access-Datenbank (Jet) als Datenquelle für Multithreadanwendungen (z. b. ASP.NET-Anwendungen) wird nicht empfohlen. Wenn Sie Jet als Datenquelle für eine ASP.NET-Anwendung verwenden müssen, stellen Sie fest, dass ASP.NET-Anwendungen, die eine Verbindung mit einer Access-Datenbank herstellen, Verbindungsprobleme auftreten können.  
  
 Die .NET Framework Datenanbieter für OLE DB unterstützt keine Schnittstellen der OLE DB, Version 2,5. OLE DB Anbieter, die Unterstützung für OLE DB 2,5-Schnittstellen benötigen, funktionieren mit dem .NET Framework Datenanbieter für OLE DB nicht ordnungsgemäß. Dies betrifft auch den Microsoft OLE DB-Anbieter für Exchange und den Microsoft OLE DB-Anbieter für Internet Publishing.  
  
 Die .NET Framework Datenanbieter für OLE DB funktioniert nicht mit dem OLE DB Anbieter für ODBC (MSDASQL). Verwenden Sie für den Zugriff auf eine ODBC-Datenquelle mithilfe von ADO.net die .NET Framework-Datenanbieter für ODBC.  
  
 .NET Framework Datenanbieter für OLE DB-Klassen befinden sich im- <xref:System.Data.OleDb> Namespace. Im folgenden Codebeispiel wird gezeigt, wie Sie den `System.Data.OleDb` -Namespace in Anwendungen einbinden können.  
  
```vb  
Imports System.Data.OleDb  
```  
  
```csharp  
using System.Data.OleDb;  
```  
  
## <a name="net-framework-data-provider-for-odbc"></a>.NET Framework-Datenanbieter für ODBC  
 Der .NET Framework Datenanbieter für ODBC (ODBC) verwendet den systemeigenen ODBC-Treiber-Manager (DM), um den Datenzugriff zu ermöglichen. Der ODBC-Datenanbieter unterstützt sowohl lokale als auch verteilte Transaktionen. Bei verteilten Transaktionen trägt sich der ODBC-Datenanbieter standardmäßig automatisch in eine Transaktion ein und ruft Transaktionsdetails von den Windows-Komponentendiensten ab. Weitere Informationen finden Sie unter [Transaktionen und](transactions-and-concurrency.md)Parallelität.  
  
 In der folgenden Tabelle sind die ODBC-Treiber aufgeführt, die mit ADO.net getestet wurden.  
  
|Treiber|  
|------------|  
|SQL Server|  
|Microsoft ODBC für Oracle|  
|Microsoft Access Driver (*.mdb)|  
  
 .NET Framework Datenanbieter für ODBC-Klassen befinden sich im- <xref:System.Data.Odbc> Namespace.  
  
 Im folgenden Codebeispiel wird gezeigt, wie Sie den `System.Data.Odbc` -Namespace in Anwendungen einbinden können.  
  
```vb  
Imports System.Data.Odbc  
```  
  
```csharp  
using System.Data.Odbc;  
```  
  
> [!NOTE]
> Die .NET Framework Datenanbieter für ODBC erfordert MDAC 2,6 oder höher, und MDAC 2,8 SP1 wird empfohlen. Sie können MDAC 2,8 SP1 aus dem [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=5793)herunterladen.
  
## <a name="net-framework-data-provider-for-oracle"></a>.NET Framework-Datenanbieter für Oracle  
 Der .NET Framework Datenanbieter für Oracle (OracleClient) ermöglicht den Datenzugriff auf Oracle-Datenquellen über Oracle-Clientkonnektivitätssoftware. Der Datenanbieter unterstützt Oracle-Clientsoftware Version 8.1.7 oder höher. Der Datenanbieter unterstützt sowohl lokale als auch verteilte Transaktionen. Weitere Informationen finden Sie unter [Transaktionen und](transactions-and-concurrency.md)Parallelität.  
  
 Die .NET Framework Datenanbieter für Oracle erfordert eine Oracle-Client Software (Version 8.1.7 oder eine höhere Version) im System, bevor Sie eine Verbindung mit einer Oracle-Datenquelle herstellen können.  
  
 .NET Framework Datenanbieter für Oracle-Klassen befinden sich im <xref:System.Data.OracleClient> -Namespace und sind in der- `System.Data.OracleClient.dll` Assembly enthalten. Beim Kompilieren einer Anwendung, die den Datenanbieter verwendet, müssen Sie auf die Dateien `System.Data.dll` und `System.Data.OracleClient.dll` verweisen.  
  
 Im folgenden Codebeispiel wird gezeigt, wie Sie den `System.Data.OracleClient` -Namespace in Anwendungen einbinden können.  
  
```vb  
Imports System.Data  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data;  
using System.Data.OracleClient;  
```  
  
## <a name="choosing-a-net-framework-data-provider"></a>Auswählen eines .NET Framework-Datenanbieters  
 Abhängig vom Entwurf und der Datenquelle für Ihre Anwendung kann die Auswahl des .NET Framework Datenanbieters die Leistung, die Fähigkeit und die Integrität Ihrer Anwendung verbessern. In der folgenden Tabelle werden die Vorteile und Einschränkungen der einzelnen .NET Framework-Datenanbieter erläutert.  
  
|Anbieter|Notizen|  
|--------------|-----------|  
|.NET Framework-Datenanbieter für SQL Server|Empfohlen für Anwendungen der mittleren Ebene, die Microsoft SQL Server verwenden.<br /><br /> Empfohlen für Anwendungen mit nur einer Ebene, die Microsoft Datenbank-Engine (MSDE) oder SQL Server verwenden.<br /><br /> Es wird empfohlen, den OLE DB Anbieter für SQL Server (SQLOLEDB) mit dem .NET Framework Datenanbieter für OLE DB zu verwenden.|  
|.NET Framework-Datenanbieter für OLE DB|Für SQL Server wird anstelle dieses Anbieters die .NET Framework Datenanbieter für SQL Server empfohlen.<br /><br /> Empfohlen für Anwendungen mit nur einer Ebene, die Microsoft Access-Datenbanken verwenden. Von der Verwendung einer Access-Datenbank für eine Anwendung der mittleren Ebene wird abgeraten.|  
|.NET Framework-Datenanbieter für ODBC|Empfohlen für Anwendungen in der mittleren Ebene und Anwendungen mit nur einer Ebene, die ODBC-Datenquellen verwenden.|  
|.NET Framework-Datenanbieter für Oracle|Empfohlen für Anwendungen in der mittleren Ebene und Anwendungen mit nur einer Ebene, die Oracle-Datenquellen verwenden.|  
  
## <a name="entityclient-provider"></a>EntityClient-Anbieter  
 Der EntityClient-Anbieter wird für den Datenzugriff basierend auf einem Entity Data Model (EDM) verwendet. Im Gegensatz zu anderen .NET Framework-Datenanbietern interagiert er nicht direkt mit einer Datenquelle. Stattdessen kommuniziert er über Entity SQL mit dem zugrunde liegenden Datenanbieter. Weitere Informationen finden Sie unter [EntityClient-Anbieter für das Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über ADO.NET](ado-net-overview.md)
- [Abrufen und Ändern von Daten in ADO.NET](retrieving-and-modifying-data.md)
