---
title: Oracle und ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: ccfe40f218e3f09de53d6cb596a31b2520d9ff9b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783473"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="e4133-102">Oracle und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e4133-102">Oracle and ADO.NET</span></span>
> [!NOTE]
> <span data-ttu-id="e4133-103">Die Typen in <xref:System.Data.OracleClient> sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="e4133-103">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="e4133-104">Die Typen werden in der aktuellen .NET Framework-Version weiterhin unterstützt, die Unterstützung wird jedoch in einem zukünftigen Release eingestellt.</span><span class="sxs-lookup"><span data-stu-id="e4133-104">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="e4133-105">Microsoft empfiehlt, einen anderen Oracle-Anbieter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4133-105">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="e4133-106">In diesem Abschnitt werden Funktionen und Verhaltensweisen beschrieben, die für die .NET Framework Datenanbieter für Oracle spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="e4133-106">This section describes features and behaviors that are specific to the .NET Framework Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="e4133-107">Der .NET Framework Datenanbieter für Oracle ermöglicht den Zugriff auf eine Oracle-Datenbank mithilfe von OCI (Oracle callinterface), wie von der Oracle-Client Software bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e4133-107">The .NET Framework Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="e4133-108">Die Funktionalität des Datenanbieters ist so konzipiert, dass Sie mit der .NET Framework Datenanbieter für SQL Server, OLE DB und ODBC vergleichbar ist.</span><span class="sxs-lookup"><span data-stu-id="e4133-108">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="e4133-109">Um die .NET Framework Datenanbieter für Oracle zu verwenden, muss eine Anwendung wie <xref:System.Data.OracleClient> folgt auf den-Namespace verweisen:</span><span class="sxs-lookup"><span data-stu-id="e4133-109">To use the .NET Framework Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="e4133-110">Außerdem müssen Sie beim Kompilieren des Codes einen Verweis auf die DLL-Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e4133-110">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="e4133-111">Wenn Sie z. B. ein C#-Programm kompilieren, muss Ihre Befehlszeile Folgendes beinhalten:</span><span class="sxs-lookup"><span data-stu-id="e4133-111">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="e4133-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e4133-112">In This Section</span></span>  
 [<span data-ttu-id="e4133-113">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="e4133-113">System Requirements</span></span>](system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="e4133-114">Beschreibt die Anforderungen für die Verwendung der .NET Framework Datenanbieter für Oracle und beschreibt eine Reihe von Problemen, die bei der Verwendung von zu beachten sind.</span><span class="sxs-lookup"><span data-stu-id="e4133-114">Describes requirements for using the .NET Framework Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="e4133-115">Oracle-BFILEs</span><span class="sxs-lookup"><span data-stu-id="e4133-115">Oracle BFILEs</span></span>](oracle-bfiles.md)  
 <span data-ttu-id="e4133-116">Beschreibt die <xref:System.Data.OracleClient.OracleBFile>-Klasse, die zum Arbeiten mit dem BFILE-Datentyp von Oracle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e4133-116">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="e4133-117">Oracle-LOBs</span><span class="sxs-lookup"><span data-stu-id="e4133-117">Oracle LOBs</span></span>](oracle-lobs.md)  
 <span data-ttu-id="e4133-118">Beschreibt die <xref:System.Data.OracleClient.OracleLob>-Klasse, die zum Arbeiten mit dem LOB-Datentyp von Oracle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e4133-118">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="e4133-119">Oracle-REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="e4133-119">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)  
 <span data-ttu-id="e4133-120">Beschreibt die Unterstützung für den REF CURSOR-Datentyp von Oracle.</span><span class="sxs-lookup"><span data-stu-id="e4133-120">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="e4133-121">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="e4133-121">OracleTypes</span></span>](oracletypes.md)  
 <span data-ttu-id="e4133-122">Beschreibt Strukturen, die zum Arbeiten mit Oracle-Datentypen verwendet werden können, z. B. <xref:System.Data.OracleClient.OracleNumber> und <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="e4133-122">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="e4133-123">Oracle-Sequenzen</span><span class="sxs-lookup"><span data-stu-id="e4133-123">Oracle Sequences</span></span>](oracle-sequences.md)  
 <span data-ttu-id="e4133-124">Beschreibt die Unterstützung für das Abrufen der servergenerierten Oracle-Sequenz-Schlüsselwerte.</span><span class="sxs-lookup"><span data-stu-id="e4133-124">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="e4133-125">Oracle-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="e4133-125">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="e4133-126">Listet Oracle-Datentypen und ihre Zuordnungen zum <xref:System.Data.OracleClient.OracleDataReader> auf.</span><span class="sxs-lookup"><span data-stu-id="e4133-126">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="e4133-127">Verteilte Oracle-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="e4133-127">Oracle Distributed Transactions</span></span>](oracle-distributed-transactions.md)  
 <span data-ttu-id="e4133-128">Beschreibt, wie das <xref:System.Data.OracleClient.OracleConnection>-Objekt automatisch in einer vorhandenen verteilten Transaktion aufgelistet wird, wenn es ermittelt, dass eine Transaktion aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="e4133-128">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e4133-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e4133-129">Related Sections</span></span>  
 [<span data-ttu-id="e4133-130">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="e4133-130">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)  
 <span data-ttu-id="e4133-131">Beschreibt sichere Programmiermethoden für ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e4133-131">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="e4133-132">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="e4133-132">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)  
 <span data-ttu-id="e4133-133">Beschreibt das Erstellen und Verwenden von `DataSets`, typisierten `DataSets`, `DataTables` und `DataViews`.</span><span class="sxs-lookup"><span data-stu-id="e4133-133">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="e4133-134">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e4133-134">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)  
 <span data-ttu-id="e4133-135">Beschreibt das Arbeiten mit Daten in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e4133-135">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="e4133-136">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e4133-136">SQL Server and ADO.NET</span></span>](./sql/index.md)  
 <span data-ttu-id="e4133-137">Beschreibt das Arbeiten mit Funktionen und Funktionalität, die spezifisch für SQL Server sind.</span><span class="sxs-lookup"><span data-stu-id="e4133-137">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="e4133-138">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="e4133-138">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="e4133-139">Beschreibt generische Klassen, mit deren Hilfe in ADO.NET anbieterunabhängiger Code geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4133-139">Describes generic classes that allow you to write provider-independent code in ADO.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4133-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4133-140">See also</span></span>

- [<span data-ttu-id="e4133-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e4133-141">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="e4133-142">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e4133-142">ADO.NET Overview</span></span>](ado-net-overview.md)
