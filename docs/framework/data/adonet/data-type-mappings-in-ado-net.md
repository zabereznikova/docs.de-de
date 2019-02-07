---
title: Datentypzuordnungen in ADO.NET
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 302ccd7b2a05dabc5f13e6f821404a8527951741
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827915"
---
# <a name="data-type-mappings-in-adonet"></a>Datentypzuordnungen in ADO.NET
.NET Framework basiert auf dem allgemeinen Typsystem, das definiert, wie Typen in der Laufzeit deklariert, verwendet und verwaltet werden. Es besteht aus Werttypen und Verweistypen, die alle vom <xref:System.Object>-Basistyp abgeleitet sind. Bei Datenquellen wird über den Datenanbieter auf den Datentyp geschlossen, wenn dieser nicht explizit angegeben ist. Ein <xref:System.Data.DataSet>-Objekt ist z. B. von keiner bestimmten Datenquelle abhängig. Daten in einem `DataSet` werden aus einer Datenquelle abgerufen, und Änderungen werden mithilfe eines `DataAdapter` in die Datenquelle übernommen. Wenn daher ein `DataAdapter`-Objekt eine <xref:System.Data.DataTable> in einem `DataSet` mit Werten aus einer Datenquelle füllt, entsprechen die Datentypen der Spalten in der `DataTable` [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datentypen und nicht speziellen Datentypen des[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieters, der zum Herstellen der Verbindung mit der Datenquelle verwendet wird.  
  
 Wenn ein `DataReader` einen Wert aus einer Datenquelle zurückgibt, wird dieser Wert entsprechend in einer lokalen Variable mit [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typ gespeichert. Sowohl bei den `Fill`-Vorgängen des `DataAdapter` als auch bei den `Get`-Methoden des `DataReader` wird der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typ von dem Wert hergeleitet, der vom [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieter zurückgegeben wird.  
  
 Sie können auch die typisierten Zugriffsmethoden des `DataReader` verwenden, wenn Sie den Typ des zurückgegebenen Werts kennen, anstatt den hergeleiteten Datentyp zu verwenden. Mit typisierten Accessormethoden erzielen Sie eine bessere Leistung, da ein Wert als bestimmter [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typ zurückgegeben wird und somit keine weitere Typkonvertierung erforderlich ist.  
  
> [!NOTE]
>  NULL-Werte werden bei Datentypen des [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieters als `DBNull.Value` dargestellt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [SQL Server-Datentypzuordnungen](../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenzugriffsmethoden für <xref:System.Data.SqlClient> auf.  
  
 [OLE DB-Datentypzuordnungen](../../../../docs/framework/data/adonet/ole-db-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenzugriffsmethoden für <xref:System.Data.OleDb> auf.  
  
 [ODBC-Datentypzuordnungen](../../../../docs/framework/data/adonet/odbc-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenzugriffsmethoden für <xref:System.Data.Odbc> auf.  
  
 [Oracle-Datentypzuordnungen](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 Listet hergeleitete Datentypzuordnungen und Datenzugriffsmethoden für <xref:System.Data.OracleClient> auf.  
  
 [Gleitkommazahlen](../../../../docs/framework/data/adonet/floating-point-numbers.md)  
 Beschreibt Probleme, auf die Entwickler beim Arbeiten mit Gleitkommazahlen häufig stoßen.  
  
## <a name="see-also"></a>Siehe auch
- [SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [Konfigurieren von Parametern und Parameterdatentypen](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [Abrufen von Datenbankschemainformationen](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [Allgemeines Typsystem](../../../../docs/standard/base-types/common-type-system.md)
- [Konvertieren von Typen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
