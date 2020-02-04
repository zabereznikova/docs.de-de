---
title: Herstellen der Verbindung mit einer Datenquelle
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 84dc15c0965b7ac8209bd9115d611162e57d6dda
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980248"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Verbinden mit einer Datenquelle in ADO.NET
In ADO.NET verwenden Sie ein **Verbindungs** Objekt, um eine Verbindung mit einer bestimmten Datenquelle herzustellen, indem Sie die erforderlichen Authentifizierungsinformationen in einer Verbindungs Zeichenfolge bereitstellen. Welches **Verbindungs** Objekt Sie verwenden, hängt vom Typ der Datenquelle ab.  
  
 Jeder in .NET Framework enthaltene .NET Framework-Datenanbieter enthält ein <xref:System.Data.Common.DbConnection>-Objekt: Der .NET Framework-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbConnection>-Objekt, der .NET Framework-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlConnection>-Objekt, der .NET Framework-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcConnection>-Objekt, und der .NET Framework-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleConnection>-Objekt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Herstellen der Verbindung](establishing-the-connection.md)  
 Beschreibt, wie ein **Verbindungs** Objekt verwendet wird, um eine Verbindung mit einer Datenquelle herzustellen.  
  
 [Verbindungsereignisse](connection-events.md)  
 Beschreibt, wie ein **infomess** -Ereignis zum Abrufen von Informationsmeldungen aus einer Datenquelle verwendet wird.  
  
## <a name="see-also"></a>Siehe auch

- [Verbindungszeichenfolgen](connection-strings.md)
- [Verbindungspooling](connection-pooling.md)
- [Befehle und Parameter](commands-and-parameters.md)
- [DataAdapters und DataReaders](dataadapters-and-datareaders.md)
- [Transaktionen und Parallelität](transactions-and-concurrency.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
