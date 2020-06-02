---
title: Massenkopiervorgänge in SQL Server
description: Erfahren Sie, wie Sie mit der SqlBulkCopy-Klasse verwaltete Code Lösungen schreiben, die große Dateien per Massen Kopiervorgang in Tabellen oder Sichten in SQL Server Datenbanken kopieren.
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: 4f877836aa45efe162cce3c42cb5733f86deab2c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286519"
---
# <a name="bulk-copy-operations-in-sql-server"></a>Massenkopiervorgänge in SQL Server
Microsoft SQL Server enthält ein beliebtes Befehlszeilen-Hilfsprogramm mit dem Namen **bcp** zum schnellen Massenkopieren großer Dateiumfänge in Tabellen oder Ansichten in SQL Server-Datenbanken. Die <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse ermöglicht Ihnen das Schreiben von verwalteten Codelösungen, die eine ähnliche Funktionalität bereitstellen. Es gibt eine Reihe weiterer Verfahren, Daten in eine SQL-Server-Tabelle zu laden (beispielsweise INSERT-Anweisungen), doch bietet <xref:System.Data.SqlClient.SqlBulkCopy> ihnen gegenüber einen erheblichen Leistungsvorteil.  
  
 Die <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse kann nur zum Schreiben von Daten in SQL Server-Tabellen verwendet werden. Die Datenquelle hingegen ist nicht auf SQL Server beschränkt. Es können beliebige Datenquellen verwendet werden, vorausgesetzt die Daten können in eine <xref:System.Data.DataTable>-Instanz geladen oder mit einer <xref:System.Data.IDataReader>-Instanz gelesen werden.  
  
 Die <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse bietet folgende Möglichkeiten:  
  
- Einen einzelnen Massenkopiervorgang  
  
- Mehrere Massenkopiervorgänge  
  
- Einen Massenkopiervorgang innerhalb einer Transaktion  
  
> [!NOTE]
> Wenn Sie .NET Framework, Version 1.1 oder früher, verwenden (bei diesen Versionen wird die <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse nicht unterstützt), können Sie die **BULK INSERT**-Anweisung von Transact-SQL für SQL Server mit dem <xref:System.Data.SqlClient.SqlCommand>-Objekt ausführen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Beispiel für Massen Kopiervorgang](bulk-copy-example-setup.md)  
 In diesem Artikel werden die Tabellen beschrieben, die in den Beispielen für Massenkopiervorgänge verwendet werden, und SQL-Skripts zum Erstellen der Tabellen in der AdventureWorks-Datenbank werden bereitgestellt.  
  
 [Einzelne Massen Kopiervorgänge](single-bulk-copy-operations.md)  
 In diesem Artikel wird das Durchführen einzelner Massenkopiervorgänge für Daten in eine SQL Server-Instanz mithilfe der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse beschrieben und wie der Massenkopiervorgang mithilfe von Transact-SQL-Anweisungen und der <xref:System.Data.SqlClient.SqlCommand>-Klasse durchgeführt werden kann.  
  
 [Mehrere Massen Kopiervorgänge](multiple-bulk-copy-operations.md)  
 Beschreibt das Ausführen mehrerer Massenkopiervorgänge von Daten in eine SQL Server-Instanz mithilfe der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse  
  
 [Transaktionen und Massen Kopiervorgänge](transaction-and-bulk-copy-operations.md)  
 Beschreibt das Ausführen eines Massenkopiervorgangs innerhalb einer Transaktion, einschließlich des Commits oder Rollbacks einer Transaktion  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server und ADO.NET](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
