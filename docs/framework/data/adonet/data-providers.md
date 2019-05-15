---
title: .NET Framework-Datenanbieter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 03a9fc62-2d24-491a-9fe6-d6bdb6dcb131
ms.openlocfilehash: 9fead8a5d54fba7232831bba349f27b7eed4657b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583788"
---
# <a name="net-framework-data-providers"></a>.NET Framework-Datenanbieter
Ein .NET Framework-Datenanbieter wird für die Verbindung mit einer Datenbank, Ausführen von Befehlen und Abrufen von Ergebnissen verwendet. Diese Ergebnisse werden entweder direkt verarbeitet und in einem <xref:System.Data.DataSet> -Objekt platziert, um sie dem Benutzer, kombiniert mit Daten aus mehreren Quellen, bei Bedarf verfügbar zu machen, oder sie werden an eine andere Ebene übergeben. .NET Framework-Datenanbieter sind kompakt und erstellen eine minimale Schicht zwischen der Datenquelle und den Code, Verbessern der Leistung ohne Einbußen bei der Funktionalität.  
  
 Die folgende Tabelle enthält die Datenanbieter, die in .NET Framework enthalten sind.  
  
|.NET Framework-Datenanbieter|Beschreibung|  
|-------------------------------------------------------------------------------|-----------------|  
|.NET Framework-Datenanbieter für SQL Server|Ermöglicht den Datenzugriff für Microsoft SQL Server. Verwendet den <xref:System.Data.SqlClient> -Namespace.|  
|.NET Framework-Datenanbieter für OLE DB|Für Datenquellen, die mit OLE DB verfügbar gemacht werden. Verwendet den <xref:System.Data.OleDb> -Namespace.|  
|.NET Framework-Datenanbieter für ODBC|Für Datenquellen, die mit ODBC verfügbar gemacht werden. Verwendet den <xref:System.Data.Odbc> -Namespace.|  
|.NET Framework-Datenanbieter für Oracle|Für Oracle-Datenquellen. Die .NET Framework-Datenanbieter für Oracle unterstützt Oracle-Clientsoftwareversion 8.1.7 und höher, und verwendet die <xref:System.Data.OracleClient> Namespace.|  
|EntityClient-Anbieter|Stellt Datenzugriff für Entity Data Model (EDM)-Anwendungen bereit. Verwendet den <xref:System.Data.EntityClient> -Namespace.|  
|.NET Framework-Datenanbieter für SQLServer Compact 4.0.|Ermöglicht den Datenzugriff für Microsoft SQL Server Compact 4.0. Verwendet den Namespace [System.Data.SqlServerCe](https://docs.microsoft.com/previous-versions/sql/compact/sql-server-compact-4.0/ec4st0e3(v=vs.100)) .|  
  
## <a name="core-objects-of-net-framework-data-providers"></a>Hauptobjekte von .NET Framework-Datenanbietern  
 In der folgende Tabelle wird beschrieben, die vier Hauptobjekte, die einen .NET Framework-Datenanbieter bilden.  
  
|Object|Beschreibung|  
|------------|-----------------|  
|`Connection`|Stellt eine Verbindung mit einer bestimmten Datenquelle her. Die Basisklasse für alle `Connection` -Objekte ist die <xref:System.Data.Common.DbConnection> -Klasse.|  
|`Command`|Führt einen Befehl für eine Datenquelle aus. Macht `Parameters` verfügbar und kann im Rahmen einer `Transaction` von einer `Connection`aus ausgeführt werden. Die Basisklasse für alle `Command` -Objekte ist die <xref:System.Data.Common.DbCommand> -Klasse.|  
|`DataReader`|Liest einen schreibgeschützten Vorwärtsstream von Daten aus einer Datenquelle. Die Basisklasse für alle `DataReader` -Objekte ist die <xref:System.Data.Common.DbDataReader> -Klasse.|  
|`DataAdapter`|Füllt ein `DataSet` auf und löst Aktualisierungen mit der Datenquelle auf. Die Basisklasse für alle `DataAdapter` -Objekte ist die <xref:System.Data.Common.DbDataAdapter> -Klasse.|  
  
 Zusätzlich zu den in der Tabelle weiter oben in diesem Dokument aufgeführten enthält ein .NET Framework-Datenanbieter auch in der folgenden Tabelle aufgeführten Klassen.  
  
|Object|Beschreibung|  
|------------|-----------------|  
|`Transaction`|Trägt Befehle in Transaktionen an der Datenquelle ein. Die Basisklasse für alle `Transaction` -Objekte ist die <xref:System.Data.Common.DbTransaction> -Klasse. ADO.NET unterstützt auch Transaktionen mit Klassen im <xref:System.Transactions> -Namespace.|  
|`CommandBuilder`|Hilfsobjekt, das automatisch Befehlseigenschaften eines `DataAdapter` erstellt oder Parameterinformationen aus einer gespeicherten Prozedur ableitet und die `Parameters` -Auflistung eines `Command` -Objekts auffüllt. Die Basisklasse für alle `CommandBuilder` -Objekte ist die <xref:System.Data.Common.DbCommandBuilder> -Klasse.|  
|`ConnectionStringBuilder`|Hilfsobjekt, das eine einfache Möglichkeit bietet, den Inhalt von Verbindungszeichenfolgen zu erstellen und zu verwalten, die von den `Connection` -Objekten verwendet werden. Die Basisklasse für alle `ConnectionStringBuilder` -Objekte ist die <xref:System.Data.Common.DbConnectionStringBuilder> -Klasse.|  
|`Parameter`|Definiert Eingabe-, Ausgabe- und Rückgabewertparameter für Befehle und gespeicherte Prozeduren. Die Basisklasse für alle `Parameter` -Objekte ist die <xref:System.Data.Common.DbParameter> -Klasse.|  
|`Exception`|Wird zurückgegeben, wenn in der Datenquelle ein Fehler auftritt. .NET Framework-Datenanbieter lösen Fehler auf dem Client eine .NET Framework-Ausnahme aus. Die Basisklasse für alle `Exception` -Objekte ist die <xref:System.Data.Common.DbException> -Klasse.|  
|`Error`|Macht die Informationen aus einer von einer Datenquelle zurückgegebenen Warnung bzw. einem von einer Datenquelle zurückgegebenen Fehler verfügbar.|  
|`ClientPermission`|Für .NET Framework Data Provider Codezugriffs-Sicherheitsattribute bereitgestellt. Die Basisklasse für alle `ClientPermission` -Objekte ist die <xref:System.Data.Common.DBDataPermission> -Klasse.|  
  
## <a name="net-framework-data-provider-for-sql-server-sqlclient"></a>.NET Framework-Datenanbieter für SQL Server (SqlClient)  
 Die .NET Framework-Datenanbieter für SQL Server (SqlClient) verwendet ein eigenes Protokoll für die Kommunikation mit SQL Server. Es ist nicht sehr umfangreich und leistungsfähig, da sie Zugriff auf eine SQL-Server direkt ohne das Hinzufügen einer Ebene mit OLE DB oder Open Database Connectivity (ODBC) optimiert ist. In der folgende Abbildung steht im Gegensatz zu den .NET Framework-Datenanbieter für SQL Server mit dem .NET Framework-Datenanbieter für OLE DB. Die .NET Framework-Datenanbieter für OLE DB kommuniziert mit einer OLE DB-Datenquelle, die sowohl die OLE DB-Dienstkomponente, die Verbindungs-pooling bereitstellt und Transaktionsdienste sowie das OLE DB-Anbieter für die Datenquelle.  
  
> [!NOTE]
>  Die .NET Framework-Datenanbieter für ODBC werden eine ähnliche Architektur wie die .NET Framework-Datenanbieter für OLE DB besitzt. Es ruft z. B. in eine ODBC-Dienstkomponente.  
  
 ![Datenanbieter](../../../../docs/framework/data/adonet/media/netdataproviders-bpuedev11.gif "NETDataProviders_bpuedev11")  
Vergleich des .NET Framework-Datenanbieters für SQL Server und des .NET Framework-Datenanbieters für OLE DB  
  
 Die .NET Framework-Datenanbieter für SQL Server-Klassen befinden sich in der <xref:System.Data.SqlClient> Namespace.  
  
 Die .NET Framework-Datenanbieter für SQL Server unterstützt sowohl lokale als auch verteilte Transaktionen. Für verteilte Transaktionen, die .NET Framework-Datenanbieter für SQL Server wird standardmäßig automatisch in einer Transaktion eingetragen und ruft Transaktionsdetails von den Windows-Komponentendiensten ab oder <xref:System.Transactions>. Weitere Informationen finden Sie unter [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Im folgenden Codebeispiel wird gezeigt, wie Sie den `System.Data.SqlClient` -Namespace in Anwendungen einbinden können.  
  
```vb  
Imports System.Data.SqlClient  
```  
  
```csharp  
using System.Data.SqlClient;  
```  
  
## <a name="net-framework-data-provider-for-ole-db"></a>.NET Framework-Datenanbieter für OLE DB  
 Die .NET Framework-Datenanbieter für OLE DB (OleDb) verwendet die native OLE DB über COM-Interop Datenzugriff aktivieren. Die .NET Framework-Datenanbieter für OLE DB unterstützt sowohl lokale als auch verteilte Transaktionen. Bei verteilten Transaktionen wird die .NET Framework-Datenanbieter für OLE DB standardmäßig automatisch in einer Transaktion eingetragen, und ruft Transaktionsdetails von den Windows-Komponentendiensten ab. Weitere Informationen finden Sie unter [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 In der folgenden Tabelle werden die Anbieter aufgeführt, die mit [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]getestet wurden.  
  
|Treiber|Anbieter|  
|------------|--------------|  
|SQLOLEDB|Microsoft OLE DB-Anbieter für SQL Server|  
|MSDAORA|Microsoft OLE DB-Anbieter für Oracle|  
|Microsoft.Jet.OLEDB.4.0|OLE DB-Anbieter für Microsoft Jet|  
  
> [!NOTE]
>  Die Verwendung einer Access-Datenbank (Jet-Datenbank) als Datenquelle für Multithread-Anwendungen (z. B. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendungen) wird nicht empfohlen. Wenn Sie Jet als Datenquelle für eine [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung verwenden müssen, müssen Sie sich bewusst sein, dass beim Herstellen von Verbindungen zwischen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendungen und einer Access-Datenbank Verbindungsprobleme auftreten können.  
  
 Die .NET Framework-Datenanbieter für OLE DB unterstützt die OLE DB 2.5-Schnittstellen nicht. OLE DB-Anbieter, die Unterstützung für OLE DB 2.5-Schnittstellen erfordern funktioniert nicht mit dem .NET Framework-Datenanbieter für OLE DB ordnungsgemäß. Dies betrifft auch den Microsoft OLE DB-Anbieter für Exchange und den Microsoft OLE DB-Anbieter für Internet Publishing.  
  
 Die .NET Framework-Datenanbieter für OLE DB funktioniert nicht mit dem OLE DB-Anbieter für ODBC (MSDASQL). Eine ODBC-Datenquelle mit den Zugriff auf [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], verwenden Sie die .NET Framework-Datenanbieter für ODBC.  
  
 .NET Framework-Datenanbieter für OLE DB-Klassen befinden sich in der <xref:System.Data.OleDb> Namespace. Im folgenden Codebeispiel wird gezeigt, wie Sie den `System.Data.OleDb` -Namespace in Anwendungen einbinden können.  
  
```vb  
Imports System.Data.OleDb  
```  
  
```csharp  
using System.Data.OleDb;  
```  
  
## <a name="net-framework-data-provider-for-odbc"></a>.NET Framework-Datenanbieter für ODBC  
 Die .NET Framework-Datenanbieter für ODBC (Odbc) verwendet die systemeigenen ODBC-Treiber-Manager (DM), um Datenzugriff zu ermöglichen. Der ODBC-Datenanbieter unterstützt sowohl lokale als auch verteilte Transaktionen. Bei verteilten Transaktionen trägt sich der ODBC-Datenanbieter standardmäßig automatisch in eine Transaktion ein und ruft Transaktionsdetails von den Windows-Komponentendiensten ab. Weitere Informationen finden Sie unter [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 In der folgenden Tabelle werden die ODBC-Treiber aufgeführt, die mit [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]getestet wurden.  
  
|Treiber|  
|------------|  
|SQL Server|  
|Microsoft ODBC für Oracle|  
|Microsoft Access Driver (*.mdb)|  
  
 .NET Framework-Datenanbieter für ODBC-Klassen befinden sich in der <xref:System.Data.Odbc> Namespace.  
  
 Im folgenden Codebeispiel wird gezeigt, wie Sie den `System.Data.Odbc` -Namespace in Anwendungen einbinden können.  
  
```vb  
Imports System.Data.Odbc  
```  
  
```csharp  
using System.Data.Odbc;  
```  
  
> [!NOTE]
>  Die .NET Framework-Datenanbieter für ODBC erfordert MDAC 2.6 oder höher, und MDAC 2.8 SP1 empfohlen wird. Sie können MDAC 2.8 SP1 aus dem [Developer Center für Datenzugriff und -speicherung](https://go.microsoft.com/fwlink/?linkid=4173)herunterladen.  
  
## <a name="net-framework-data-provider-for-oracle"></a>.NET Framework-Datenanbieter für Oracle  
 Die .NET Framework-Datenanbieter für Oracle (OracleClient) ermöglicht den Datenzugriff auf Oracle-Datenquellen über die Oracle-Clientverbindungssoftware. Der Datenanbieter unterstützt Oracle-Clientsoftware Version 8.1.7 oder höher. Der Datenanbieter unterstützt sowohl lokale als auch verteilte Transaktionen. Weitere Informationen finden Sie unter [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Die .NET Framework-Datenanbieter für Oracle erfordert Oracle-Clientsoftware (Version 8.1.7 oder höher) auf dem System, bevor Sie eine Verbindung mit einer Oracle-Datenquelle herstellen können.  
  
 .NET Framework-Datenanbieter für Oracle-Klassen befinden sich in der <xref:System.Data.OracleClient> Namespace und sind in enthalten die `System.Data.OracleClient.dll` Assembly. Beim Kompilieren einer Anwendung, die den Datenanbieter verwendet, müssen Sie auf die Dateien `System.Data.dll` und `System.Data.OracleClient.dll` verweisen.  
  
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
 Je nach den Entwurf und die Datenquelle für Ihre Anwendung kann es sich bei Ihrer Wahl von .NET Framework-Datenanbieter die Leistung, Funktionalität und Integrität der Anwendung verbessern. In der folgende Tabelle erläutert die Vorteile und Einschränkungen jeder .NET Framework-Datenanbieter.  
  
|Anbieter|Hinweise|  
|--------------|-----------|  
|.NET Framework-Datenanbieter für SQL Server|Empfohlen für Anwendungen der mittleren Ebene, die Microsoft SQL Server verwenden.<br /><br /> Es wird empfohlen, ein-Ebenen-Anwendungen, die Microsoft-Datenbank-Engine (MSDE) oder SQL Server verwenden.<br /><br /> Sollten über die Verwendung von OLE DB-Anbieter für SQL Server (SQLOLEDB) mit dem .NET Framework-Datenanbieter für OLE DB.|  
|.NET Framework-Datenanbieter für OLE DB|Für SQL Server wird die .NET Framework-Datenanbieter für SQL Server anstelle dieses Anbieters empfohlen.<br /><br /> Empfohlen für Anwendungen mit nur einer Ebene, die Microsoft Access-Datenbanken verwenden. Von der Verwendung einer Access-Datenbank für eine Anwendung der mittleren Ebene wird abgeraten.|  
|.NET Framework-Datenanbieter für ODBC|Empfohlen für Anwendungen in der mittleren Ebene und Anwendungen mit nur einer Ebene, die ODBC-Datenquellen verwenden.|  
|.NET Framework-Datenanbieter für Oracle|Empfohlen für Anwendungen in der mittleren Ebene und Anwendungen mit nur einer Ebene, die Oracle-Datenquellen verwenden.|  
  
## <a name="entityclient-provider"></a>EntityClient-Anbieter  
 Der EntityClient-Anbieter wird für den Datenzugriff basierend auf einem Entity Data Model (EDM) verwendet. Im Gegensatz zu anderen .NET Framework-Datenanbietern interagiert er nicht direkt mit einer Datenquelle. Stattdessen kommuniziert er über Entity SQL mit dem zugrunde liegenden Datenanbieter. Weitere Informationen finden Sie unter [EntityClient-Anbieter für Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
