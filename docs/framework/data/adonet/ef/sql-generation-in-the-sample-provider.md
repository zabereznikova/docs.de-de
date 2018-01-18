---
title: SQL-Generierung im Beispielanbieter
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 7a7f95f7432fdac00a34e7d878ef979656a7af4e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="592cd-102">SQL-Generierung im Beispielanbieter</span><span class="sxs-lookup"><span data-stu-id="592cd-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="592cd-103">Die [Entity Framework-Beispielanbieter](http://go.microsoft.com/fwlink/?LinkId=180616) veranschaulicht die neuen Komponenten von ADO.NET-Datenanbietern,, die Unterstützung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="592cd-103">The [Entity Framework Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="592cd-104">Es funktioniert mit einer SQL Server 2005-Datenbank und wird als Wrapper für den System.Data.SqlClient ADO.NET 2.0-Datenanbieter implementiert.</span><span class="sxs-lookup"><span data-stu-id="592cd-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="592cd-105">Das SQL-Generierungsmodul des Beispielanbieters (das sich abgesehen von der Datei DmlSqlGenerator.cs im Ordner SQL-Generierung befindet) verwendet einen Eingabe-DbQueryCommandTree und erzeugt eine einzelne SQL-SELECT-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="592cd-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="592cd-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="592cd-106">In This Section</span></span>  
 <span data-ttu-id="592cd-107">Dieser Abschnitt schließt folgende Themen ein:</span><span class="sxs-lookup"><span data-stu-id="592cd-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="592cd-108">Architektur und Entwurf</span><span class="sxs-lookup"><span data-stu-id="592cd-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="592cd-109">Exemplarische Vorgehensweise: SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="592cd-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="592cd-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="592cd-110">See Also</span></span>  
 [<span data-ttu-id="592cd-111">SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="592cd-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
