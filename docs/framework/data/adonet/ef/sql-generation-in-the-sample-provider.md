---
title: SQL-Generierung im Beispielanbieter
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: b2397570bb5f312aa6a3955a76234bde508fcc6a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505500"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="66982-102">SQL-Generierung im Beispielanbieter</span><span class="sxs-lookup"><span data-stu-id="66982-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="66982-103">Die [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) veranschaulicht die neuen Komponenten von ADO.NET-Datenanbietern,, die Unterstützung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66982-103">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="66982-104">Es funktioniert mit einer SQL Server 2005-Datenbank und wird als Wrapper für den System.Data.SqlClient ADO.NET 2.0-Datenanbieter implementiert.</span><span class="sxs-lookup"><span data-stu-id="66982-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="66982-105">Das SQL-Generierungsmodul des Beispielanbieters (das sich abgesehen von der Datei DmlSqlGenerator.cs im Ordner SQL-Generierung befindet) verwendet einen Eingabe-DbQueryCommandTree und erzeugt eine einzelne SQL-SELECT-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="66982-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66982-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="66982-106">In This Section</span></span>  
 <span data-ttu-id="66982-107">Dieser Abschnitt schließt folgende Themen ein:</span><span class="sxs-lookup"><span data-stu-id="66982-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="66982-108">Architektur und Entwurf</span><span class="sxs-lookup"><span data-stu-id="66982-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="66982-109">Exemplarische Vorgehensweise: SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="66982-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="66982-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66982-110">See also</span></span>
- [<span data-ttu-id="66982-111">SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="66982-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
