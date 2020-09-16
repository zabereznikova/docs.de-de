---
title: Datentypzuordnungen
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 065a9dcb5e03c784c5dec9ffbe6a3153aead9e3c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554709"
---
# <a name="data-type-mappings-in-adonet"></a>Datentypzuordnungen in ADO.NET
.NET Framework basiert auf dem allgemeinen Typsystem, das definiert, wie Typen in der Laufzeit deklariert, verwendet und verwaltet werden. Es besteht aus Werttypen und Verweistypen, die alle vom <xref:System.Object>-Basistyp abgeleitet sind. Bei Datenquellen wird über den Datenanbieter auf den Datentyp geschlossen, wenn dieser nicht explizit angegeben ist. Ein <xref:System.Data.DataSet>-Objekt ist z. B. von keiner bestimmten Datenquelle abhängig. Daten in einem `DataSet` werden aus einer Datenquelle abgerufen, und Änderungen werden mithilfe eines `DataAdapter` in die Datenquelle übernommen. Dies bedeutet Folgendes: Wenn ein- `DataAdapter` <xref:System.Data.DataTable> Wert in einer `DataSet` mit Werten aus einer Datenquelle füllt, sind die resultierenden Datentypen der Spalten in `DataTable` .NET Framework Typen, anstelle von Typen, die für den .NET Framework Datenanbieter spezifisch sind, der zum Herstellen der Verbindung mit der Datenquelle verwendet wird.  
  
 Ebenso, wenn ein einen `DataReader` Wert aus einer Datenquelle zurückgibt, wird der resultierende Wert in einer lokalen Variablen gespeichert, die einen .NET Framework-Typ aufweist. Sowohl für die `Fill` `DataAdapter` -als auch die- `Get` Methode der-Methode `DataReader` wird der .NET Framework-Typ von dem Wert abgeleitet, der vom .NET Framework Datenanbieter zurückgegeben wird.  
  
 Sie können auch die typisierten Zugriffsmethoden des `DataReader` verwenden, wenn Sie den Typ des zurückgegebenen Werts kennen, anstatt den hergeleiteten Datentyp zu verwenden. Typisierte Accessormethoden bieten eine bessere Leistung, indem ein Wert als bestimmter .NET Framework Typ zurückgegeben wird, wodurch die Notwendigkeit zusätzlicher Typkonvertierungen entfällt.  
  
> [!NOTE]
> NULL-Werte für .NET Framework Datenanbieter Datentypen werden durch dargestellt `DBNull.Value` .  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [SQL Server-Datentypzuordnungen](sql-server-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.SqlClient> auf.  
  
 [OLE DB-Datentypzuordnungen](ole-db-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.OleDb> auf.  
  
 [ODBC-Datentypzuordnungen](odbc-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.Odbc> auf.  
  
 [Oracle-Datentypzuordnungen](oracle-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.OracleClient> auf.  
  
 [Gleitkommazahlen](floating-point-numbers.md)  
 Beschreibt Probleme, auf die Entwickler beim Arbeiten mit Gleitkommazahlen häufig stoßen.  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server-Datentypen und ADO.net](./sql/sql-server-data-types.md)
- [Konfigurieren von Parametern und Parameterdatentypen](configuring-parameters-and-parameter-data-types.md)
- [Abrufen von Datenbankschemainformationen](retrieving-database-schema-information.md)
- [Allgemeines Typsystem](../../../standard/base-types/common-type-system.md)
- [Typumwandlungs Typen](/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))
- [Übersicht über ADO.NET](ado-net-overview.md)
