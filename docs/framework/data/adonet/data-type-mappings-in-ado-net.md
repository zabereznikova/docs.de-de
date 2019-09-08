---
title: Datentypzuordnungen in ADO.NET
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 9c0d19f724c1876f7dac86055bed2ef77ac76a77
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785589"
---
# <a name="data-type-mappings-in-adonet"></a>Datentypzuordnungen in ADO.NET
.NET Framework basiert auf dem allgemeinen Typsystem, das definiert, wie Typen in der Laufzeit deklariert, verwendet und verwaltet werden. Es besteht aus Werttypen und Verweistypen, die alle vom <xref:System.Object>-Basistyp abgeleitet sind. Bei Datenquellen wird über den Datenanbieter auf den Datentyp geschlossen, wenn dieser nicht explizit angegeben ist. Ein <xref:System.Data.DataSet>-Objekt ist z. B. von keiner bestimmten Datenquelle abhängig. Daten in einem `DataSet` werden aus einer Datenquelle abgerufen, und Änderungen werden mithilfe eines `DataAdapter` in die Datenquelle übernommen. Dies bedeutet Folgendes: Wenn `DataAdapter` ein- <xref:System.Data.DataTable> Wert in `DataSet` einem-Wert mit Werten aus einer Datenquelle füllt, `DataTable` sind die resultierenden Datentypen der Spalten in .NET Framework Typen, anstelle von Typen, die für den .NET Framework Datenanbieter spezifisch sind. wird verwendet, um eine Verbindung mit der Datenquelle herzustellen.  
  
 Ebenso, wenn ein `DataReader` einen Wert aus einer Datenquelle zurückgibt, wird der resultierende Wert in einer lokalen Variablen gespeichert, die einen .NET Framework-Typ aufweist. Sowohl für die `Fill` `DataAdapter` -als`Get` auch die-Methode der-Methode wird der .NET Framework-Typ von dem Wert abgeleitet ,dervom.NETFrameworkDatenanbieterzurückgegebenwird.`DataReader`  
  
 Sie können auch die typisierten Zugriffsmethoden des `DataReader` verwenden, wenn Sie den Typ des zurückgegebenen Werts kennen, anstatt den hergeleiteten Datentyp zu verwenden. Typisierte Accessormethoden bieten eine bessere Leistung, indem ein Wert als bestimmter .NET Framework Typ zurückgegeben wird, wodurch die Notwendigkeit zusätzlicher Typkonvertierungen entfällt.  
  
> [!NOTE]
> NULL-Werte für .NET Framework Datenanbieter Datentypen werden `DBNull.Value`durch dargestellt.  
  
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

- [SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)](./sql/sql-server-data-types.md)
- [Konfigurieren von Parametern und Parameterdatentypen](configuring-parameters-and-parameter-data-types.md)
- [Abrufen von Datenbankschemainformationen](retrieving-database-schema-information.md)
- [Allgemeines Typsystem](../../../standard/base-types/common-type-system.md)
- [Typumwandlungs Typen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))
- [Übersicht über ADO.NET](ado-net-overview.md)
