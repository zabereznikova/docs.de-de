---
title: Binäre Daten und Daten mit umfangreichen Werten in SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 9ebbe23dfbcac7825ce449dd40f62b921d13ab4a
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46507938"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="f354b-102">Binäre Daten und Daten mit umfangreichen Werten in SQL Server</span><span class="sxs-lookup"><span data-stu-id="f354b-102">SQL Server Binary and Large-Value Data</span></span>
<span data-ttu-id="f354b-103">SQL Server umfasst den `max`-Bezeichner, der die Speicherkapazität für die Datentypen `varchar`, `nvarchar` und `varbinary` erhöht.</span><span class="sxs-lookup"><span data-stu-id="f354b-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="f354b-104">`varchar(max)`, `nvarchar(max)`, und `varbinary(max)` werden zusammenfassend als bezeichnet *Datentypen mit umfangreichen Werten*.</span><span class="sxs-lookup"><span data-stu-id="f354b-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="f354b-105">Sie können die Datentypen mit umfangreichen Werten zum Speichern von bis zu 2^31-1 Bytes an Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="f354b-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="f354b-106">In SQL Server 2008 wird das FILESTREAM-Attribut eingeführt. Es ist kein Datentyp, sondern eher ein Attribut, das für eine Spalte definiert werden kann, damit Daten mit umfangreichen Werten im Dateisystem statt in der Datenbank gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="f354b-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f354b-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f354b-107">In This Section</span></span>  
 [<span data-ttu-id="f354b-108">Ändern von Daten mit umfangreichen Werten (max) in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f354b-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 <span data-ttu-id="f354b-109">Beschreibt das Arbeiten mit Datentypen für hohe Werte.</span><span class="sxs-lookup"><span data-stu-id="f354b-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="f354b-110">FILESTREAM-Daten</span><span class="sxs-lookup"><span data-stu-id="f354b-110">FILESTREAM Data</span></span>](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 <span data-ttu-id="f354b-111">Beschreibt die Verwendung von Datentypen für große Werte, die mit dem FILESTREAM-Attribut in SQL Server 2008 gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="f354b-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f354b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f354b-112">See Also</span></span>  
 [<span data-ttu-id="f354b-113">SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="f354b-113">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="f354b-114">SQL Server Data Operations in ADO.NET (SQL Server-Datenvorgänge in ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="f354b-114">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [<span data-ttu-id="f354b-115">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f354b-115">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="f354b-116">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="f354b-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
