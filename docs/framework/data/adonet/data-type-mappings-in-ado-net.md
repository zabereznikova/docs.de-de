---
title: Datentypzuordnungen in ADO.NET
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 4e85db4732da664848cee2ef48f9a880a86fef18
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583762"
---
# <a name="data-type-mappings-in-adonet"></a>Datentypzuordnungen in ADO.NET
.NET Framework basiert auf dem allgemeinen Typsystem, das definiert, wie Typen in der Laufzeit deklariert, verwendet und verwaltet werden. Es besteht aus Werttypen und Verweistypen, die alle vom <xref:System.Object>-Basistyp abgeleitet sind. Bei Datenquellen wird über den Datenanbieter auf den Datentyp geschlossen, wenn dieser nicht explizit angegeben ist. Ein <xref:System.Data.DataSet>-Objekt ist z. B. von keiner bestimmten Datenquelle abhängig. Daten in einem `DataSet` werden aus einer Datenquelle abgerufen, und Änderungen werden mithilfe eines `DataAdapter` in die Datenquelle übernommen. Das bedeutet, wenn eine `DataAdapter` füllt eine <xref:System.Data.DataTable> in einer `DataSet` mit Werten aus einer Datenquelle, die Datentypen der Spalten in der `DataTable` sind .NET Framework-Typen anstelle der .NET Framework-Datenanbieter für Typen, die wird bei der Herstellung einer Verbindung mit der Datenquelle verwendet werden.  
  
 Ebenso, wenn eine `DataReader` gibt ein Wert aus einer Datenquelle, die sich ergebenden Wert befindet sich in einer lokalen Variablen, die .NET Framework-Typ aufweist. Für beide die `Fill` Vorgänge von der `DataAdapter` und `Get` Methoden der `DataReader`, der .NET Framework-Typ wird abgeleitet aus dem Wert, der von der .NET Framework-Datenanbieter zurückgegeben.  
  
 Sie können auch die typisierten Zugriffsmethoden des `DataReader` verwenden, wenn Sie den Typ des zurückgegebenen Werts kennen, anstatt den hergeleiteten Datentyp zu verwenden. Typisierten Zugriffsmethoden erzielen Sie eine bessere Leistung durch Rückgabe eines Werts als einen bestimmten .NET Framework-Typ, der nicht mehr die weitere typkonvertierung erforderlich ist.  
  
> [!NOTE]
>  Für .NET Framework-Datenanbieters NULL-Werte werden durch dargestellt `DBNull.Value`.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [SQL Server-Datentypzuordnungen](../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.SqlClient> auf.  
  
 [OLE DB-Datentypzuordnungen](../../../../docs/framework/data/adonet/ole-db-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.OleDb> auf.  
  
 [ODBC-Datentypzuordnungen](../../../../docs/framework/data/adonet/odbc-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.Odbc> auf.  
  
 [Oracle-Datentypzuordnungen](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenaccessormethoden für <xref:System.Data.OracleClient> auf.  
  
 [Gleitkommazahlen](../../../../docs/framework/data/adonet/floating-point-numbers.md)  
 Beschreibt Probleme, auf die Entwickler beim Arbeiten mit Gleitkommazahlen häufig stoßen.  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [Konfigurieren von Parametern und Parameterdatentypen](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [Abrufen von Datenbankschemainformationen](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [Allgemeines Typsystem](../../../../docs/standard/base-types/common-type-system.md)
- [Konvertieren von Typen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
