---
title: SQL-Generierung im Beispielanbieter
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: a59f1fecf85d63208c3388204c962b5838902ba7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854315"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="e6b7d-102">SQL-Generierung im Beispielanbieter</span><span class="sxs-lookup"><span data-stu-id="e6b7d-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="e6b7d-103">Der [Entity Framework Beispiel Anbieter](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) veranschaulicht die neuen Komponenten von ADO.NET-Datenanbietern, die die Entity Framework unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-103">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the new components of ADO.NET Data Providers that support the Entity Framework.</span></span>  <span data-ttu-id="e6b7d-104">Es funktioniert mit einer SQL Server 2005-Datenbank und wird als Wrapper für den System.Data.SqlClient ADO.NET 2.0-Datenanbieter implementiert.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="e6b7d-105">Das SQL-Generierungsmodul des Beispielanbieters (das sich abgesehen von der Datei DmlSqlGenerator.cs im Ordner SQL-Generierung befindet) verwendet einen Eingabe-DbQueryCommandTree und erzeugt eine einzelne SQL-SELECT-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e6b7d-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e6b7d-106">In This Section</span></span>  
 <span data-ttu-id="e6b7d-107">Dieser Abschnitt schließt folgende Themen ein:</span><span class="sxs-lookup"><span data-stu-id="e6b7d-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="e6b7d-108">Architektur und Entwurf</span><span class="sxs-lookup"><span data-stu-id="e6b7d-108">Architecture and Design</span></span>](architecture-and-design.md)  
  
 [<span data-ttu-id="e6b7d-109">Exemplarische Vorgehensweise: SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="e6b7d-109">Walkthrough: SQL Generation</span></span>](walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="e6b7d-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6b7d-110">See also</span></span>

- [<span data-ttu-id="e6b7d-111">SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="e6b7d-111">SQL Generation</span></span>](sql-generation.md)
