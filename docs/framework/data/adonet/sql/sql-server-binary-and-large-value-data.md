---
title: "Binäre Daten und Daten mit umfangreichen Werten in SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5ce85e61ac001ec07c14cebbc8d07e6c031498fc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="31907-102">Binäre Daten und Daten mit umfangreichen Werten in SQL Server</span><span class="sxs-lookup"><span data-stu-id="31907-102">SQL Server Binary and Large-Value Data</span></span>
<span data-ttu-id="31907-103">SQL Server umfasst den `max`-Bezeichner, der die Speicherkapazität für die Datentypen `varchar`, `nvarchar` und `varbinary` erhöht.</span><span class="sxs-lookup"><span data-stu-id="31907-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="31907-104">`varchar(max)`, `nvarchar(max)`, und `varbinary(max)` werden insgesamt als *Datentypen mit umfangreichen Werten*.</span><span class="sxs-lookup"><span data-stu-id="31907-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="31907-105">Sie können die Datentypen mit umfangreichen Werten zum Speichern von bis zu 2^31-1 Bytes an Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="31907-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="31907-106">In SQL Server 2008 wird das FILESTREAM-Attribut eingeführt. Es ist kein Datentyp, sondern eher ein Attribut, das für eine Spalte definiert werden kann, damit Daten mit umfangreichen Werten im Dateisystem statt in der Datenbank gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="31907-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31907-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="31907-107">In This Section</span></span>  
 [<span data-ttu-id="31907-108">Ändern von Daten mit umfangreichen Werten (max) in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="31907-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 <span data-ttu-id="31907-109">Beschreibt das Arbeiten mit Datentypen für hohe Werte.</span><span class="sxs-lookup"><span data-stu-id="31907-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="31907-110">FILESTREAM-Daten</span><span class="sxs-lookup"><span data-stu-id="31907-110">FILESTREAM Data</span></span>](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 <span data-ttu-id="31907-111">Beschreibt die Verwendung von Datentypen für große Werte, die mit dem FILESTREAM-Attribut in SQL Server 2008 gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="31907-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31907-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31907-112">See Also</span></span>  
 [<span data-ttu-id="31907-113">SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="31907-113">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="31907-114">SQL Server Data Operations in ADO.NET (SQL Server-Datenvorgänge in ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="31907-114">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [<span data-ttu-id="31907-115">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="31907-115">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="31907-116">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="31907-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
