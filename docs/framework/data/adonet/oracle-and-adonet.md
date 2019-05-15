---
title: Oracle und ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: a8668ee115a3babbdf1ef549a418187d2c5e26b8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583410"
---
# <a name="oracle-and-adonet"></a>Oracle und ADO.NET
> [!NOTE]
>  Die Typen in <xref:System.Data.OracleClient> sind veraltet. Die Typen werden in der aktuellen .NET Framework-Version weiterhin unterstützt, die Unterstützung wird jedoch in einem zukünftigen Release eingestellt. Microsoft empfiehlt, einen anderen Oracle-Anbieter zu verwenden.  
  
 Dieser Abschnitt beschreibt die Funktionen und Verhaltensweisen, die spezifisch für die .NET Framework-Datenanbieter für Oracle sind.  
  
 Die .NET Framework-Datenanbieter für Oracle ermöglicht den Zugriff auf eine Oracle-Datenbank, die mit der Oracle aufrufen-Schnittstelle (OCI) von Oracle-Clientsoftware bereitgestellt. Die Funktionalität des Datenanbieters soll ähnelt der von der .NET Framework-Datenanbieter für SQL Server, OLE DB und ODBC werden.  
  
 Um den .NET Framework-Datenanbieter für Oracle verwenden zu können, muss eine Anwendung verweisen die <xref:System.Data.OracleClient> Namespace wie folgt:  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 Außerdem müssen Sie beim Kompilieren des Codes einen Verweis auf die DLL-Datei hinzufügen. Wenn Sie z. B. ein C#-Programm kompilieren, muss Ihre Befehlszeile Folgendes beinhalten:  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Systemanforderungen](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 Beschreibt die Anforderungen für die Verwendung der .NET Framework-Datenanbieter für Oracle und eine Reihe von Problemen, zu berücksichtigen, dass bei dessen Verwendung beschreibt.  
  
 [Oracle-BFILEs](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 Beschreibt die <xref:System.Data.OracleClient.OracleBFile>-Klasse, die zum Arbeiten mit dem BFILE-Datentyp von Oracle verwendet wird.  
  
 [Oracle-LOBs](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 Beschreibt die <xref:System.Data.OracleClient.OracleLob>-Klasse, die zum Arbeiten mit dem LOB-Datentyp von Oracle verwendet wird.  
  
 [Oracle-REF CURSORs](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 Beschreibt die Unterstützung für den REF CURSOR-Datentyp von Oracle.  
  
 [OracleTypes](../../../../docs/framework/data/adonet/oracletypes.md)  
 Beschreibt Strukturen, die zum Arbeiten mit Oracle-Datentypen verwendet werden können, z. B. <xref:System.Data.OracleClient.OracleNumber> und <xref:System.Data.OracleClient.OracleString>.  
  
 [Oracle-Sequenzen](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 Beschreibt die Unterstützung für das Abrufen der servergenerierten Oracle-Sequenz-Schlüsselwerte.  
  
 [Oracle-Datentypzuordnungen](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 Listet Oracle-Datentypen und ihre Zuordnungen zum <xref:System.Data.OracleClient.OracleDataReader> auf.  
  
 [Verteilte Oracle-Transaktionen](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 Beschreibt, wie das <xref:System.Data.OracleClient.OracleConnection>-Objekt automatisch in einer vorhandenen verteilten Transaktion aufgelistet wird, wenn es ermittelt, dass eine Transaktion aktiv ist.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Sichern von ADO.NET-Anwendungen](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 Beschreibt sichere Codierungstechniken bei der Verwendung von [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
 [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Beschreibt das Erstellen und Verwenden von `DataSets`, typisierten `DataSets`, `DataTables` und `DataViews`.  
  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 Beschreibt das Arbeiten mit Daten in ADO.NET.  
  
 [SQL Server und ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 Beschreibt das Arbeiten mit Funktionen und Funktionalität, die spezifisch für SQL Server sind.  
  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 Beschreibt generische Klassen, mit deren Hilfe in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] anbieterunabhängiger Code geschrieben werden kann.  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
