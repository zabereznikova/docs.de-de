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
# <a name="oracle-and-adonet"></a><span data-ttu-id="2562d-103">Oracle und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2562d-103">Oracle and ADO.NET</span></span>
> [!NOTE]
> <span data-ttu-id="2562d-104">Die Typen in <xref:System.Data.OracleClient> sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="2562d-104">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="2562d-105">Die Typen werden in der aktuellen .NET Framework-Version weiterhin unterstützt, die Unterstützung wird jedoch in einem zukünftigen Release eingestellt.</span><span class="sxs-lookup"><span data-stu-id="2562d-105">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="2562d-106">Microsoft empfiehlt, einen anderen Oracle-Anbieter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2562d-106">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="2562d-107">In diesem Abschnitt werden Funktionen und Verhaltensweisen beschrieben, die für die .NET Framework Datenanbieter für Oracle spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="2562d-107">This section describes features and behaviors that are specific to the .NET Framework Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="2562d-108">Der .NET Framework Datenanbieter für Oracle ermöglicht den Zugriff auf eine Oracle-Datenbank mithilfe von OCI (Oracle callinterface), wie von der Oracle-Client Software bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2562d-108">The .NET Framework Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="2562d-109">Die Funktionalität des Datenanbieters ist so konzipiert, dass Sie mit der .NET Framework Datenanbieter für SQL Server, OLE DB und ODBC vergleichbar ist.</span><span class="sxs-lookup"><span data-stu-id="2562d-109">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="2562d-110">Um die .NET Framework Datenanbieter für Oracle zu verwenden, muss eine Anwendung wie folgt auf den- <xref:System.Data.OracleClient> Namespace verweisen:</span><span class="sxs-lookup"><span data-stu-id="2562d-110">To use the .NET Framework Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="2562d-111">Außerdem müssen Sie beim Kompilieren des Codes einen Verweis auf die DLL-Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2562d-111">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="2562d-112">Wenn Sie z. B. ein C#-Programm kompilieren, muss Ihre Befehlszeile Folgendes beinhalten:</span><span class="sxs-lookup"><span data-stu-id="2562d-112">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```console
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="2562d-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2562d-113">In This Section</span></span>  
 [<span data-ttu-id="2562d-114">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="2562d-114">System Requirements</span></span>](system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="2562d-115">Beschreibt die Anforderungen für die Verwendung der .NET Framework Datenanbieter für Oracle und beschreibt eine Reihe von Problemen, die bei der Verwendung von zu beachten sind.</span><span class="sxs-lookup"><span data-stu-id="2562d-115">Describes requirements for using the .NET Framework Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="2562d-116">Oracle-BFILEs</span><span class="sxs-lookup"><span data-stu-id="2562d-116">Oracle BFILEs</span></span>](oracle-bfiles.md)  
 <span data-ttu-id="2562d-117">Beschreibt die <xref:System.Data.OracleClient.OracleBFile>-Klasse, die zum Arbeiten mit dem BFILE-Datentyp von Oracle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2562d-117">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="2562d-118">Oracle-LOBs</span><span class="sxs-lookup"><span data-stu-id="2562d-118">Oracle LOBs</span></span>](oracle-lobs.md)  
 <span data-ttu-id="2562d-119">Beschreibt die <xref:System.Data.OracleClient.OracleLob>-Klasse, die zum Arbeiten mit dem LOB-Datentyp von Oracle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2562d-119">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="2562d-120">Oracle-REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="2562d-120">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)  
 <span data-ttu-id="2562d-121">Beschreibt die Unterstützung für den REF CURSOR-Datentyp von Oracle.</span><span class="sxs-lookup"><span data-stu-id="2562d-121">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="2562d-122">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="2562d-122">OracleTypes</span></span>](oracletypes.md)  
 <span data-ttu-id="2562d-123">Beschreibt Strukturen, die zum Arbeiten mit Oracle-Datentypen verwendet werden können, z. B. <xref:System.Data.OracleClient.OracleNumber> und <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="2562d-123">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="2562d-124">Oracle-Sequenzen</span><span class="sxs-lookup"><span data-stu-id="2562d-124">Oracle Sequences</span></span>](oracle-sequences.md)  
 <span data-ttu-id="2562d-125">Beschreibt die Unterstützung für das Abrufen der servergenerierten Oracle-Sequenz-Schlüsselwerte.</span><span class="sxs-lookup"><span data-stu-id="2562d-125">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="2562d-126">Oracle-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="2562d-126">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="2562d-127">Listet Oracle-Datentypen und ihre Zuordnungen zum <xref:System.Data.OracleClient.OracleDataReader> auf.</span><span class="sxs-lookup"><span data-stu-id="2562d-127">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="2562d-128">Verteilte Oracle-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="2562d-128">Oracle Distributed Transactions</span></span>](oracle-distributed-transactions.md)  
 <span data-ttu-id="2562d-129">Beschreibt, wie das <xref:System.Data.OracleClient.OracleConnection>-Objekt automatisch in einer vorhandenen verteilten Transaktion aufgelistet wird, wenn es ermittelt, dass eine Transaktion aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="2562d-129">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2562d-130">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="2562d-130">Related Sections</span></span>  
 [<span data-ttu-id="2562d-131">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="2562d-131">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)  
 <span data-ttu-id="2562d-132">Beschreibt sichere Programmiermethoden für ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="2562d-132">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="2562d-133">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="2562d-133">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)  
 <span data-ttu-id="2562d-134">Beschreibt das Erstellen und Verwenden von `DataSets`, typisierten `DataSets`, `DataTables` und `DataViews`.</span><span class="sxs-lookup"><span data-stu-id="2562d-134">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="2562d-135">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2562d-135">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)  
 <span data-ttu-id="2562d-136">Beschreibt das Arbeiten mit Daten in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="2562d-136">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="2562d-137">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2562d-137">SQL Server and ADO.NET</span></span>](./sql/index.md)  
 <span data-ttu-id="2562d-138">Beschreibt das Arbeiten mit Funktionen und Funktionalität, die spezifisch für SQL Server sind.</span><span class="sxs-lookup"><span data-stu-id="2562d-138">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="2562d-139">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="2562d-139">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="2562d-140">Beschreibt generische Klassen, mit deren Hilfe in ADO.NET anbieterunabhängiger Code geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="2562d-140">Describes generic classes that allow you to write provider-independent code in ADO.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2562d-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2562d-141">See also</span></span>

- [<span data-ttu-id="2562d-142">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2562d-142">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="2562d-143">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2562d-143">ADO.NET Overview</span></span>](ado-net-overview.md)
