---
title: SQL-Generierung im Beispielanbieter
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: 7275a67927d7692dc943e2555d65d1f7d6e4ba5a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762152"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="42d46-102">SQL-Generierung im Beispielanbieter</span><span class="sxs-lookup"><span data-stu-id="42d46-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="42d46-103">Die [Entity Framework-Beispielanbieter](http://go.microsoft.com/fwlink/?LinkId=180616) veranschaulicht die neuen Komponenten von ADO.NET-Datenanbietern,, die Unterstützung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42d46-103">The [Entity Framework Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="42d46-104">Es funktioniert mit einer SQL Server 2005-Datenbank und wird als Wrapper für den System.Data.SqlClient ADO.NET 2.0-Datenanbieter implementiert.</span><span class="sxs-lookup"><span data-stu-id="42d46-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="42d46-105">Das SQL-Generierungsmodul des Beispielanbieters (das sich abgesehen von der Datei DmlSqlGenerator.cs im Ordner SQL-Generierung befindet) verwendet einen Eingabe-DbQueryCommandTree und erzeugt eine einzelne SQL-SELECT-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="42d46-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="42d46-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="42d46-106">In This Section</span></span>  
 <span data-ttu-id="42d46-107">Dieser Abschnitt schließt folgende Themen ein:</span><span class="sxs-lookup"><span data-stu-id="42d46-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="42d46-108">Architektur und Entwurf</span><span class="sxs-lookup"><span data-stu-id="42d46-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="42d46-109">Exemplarische Vorgehensweise: SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="42d46-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="42d46-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42d46-110">See Also</span></span>  
 [<span data-ttu-id="42d46-111">SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="42d46-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
