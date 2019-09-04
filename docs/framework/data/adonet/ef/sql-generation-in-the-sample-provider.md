---
title: SQL-Generierung im Beispielanbieter
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: d0e058cdc4dd3f7a1a04ab6eea5acf4d3deabb89
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248512"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="3c517-102">SQL-Generierung im Beispielanbieter</span><span class="sxs-lookup"><span data-stu-id="3c517-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="3c517-103">Der [Entity Framework Beispiel Anbieter](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) veranschaulicht die neuen Komponenten von ADO.NET-Datenanbietern, die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3c517-103">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="3c517-104">Es funktioniert mit einer SQL Server 2005-Datenbank und wird als Wrapper für den System.Data.SqlClient ADO.NET 2.0-Datenanbieter implementiert.</span><span class="sxs-lookup"><span data-stu-id="3c517-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="3c517-105">Das SQL-Generierungsmodul des Beispielanbieters (das sich abgesehen von der Datei DmlSqlGenerator.cs im Ordner SQL-Generierung befindet) verwendet einen Eingabe-DbQueryCommandTree und erzeugt eine einzelne SQL-SELECT-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="3c517-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c517-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3c517-106">In This Section</span></span>  
 <span data-ttu-id="3c517-107">Dieser Abschnitt schließt folgende Themen ein:</span><span class="sxs-lookup"><span data-stu-id="3c517-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="3c517-108">Architektur und Entwurf</span><span class="sxs-lookup"><span data-stu-id="3c517-108">Architecture and Design</span></span>](architecture-and-design.md)  
  
 [<span data-ttu-id="3c517-109">Exemplarische Vorgehensweise: SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="3c517-109">Walkthrough: SQL Generation</span></span>](walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="3c517-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c517-110">See also</span></span>

- [<span data-ttu-id="3c517-111">SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="3c517-111">SQL Generation</span></span>](sql-generation.md)
