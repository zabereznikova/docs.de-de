---
title: Oracle und ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 012a5b55d052f5f06da5c152da79f4676b2bff4e
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877948"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="2664b-102">Oracle und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2664b-102">Oracle and ADO.NET</span></span>
> [!NOTE]
>  <span data-ttu-id="2664b-103">Die Typen in <xref:System.Data.OracleClient> sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="2664b-103">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="2664b-104">Die Typen werden in der aktuellen .NET Framework-Version weiterhin unterstützt, die Unterstützung wird jedoch in einem zukünftigen Release eingestellt.</span><span class="sxs-lookup"><span data-stu-id="2664b-104">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="2664b-105">Microsoft empfiehlt, einen anderen Oracle-Anbieter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2664b-105">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="2664b-106">Dieser Abschnitt beschreibt die Funktionen und Verhaltensweisen, die spezifisch für die .NET Framework-Datenanbieter für Oracle sind.</span><span class="sxs-lookup"><span data-stu-id="2664b-106">This section describes features and behaviors that are specific to the .NET Framework Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="2664b-107">Die .NET Framework-Datenanbieter für Oracle ermöglicht den Zugriff auf eine Oracle-Datenbank, die mit der Oracle aufrufen-Schnittstelle (OCI) von Oracle-Clientsoftware bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2664b-107">The .NET Framework Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="2664b-108">Die Funktionalität des Datenanbieters soll ähnelt der von der .NET Framework-Datenanbieter für SQL Server, OLE DB und ODBC werden.</span><span class="sxs-lookup"><span data-stu-id="2664b-108">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="2664b-109">Um den .NET Framework-Datenanbieter für Oracle verwenden zu können, muss eine Anwendung verweisen die <xref:System.Data.OracleClient> Namespace wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2664b-109">To use the .NET Framework Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="2664b-110">Außerdem müssen Sie beim Kompilieren des Codes einen Verweis auf die DLL-Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2664b-110">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="2664b-111">Wenn Sie z. B. ein C#-Programm kompilieren, muss Ihre Befehlszeile Folgendes beinhalten:</span><span class="sxs-lookup"><span data-stu-id="2664b-111">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="2664b-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2664b-112">In This Section</span></span>  
 [<span data-ttu-id="2664b-113">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="2664b-113">System Requirements</span></span>](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="2664b-114">Beschreibt die Anforderungen für die Verwendung der .NET Framework-Datenanbieter für Oracle und eine Reihe von Problemen, zu berücksichtigen, dass bei dessen Verwendung beschreibt.</span><span class="sxs-lookup"><span data-stu-id="2664b-114">Describes requirements for using the .NET Framework Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="2664b-115">Oracle-BFILEs</span><span class="sxs-lookup"><span data-stu-id="2664b-115">Oracle BFILEs</span></span>](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 <span data-ttu-id="2664b-116">Beschreibt die <xref:System.Data.OracleClient.OracleBFile>-Klasse, die zum Arbeiten mit dem BFILE-Datentyp von Oracle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2664b-116">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="2664b-117">Oracle-LOBs</span><span class="sxs-lookup"><span data-stu-id="2664b-117">Oracle LOBs</span></span>](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 <span data-ttu-id="2664b-118">Beschreibt die <xref:System.Data.OracleClient.OracleLob>-Klasse, die zum Arbeiten mit dem LOB-Datentyp von Oracle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2664b-118">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="2664b-119">Oracle-REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="2664b-119">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 <span data-ttu-id="2664b-120">Beschreibt die Unterstützung für den REF CURSOR-Datentyp von Oracle.</span><span class="sxs-lookup"><span data-stu-id="2664b-120">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="2664b-121">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="2664b-121">OracleTypes</span></span>](../../../../docs/framework/data/adonet/oracletypes.md)  
 <span data-ttu-id="2664b-122">Beschreibt Strukturen, die zum Arbeiten mit Oracle-Datentypen verwendet werden können, z. B. <xref:System.Data.OracleClient.OracleNumber> und <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="2664b-122">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="2664b-123">Oracle-Sequenzen</span><span class="sxs-lookup"><span data-stu-id="2664b-123">Oracle Sequences</span></span>](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 <span data-ttu-id="2664b-124">Beschreibt die Unterstützung für das Abrufen der servergenerierten Oracle-Sequenz-Schlüsselwerte.</span><span class="sxs-lookup"><span data-stu-id="2664b-124">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="2664b-125">Oracle-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="2664b-125">Oracle Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <span data-ttu-id="2664b-126">Listet Oracle-Datentypen und ihre Zuordnungen zum <xref:System.Data.OracleClient.OracleDataReader> auf.</span><span class="sxs-lookup"><span data-stu-id="2664b-126">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="2664b-127">Verteilte Oracle-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="2664b-127">Oracle Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 <span data-ttu-id="2664b-128">Beschreibt, wie das <xref:System.Data.OracleClient.OracleConnection>-Objekt automatisch in einer vorhandenen verteilten Transaktion aufgelistet wird, wenn es ermittelt, dass eine Transaktion aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="2664b-128">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2664b-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="2664b-129">Related Sections</span></span>  
 [<span data-ttu-id="2664b-130">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="2664b-130">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 <span data-ttu-id="2664b-131">Beschreibt sichere Programmiermethoden für ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="2664b-131">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="2664b-132">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="2664b-132">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="2664b-133">Beschreibt das Erstellen und Verwenden von `DataSets`, typisierten `DataSets`, `DataTables` und `DataViews`.</span><span class="sxs-lookup"><span data-stu-id="2664b-133">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="2664b-134">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2664b-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 <span data-ttu-id="2664b-135">Beschreibt das Arbeiten mit Daten in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="2664b-135">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="2664b-136">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2664b-136">SQL Server and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/index.md)  
 <span data-ttu-id="2664b-137">Beschreibt das Arbeiten mit Funktionen und Funktionalität, die spezifisch für SQL Server sind.</span><span class="sxs-lookup"><span data-stu-id="2664b-137">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="2664b-138">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="2664b-138">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 <span data-ttu-id="2664b-139">Beschreibt generische Klassen, mit deren Hilfe in ADO.NET anbieterunabhängiger Code geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="2664b-139">Describes generic classes that allow you to write provider-independent code in ADO.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2664b-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2664b-140">See also</span></span>

- [<span data-ttu-id="2664b-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2664b-141">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
- [<span data-ttu-id="2664b-142">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="2664b-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
