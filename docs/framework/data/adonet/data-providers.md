---
title: .NET Framework-Datenanbieter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 03a9fc62-2d24-491a-9fe6-d6bdb6dcb131
ms.openlocfilehash: f821088375bf1df01e75de5e0c226334baca113f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607538"
---
# <a name="net-framework-data-providers"></a>.NET Framework-Datenanbieter
Mithilfe eines [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieters werden Verbindungen mit einer Datenbank hergestellt, Befehle ausgeführt und Ergebnisse abgerufen. Diese Ergebnisse werden entweder direkt verarbeitet und in einem <xref:System.Data.DataSet> -Objekt platziert, um sie dem Benutzer, kombiniert mit Daten aus mehreren Quellen, bei Bedarf verfügbar zu machen, oder sie werden an eine andere Ebene übergeben. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter sind einfach. Sie erstellen eine Ebene von minimaler Größe zwischen der Datenquelle und dem Code und erhöhen so die Leistung, ohne auf Funktionalität verzichten zu müssen.  
  
 Die folgende Tabelle enthält eine Auflistung der Datenanbieter in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]:  
  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter|Beschreibung|  
|-------------------------------------------------------------------------------|-----------------|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Datenanbieter für SQLServer|Ermöglicht den Datenzugriff für Microsoft SQL Server. Verwendet den <xref:System.Data.SqlClient> -Namespace.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für OLE DB|Für Datenquellen, die mit OLE DB verfügbar gemacht werden. Verwendet den <xref:System.Data.OleDb> -Namespace.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Datenanbieter für ODBC|Für Datenquellen, die mit ODBC verfügbar gemacht werden. Verwendet den <xref:System.Data.Odbc> -Namespace.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Datenanbieter für Oracle|Für Oracle-Datenquellen. Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für Oracle unterstützt Oracle-Clientsoftware der Version 8.1.7 und höher und verwendet den <xref:System.Data.OracleClient> -Namespace.|  
|EntityClient-Anbieter|Stellt Datenzugriff für Entity Data Model (EDM)-Anwendungen bereit. Verwendet den <xref:System.Data.EntityClient> -Namespace.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Datenanbieter für SQLServer Compact 4.0.|Ermöglicht den Datenzugriff für Microsoft SQL Server Compact 4.0. Verwendet den Namespace [System.Data.SqlServerCe](https://docs.microsoft.com/previous-versions/sql/compact/sql-server-compact-4.0/ec4st0e3(v=vs.100)) .|  
  
## <a name="core-objects-of-net-framework-data-providers"></a>Hauptobjekte von .NET Framework-Datenanbietern  
 In der folgenden Tabelle werden die vier Hauptobjekte aufgelistet, aus denen sich ein [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter zusammensetzt.  
  
|Object|Beschreibung|  
|------------|-----------------|  
|`Connection`|Stellt eine Verbindung mit einer bestimmten Datenquelle her. Die Basisklasse für alle `Connection` -Objekte ist die <xref:System.Data.Common.DbConnection> -Klasse.|  
|`Command`|Führt einen Befehl für eine Datenquelle aus. Macht `Parameters` verfügbar und kann im Rahmen einer `Transaction` von einer `Connection`aus ausgeführt werden. Die Basisklasse für alle `Command` -Objekte ist die <xref:System.Data.Common.DbCommand> -Klasse.|  
|`DataReader`|Liest einen schreibgeschützten Vorwärtsstream von Daten aus einer Datenquelle. Die Basisklasse für alle `DataReader` -Objekte ist die <xref:System.Data.Common.DbDataReader> -Klasse.|  
|`DataAdapter`|Füllt ein `DataSet` auf und löst Aktualisierungen mit der Datenquelle auf. Die Basisklasse für alle `DataAdapter` -Objekte ist die <xref:System.Data.Common.DbDataAdapter> -Klasse.|  
  
 Zusätzlich zu den in der Tabelle oben aufgelisteten Hauptklassen enthält ein [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter auch die in der folgenden Tabelle aufgeführten Klassen.  
  
|Object|Beschreibung|  
|------------|-----------------|  
|`Transaction`|Trägt Befehle in Transaktionen an der Datenquelle ein. Die Basisklasse für alle `Transaction` -Objekte ist die <xref:System.Data.Common.DbTransaction> -Klasse. ADO.NET unterstützt auch Transaktionen mit Klassen im <xref:System.Transactions> -Namespace.|  
|`CommandBuilder`|Hilfsobjekt, das automatisch Befehlseigenschaften eines `DataAdapter` erstellt oder Parameterinformationen aus einer gespeicherten Prozedur ableitet und die `Parameters` -Auflistung eines `Command` -Objekts auffüllt. Die Basisklasse für alle `CommandBuilder` -Objekte ist die <xref:System.Data.Common.DbCommandBuilder> -Klasse.|  
|`ConnectionStringBuilder`|Hilfsobjekt, das eine einfache Möglichkeit bietet, den Inhalt von Verbindungszeichenfolgen zu erstellen und zu verwalten, die von den `Connection` -Objekten verwendet werden. Die Basisklasse für alle `ConnectionStringBuilder` -Objekte ist die <xref:System.Data.Common.DbConnectionStringBuilder> -Klasse.|  
|`Parameter`|Definiert Eingabe-, Ausgabe- und Rückgabewertparameter für Befehle und gespeicherte Prozeduren. Die Basisklasse für alle `Parameter` -Objekte ist die <xref:System.Data.Common.DbParameter> -Klasse.|  
|`Exception`|Wird zurückgegeben, wenn in der Datenquelle ein Fehler auftritt. Wenn auf dem Client ein Fehler festgestellt wird, lösen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter eine [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Ausnahme aus. Die Basisklasse für alle `Exception` -Objekte ist die <xref:System.Data.Common.DbException> -Klasse.|  
|`Error`|Macht die Informationen aus einer von einer Datenquelle zurückgegebenen Warnung bzw. einem von einer Datenquelle zurückgegebenen Fehler verfügbar.|  
|`ClientPermission`|Wird für Codezugriffs-Sicherheitsattribute von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbietern bereitgestellt. Die Basisklasse für alle `ClientPermission` -Objekte ist die <xref:System.Data.Common.DBDataPermission> -Klasse.|  
  
## <a name="net-framework-data-provider-for-sql-server-sqlclient"></a>.NET Framework-Datenanbieter für SQL Server (SqlClient)  
 Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für SQL Server (SqlClient) verwendet ein eigenes Protokoll für die Kommunikation mit SQL Server. Es ist nicht sehr umfangreich und leistungsfähig, da sie Zugriff auf eine SQL-Server direkt ohne das Hinzufügen einer Ebene mit OLE DB oder Open Database Connectivity (ODBC) optimiert ist. Die folgende Abbildung stellt die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für SQL Server mit der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für OLE DB. Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für OLE DB kommuniziert mit einer OLE DB-Datenquelle über die OLE DB-Dienstkomponente, die das Verbindungspooling und Transaktionsdienste bereitstellt, und über den OLE DB-Anbieter für die Datenquelle.  
  
> [!NOTE]
>  Die Architektur des [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieters für ODBC ähnelt der des [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieters für OLE DB. So wird z. B. bei beiden eine ODBC-Dienstkomponente aufgerufen.  
  
 ![Datenanbieter](../../../../docs/framework/data/adonet/media/netdataproviders-bpuedev11.gif "NETDataProviders_bpuedev11")  
Vergleich des .NET Framework-Datenanbieters für SQL Server und des .NET Framework-Datenanbieters für OLE DB  
  
 Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für SQL Server-Klassen befinden sich in der <xref:System.Data.SqlClient> Namespace.  
  
 Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für SQL Server unterstützt sowohl lokale als auch verteilte Transaktionen. Für verteilte Transaktionen die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für SQL Server, wird standardmäßig automatisch in einer Transaktion eingetragen, und ruft Transaktionsdetails von den Windows-Komponentendiensten ab oder <xref:System.Transactions>. Weitere Informationen finden Sie unter [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Im folgenden Codebeispiel wird gezeigt, wie Sie den `System.Data.SqlClient` -Namespace in Anwendungen einbinden können.  
  
```vb  
Imports System.Data.SqlClient  
```  
  
```csharp  
using System.Data.SqlClient;  
```  
  
## <a name="net-framework-data-provider-for-ole-db"></a>.NET Framework-Datenanbieter für OLE DB  
 Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für OLE DB (OleDb) ermöglicht den Datenzugriff mithilfe von systemeigenem OLE DB über COM-Interop. Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für OLE DB unterstützt sowohl lokale als auch verteilte Transaktionen. Bei verteilten Transaktionen trägt sich der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für OLE DB standardmäßig automatisch in eine Transaktion ein und ruft Transaktionsdetails von den Windows-Komponentendiensten ab. Weitere Informationen finden Sie unter [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 In der folgenden Tabelle werden die Anbieter aufgeführt, die mit [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]getestet wurden.  
  
|Treiber|Anbieter|  
|------------|--------------|  
|SQLOLEDB|Microsoft OLE DB-Anbieter für SQL Server|  
|MSDAORA|Microsoft OLE DB-Anbieter für Oracle|  
|Microsoft.Jet.OLEDB.4.0|OLE DB-Anbieter für Microsoft Jet|  
  
> [!NOTE]
>  Die Verwendung einer Access-Datenbank (Jet-Datenbank) als Datenquelle für Multithread-Anwendungen (z. B. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendungen) wird nicht empfohlen. Wenn Sie Jet als Datenquelle für eine [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung verwenden müssen, müssen Sie sich bewusst sein, dass beim Herstellen von Verbindungen zwischen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendungen und einer Access-Datenbank Verbindungsprobleme auftreten können.  
  
 Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für OLE DB unterstützt keine OLE DB 2.5-Schnittstellen. OLE DB-Anbieter, die Unterstützung von OLE DB 2.5-Schnittstellen benötigen, funktionieren in Verbindung mit dem [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für OLE DB nicht ordnungsgemäß. Dies betrifft auch den Microsoft OLE DB-Anbieter für Exchange und den Microsoft OLE DB-Anbieter für Internet Publishing.  
  
 Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für OLE DB funktioniert nicht in Verbindung mit dem OLE DB-Anbieter für ODBC (MSDASQL). Wenn Sie mit [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]auf eine ODBC-Datenquelle zugreifen möchten, verwenden Sie den [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für ODBC.  
  
 Die Klassen des[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieters für OLE DB befinden sich im <xref:System.Data.OleDb> -Namespace. Im folgenden Codebeispiel wird gezeigt, wie Sie den `System.Data.OleDb` -Namespace in Anwendungen einbinden können.  
  
```vb  
Imports System.Data.OleDb  
```  
  
```csharp  
using System.Data.OleDb;  
```  
  
## <a name="net-framework-data-provider-for-odbc"></a>.NET Framework-Datenanbieter für ODBC  
 Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für ODBC (Odbc) verwendet für die Bereitstellung des Datenzugriffs den systemeigenen ODBC-Treiber-Manager. Der ODBC-Datenanbieter unterstützt sowohl lokale als auch verteilte Transaktionen. Bei verteilten Transaktionen trägt sich der ODBC-Datenanbieter standardmäßig automatisch in eine Transaktion ein und ruft Transaktionsdetails von den Windows-Komponentendiensten ab. Weitere Informationen finden Sie unter [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 In der folgenden Tabelle werden die ODBC-Treiber aufgeführt, die mit [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]getestet wurden.  
  
|Treiber|  
|------------|  
|SQL Server|  
|Microsoft ODBC für Oracle|  
|Microsoft Access Driver (*.mdb)|  
  
 Die Klassen des[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenbieters für ODBC befinden sich im <xref:System.Data.Odbc> -Namespace.  
  
 Im folgenden Codebeispiel wird gezeigt, wie Sie den `System.Data.Odbc` -Namespace in Anwendungen einbinden können.  
  
```vb  
Imports System.Data.Odbc  
```  
  
```csharp  
using System.Data.Odbc;  
```  
  
> [!NOTE]
>  Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für ODBC erfordert MDAC 2.6 oder höher, wir empfehlen MDAC 2.8 SP1. Sie können MDAC 2.8 SP1 aus dem [Developer Center für Datenzugriff und -speicherung](https://go.microsoft.com/fwlink/?linkid=4173)herunterladen.  
  
## <a name="net-framework-data-provider-for-oracle"></a>.NET Framework-Datenanbieter für Oracle  
 Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für Oracle (OracleClient) ermöglicht den Datenzugriff auf Oracle-Daten mithilfe von Oracle-Clientverbindungssoftware. Der Datenanbieter unterstützt Oracle-Clientsoftware Version 8.1.7 oder höher. Der Datenanbieter unterstützt sowohl lokale als auch verteilte Transaktionen. Weitere Informationen finden Sie unter [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Für die Herstellung einer Verbindung mit der Oracle-Datenquelle benötigt der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für Oracle die Oracle-Clientsoftware (Version 8.1.7 oder höher) im System.  
  
 Die Klassen des[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieters für Oracle befinden sich im <xref:System.Data.OracleClient> -Namespace und sind in der `System.Data.OracleClient.dll` -Assembly enthalten. Beim Kompilieren einer Anwendung, die den Datenanbieter verwendet, müssen Sie auf die Dateien `System.Data.dll` und `System.Data.OracleClient.dll` verweisen.  
  
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
 Abhängig vom Design und der Datenquelle für Ihre Anwendung kann die Auswahl des richtigen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieters dazu beitragen, die Leistung, Effizienz und Integrität Ihrer Anwendung zu verbessern. In der folgenden Tabelle werden die Vorteile und Grenzen der einzelnen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter erläutert.  
  
|Anbieter|Hinweise|  
|--------------|-----------|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Datenanbieter für SQLServer|Empfohlen für Anwendungen der mittleren Ebene, die Microsoft SQL Server verwenden.<br /><br /> Es wird empfohlen, ein-Ebenen-Anwendungen, die Microsoft-Datenbank-Engine (MSDE) oder SQL Server verwenden.<br /><br /> Empfohlen bei Verwendung des OLE DB-Anbieter für SQL Server (SQLOLEDB) mit der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für OLE DB.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für OLE DB|Für SQL Server die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für SQL Server wird empfohlen, anstelle von diesem Anbieter.<br /><br /> Empfohlen für Anwendungen mit nur einer Ebene, die Microsoft Access-Datenbanken verwenden. Von der Verwendung einer Access-Datenbank für eine Anwendung der mittleren Ebene wird abgeraten.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Datenanbieter für ODBC|Empfohlen für Anwendungen in der mittleren Ebene und Anwendungen mit nur einer Ebene, die ODBC-Datenquellen verwenden.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Datenanbieter für Oracle|Empfohlen für Anwendungen in der mittleren Ebene und Anwendungen mit nur einer Ebene, die Oracle-Datenquellen verwenden.|  
  
## <a name="entityclient-provider"></a>EntityClient-Anbieter  
 Der EntityClient-Anbieter wird für den Datenzugriff basierend auf einem Entity Data Model (EDM) verwendet. Im Gegensatz zu anderen .NET Framework-Datenanbietern interagiert er nicht direkt mit einer Datenquelle. Stattdessen kommuniziert er über Entity SQL mit dem zugrunde liegenden Datenanbieter. Weitere Informationen finden Sie unter [EntityClient-Anbieter für Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
