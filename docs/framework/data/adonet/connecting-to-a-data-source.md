---
title: Herstellen einer Verbindung mit einer Datenquelle
deescription: Learn about Connection objects, used to connect to data sources in ADO.NET. The Connection object you choose depends on the type of data source.
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: a14fe179cf2fc8714a54e52252c53bd71346cad3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287076"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Verbinden mit einer Datenquelle in ADO.NET

In ADO.NET verwenden Sie ein **Verbindungs** Objekt, um eine Verbindung mit einer bestimmten Datenquelle herzustellen, indem Sie die erforderlichen Authentifizierungsinformationen in einer Verbindungs Zeichenfolge bereitstellen. Welches **Verbindungs** Objekt Sie verwenden, hängt vom Typ der Datenquelle ab.  
  
 Jeder in .NET Framework enthaltene .NET Framework-Datenanbieter enthält ein <xref:System.Data.Common.DbConnection>-Objekt: Der .NET Framework-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbConnection>-Objekt, der .NET Framework-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlConnection>-Objekt, der .NET Framework-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcConnection>-Objekt, und der .NET Framework-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleConnection>-Objekt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Herstellen der Verbindung](establishing-the-connection.md)\
 Beschreibt, wie ein **Verbindungs** Objekt verwendet wird, um eine Verbindung mit einer Datenquelle herzustellen.  
  
 [Verbindungs Ereignisse](connection-events.md)\
 Beschreibt, wie ein **infomess** -Ereignis zum Abrufen von Informationsmeldungen aus einer Datenquelle verwendet wird.  
  
## <a name="see-also"></a>Siehe auch

- [Verbindungs Zeichenfolgen](connection-strings.md)
- [Verbindungspooling](connection-pooling.md)
- [Befehle und Parameter](commands-and-parameters.md)
- ["DataAdapters" und "DataReaders"](dataadapters-and-datareaders.md)
- [Transaktionen und Parallelität](transactions-and-concurrency.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
