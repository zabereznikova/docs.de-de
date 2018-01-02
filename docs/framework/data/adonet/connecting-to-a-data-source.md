---
title: Verbinden mit einer Datenquelle in ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 01a7342d6e081bec88aeef2c55461be2d936e4a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Verbinden mit einer Datenquelle in ADO.NET
In ADO.NET verwenden Sie eine **Verbindung** Objekt einer Verbindung mit einer bestimmten Datenquelle erforderlichen Authentifizierungsinformationen in einer Verbindungszeichenfolge angeben. Die **Verbindung** Objekt, die Sie verwenden, hängt vom Typ der Datenquelle.  
  
 Jeder in .NET Framework enthaltene .NET Framework-Datenanbieter enthält ein <xref:System.Data.Common.DbConnection>-Objekt: Der .NET Framework-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbConnection>-Objekt, der .NET Framework-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlConnection>-Objekt, der .NET Framework-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcConnection>-Objekt, und der .NET Framework-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleConnection>-Objekt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Herstellen der Verbindung](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 Beschreibt, wie eine **Verbindung** Objekt zum Herstellen einer Verbindung mit einer Datenquelle.  
  
 [Verbindungsereignisse](../../../../docs/framework/data/adonet/connection-events.md)  
 Beschreibt, wie ein **InfoMessage** Ereignis informationsmeldungen aus einer Datenquelle abgerufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verbindungszeichenfolgen](../../../../docs/framework/data/adonet/connection-strings.md)  
 [Verbindungspooling](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [DataAdapters und DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
