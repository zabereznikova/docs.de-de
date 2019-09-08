---
title: Massenkopiervorgänge in SQL Server
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: ae97bcdd6776d573cf9e523133c2c00a42c273bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782527"
---
# <a name="bulk-copy-operations-in-sql-server"></a>Massenkopiervorgänge in SQL Server
Microsoft SQL Server enthält ein beliebtes Befehlszeilen-Hilfsprogramm mit dem Namen **bcp** für das schnelle Massen Kopieren großer Dateien in Tabellen oder Sichten in SQL Server Datenbanken. Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Sie verwaltete Codelösungen schreiben, durch die ähnliche Funktionen bereitgestellt werden. Es stehen auch andere Möglichkeiten zum Laden von Daten in eine SQL Server-Tabelle zur Verfügung (z. B. INSERT-Anweisungen), <xref:System.Data.SqlClient.SqlBulkCopy> weist diesen gegenüber jedoch einen deutlichen Leistungsvorteil auf.  
  
 Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Daten nur in SQL Server-Tabellen geschrieben werden. Die Datenquelle hingegen ist nicht auf SQL Server beschränkt. Es können beliebige Datenquellen verwendet werden, vorausgesetzt die Daten können in eine <xref:System.Data.DataTable>-Instanz geladen oder mit einer <xref:System.Data.IDataReader>-Instanz gelesen werden.  
  
 Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Sie folgende Vorgänge ausführen:  
  
- Einzelne Massenkopiervorgänge  
  
- Mehrere Massenkopiervorgänge  
  
- Massenkopiervorgänge innerhalb von Transaktionen  
  
> [!NOTE]
> Wenn Sie .NET Framework Version 1,1 oder früher verwenden (die die <xref:System.Data.SqlClient.SqlBulkCopy> -Klasse nicht unterstützt), können Sie die SQL Server Transact-SQL- **Bulk Insert** - <xref:System.Data.SqlClient.SqlCommand> Anweisung mit dem-Objekt ausführen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Einrichtung der Massenkopierbeispiele](bulk-copy-example-setup.md)  
 Beschreibt die in den Beispielen für Massenkopiervorgänge verwendeten Tabellen und stellt SQL-Skripts zum Erstellen der Tabellen in der AdventureWorks-Datenbank bereit.  
  
 [Einzelne Massenkopiervorgänge](single-bulk-copy-operations.md)  
 Beschreibt die Durchführung eines einzelnen Massenkopiervorgangs für Daten in eine Instanz von SQL Server unter Verwendung der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse sowie die Durchführung des Massenkopiervorgangs mithilfe von Transact-SQL-Anweisungen und der <xref:System.Data.SqlClient.SqlCommand>-Klasse.  
  
 [Mehrere Massenkopiervorgänge](multiple-bulk-copy-operations.md)  
 Beschreibt die Durchführung mehrerer Massenkopiervorgänge in eine Instanz von SQL Server unter Verwendung der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse.  
  
 [Transaktionen und Massenkopiervorgänge](transaction-and-bulk-copy-operations.md)  
 Beschreibt die Durchführung eines Massenkopiervorgangs innerhalb einer Transaktion, einschließlich des Ausführens eines Commit oder Rollback für diese Transaktion.  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server und ADO.NET](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
