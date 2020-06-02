---
title: Oracle und ADO.NET
description: Erfahren Sie mehr über Features und Verhalten der .NET Framework Datenanbieter für Oracle, die den Zugriff auf eine Oracle-Datenbank mithilfe der Oracle-Benutzeroberfläche ermöglicht.
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 8757352a7444fad802ea88ba58e0fe643c86cbb8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286688"
---
# <a name="oracle-and-adonet"></a>Oracle und ADO.NET
> [!NOTE]
> Die Typen in <xref:System.Data.OracleClient> sind veraltet. Die Typen werden in der aktuellen .NET Framework-Version weiterhin unterstützt, die Unterstützung wird jedoch in einem zukünftigen Release eingestellt. Microsoft empfiehlt, einen anderen Oracle-Anbieter zu verwenden.  
  
 In diesem Abschnitt werden Funktionen und Verhaltensweisen beschrieben, die für die .NET Framework Datenanbieter für Oracle spezifisch sind.  
  
 Der .NET Framework Datenanbieter für Oracle ermöglicht den Zugriff auf eine Oracle-Datenbank mithilfe von OCI (Oracle callinterface), wie von der Oracle-Client Software bereitgestellt. Die Funktionalität des Datenanbieters ist so konzipiert, dass Sie mit der .NET Framework Datenanbieter für SQL Server, OLE DB und ODBC vergleichbar ist.  
  
 Um die .NET Framework Datenanbieter für Oracle zu verwenden, muss eine Anwendung wie folgt auf den- <xref:System.Data.OracleClient> Namespace verweisen:  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 Außerdem müssen Sie beim Kompilieren des Codes einen Verweis auf die DLL-Datei hinzufügen. Wenn Sie z. B. ein C#-Programm kompilieren, muss Ihre Befehlszeile Folgendes beinhalten:  
  
```console
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Systemanforderungen](system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 Beschreibt die Anforderungen für die Verwendung der .NET Framework Datenanbieter für Oracle und beschreibt eine Reihe von Problemen, die bei der Verwendung von zu beachten sind.  
  
 [Oracle-BFILEs](oracle-bfiles.md)  
 Beschreibt die <xref:System.Data.OracleClient.OracleBFile>-Klasse, die zum Arbeiten mit dem BFILE-Datentyp von Oracle verwendet wird.  
  
 [Oracle-LOBs](oracle-lobs.md)  
 Beschreibt die <xref:System.Data.OracleClient.OracleLob>-Klasse, die zum Arbeiten mit dem LOB-Datentyp von Oracle verwendet wird.  
  
 [Oracle-REF CURSORs](oracle-ref-cursors.md)  
 Beschreibt die Unterstützung für den REF CURSOR-Datentyp von Oracle.  
  
 [OracleTypes](oracletypes.md)  
 Beschreibt Strukturen, die zum Arbeiten mit Oracle-Datentypen verwendet werden können, z. B. <xref:System.Data.OracleClient.OracleNumber> und <xref:System.Data.OracleClient.OracleString>.  
  
 [Oracle-Sequenzen](oracle-sequences.md)  
 Beschreibt die Unterstützung für das Abrufen der servergenerierten Oracle-Sequenz-Schlüsselwerte.  
  
 [Oracle-Datentypzuordnungen](oracle-data-type-mappings.md)  
 Listet Oracle-Datentypen und ihre Zuordnungen zum <xref:System.Data.OracleClient.OracleDataReader> auf.  
  
 [Verteilte Oracle-Transaktionen](oracle-distributed-transactions.md)  
 Beschreibt, wie das <xref:System.Data.OracleClient.OracleConnection>-Objekt automatisch in einer vorhandenen verteilten Transaktion aufgelistet wird, wenn es ermittelt, dass eine Transaktion aktiv ist.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Sichern von ADO.NET-Anwendungen](securing-ado-net-applications.md)  
 Beschreibt sichere Programmiermethoden für ADO.NET.  
  
 ["DataSets", "DataTables" und "DataViews"](./dataset-datatable-dataview/index.md)  
 Beschreibt das Erstellen und Verwenden von `DataSets`, typisierten `DataSets`, `DataTables` und `DataViews`.  
  
 [Abrufen und Ändern von Daten in ADO.NET](retrieving-and-modifying-data.md)  
 Beschreibt das Arbeiten mit Daten in ADO.NET.  
  
 [SQL Server und ADO.NET](./sql/index.md)  
 Beschreibt das Arbeiten mit Funktionen und Funktionalität, die spezifisch für SQL Server sind.  
  
 [DbProviderFactories](dbproviderfactories.md)  
 Beschreibt generische Klassen, mit deren Hilfe in ADO.NET anbieterunabhängiger Code geschrieben werden kann.  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET](index.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
