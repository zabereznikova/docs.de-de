---
title: Oracle und ADO.NET
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 40b81df158dbad0247df76124201decae41e3267
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="ff6b6-102">Oracle und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ff6b6-102">Oracle and ADO.NET</span></span>
> [!NOTE]
>  <span data-ttu-id="ff6b6-103">Die Typen in <xref:System.Data.OracleClient> sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-103">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="ff6b6-104">Die Typen werden in der aktuellen .NET Framework-Version weiterhin unterstützt, die Unterstützung wird jedoch in einer zukünftigen Version eingestellt.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-104">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="ff6b6-105">Microsoft empfiehlt, einen anderen Oracle-Anbieter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-105">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="ff6b6-106">In diesem Abschnitt werden spezifische Funktionen und Verhaltensweisen des [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieters für Oracle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-106">This section describes features and behaviors that are specific to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="ff6b6-107">Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieter für Oracle ermöglicht über die OCI (Oracle Call Interface), die Bestandteil der Oracle Client-Software ist, den Zugriff auf eine Oracle-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="ff6b6-108">Die Funktionalität des Datenanbieters soll eine ähnlich dem Konzept der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für SQL Server, OLE DB und ODBC.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-108">The functionality of the data provider is designed to be similar to that of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="ff6b6-109">Damit der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieter für Oracle in einer Anwendung verwendet werden kann, muss die Anwendung wie folgt auf den <xref:System.Data.OracleClient>-Namespace verweisen:</span><span class="sxs-lookup"><span data-stu-id="ff6b6-109">To use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="ff6b6-110">Außerdem müssen Sie beim Kompilieren des Codes einen Verweis auf die DLL-Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-110">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="ff6b6-111">Wenn Sie z. B. ein C#-Programm kompilieren, muss Ihre Befehlszeile Folgendes beinhalten:</span><span class="sxs-lookup"><span data-stu-id="ff6b6-111">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="ff6b6-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ff6b6-112">In This Section</span></span>  
 [<span data-ttu-id="ff6b6-113">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="ff6b6-113">System Requirements</span></span>](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="ff6b6-114">Benennt die Voraussetzungen, die für die Verwendung des [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieters für Oracle erfüllt sein müssen, und beschreibt eine Reihe von Punkten, die bei dessen Verwendung zu beachten sind.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-114">Describes requirements for using the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="ff6b6-115">Oracle-BFILEs</span><span class="sxs-lookup"><span data-stu-id="ff6b6-115">Oracle BFILEs</span></span>](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 <span data-ttu-id="ff6b6-116">Beschreibt die <xref:System.Data.OracleClient.OracleBFile>-Klasse, die zum Arbeiten mit dem BFILE-Datentyp von Oracle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-116">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="ff6b6-117">Oracle-LOBs</span><span class="sxs-lookup"><span data-stu-id="ff6b6-117">Oracle LOBs</span></span>](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 <span data-ttu-id="ff6b6-118">Beschreibt die <xref:System.Data.OracleClient.OracleLob>-Klasse, die zum Arbeiten mit dem LOB-Datentyp von Oracle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-118">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="ff6b6-119">Oracle-REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="ff6b6-119">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 <span data-ttu-id="ff6b6-120">Beschreibt die Unterstützung für den REF CURSOR-Datentyp von Oracle.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-120">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="ff6b6-121">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="ff6b6-121">OracleTypes</span></span>](../../../../docs/framework/data/adonet/oracletypes.md)  
 <span data-ttu-id="ff6b6-122">Beschreibt Strukturen, die zum Arbeiten mit Oracle-Datentypen verwendet werden können, z. B. <xref:System.Data.OracleClient.OracleNumber> und <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-122">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="ff6b6-123">Oracle-Sequenzen</span><span class="sxs-lookup"><span data-stu-id="ff6b6-123">Oracle Sequences</span></span>](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 <span data-ttu-id="ff6b6-124">Beschreibt die Unterstützung für das Abrufen der servergenerierten Oracle-Sequenz-Schlüsselwerte.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-124">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="ff6b6-125">Oracle-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="ff6b6-125">Oracle Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <span data-ttu-id="ff6b6-126">Listet Oracle-Datentypen und ihre Zuordnungen zum <xref:System.Data.OracleClient.OracleDataReader> auf.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-126">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="ff6b6-127">Verteilte Oracle-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="ff6b6-127">Oracle Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 <span data-ttu-id="ff6b6-128">Beschreibt, wie das <xref:System.Data.OracleClient.OracleConnection>-Objekt automatisch in einer vorhandenen verteilten Transaktion aufgelistet wird, wenn es ermittelt, dass eine Transaktion aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-128">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ff6b6-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ff6b6-129">Related Sections</span></span>  
 [<span data-ttu-id="ff6b6-130">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="ff6b6-130">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 <span data-ttu-id="ff6b6-131">Beschreibt sichere Codierungstechniken bei der Verwendung von [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff6b6-131">Describes secure coding practices when using [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
 [<span data-ttu-id="ff6b6-132">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="ff6b6-132">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="ff6b6-133">Beschreibt das Erstellen und Verwenden von `DataSets`, typisierten `DataSets`, `DataTables` und `DataViews`.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-133">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="ff6b6-134">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ff6b6-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 <span data-ttu-id="ff6b6-135">Beschreibt das Arbeiten mit Daten in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-135">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="ff6b6-136">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ff6b6-136">SQL Server and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/index.md)  
 <span data-ttu-id="ff6b6-137">Beschreibt das Arbeiten mit Funktionen und Funktionalität, die spezifisch für SQL Server sind.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-137">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="ff6b6-138">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="ff6b6-138">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 <span data-ttu-id="ff6b6-139">Beschreibt generische Klassen, mit deren Hilfe in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] anbieterunabhängiger Code geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="ff6b6-139">Describes generic classes that allow you to write provider-independent code in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff6b6-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff6b6-140">See Also</span></span>  
 [<span data-ttu-id="ff6b6-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ff6b6-141">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="ff6b6-142">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="ff6b6-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
