---
title: Verteilte Oracle-Transaktionen
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 8e7530621254881402570b59b47a22052b40f2b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713242"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="04b28-102">Verteilte Oracle-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="04b28-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="04b28-103">Das <xref:System.Data.OracleClient.OracleConnection>-Objekt wird automatisch in einer vorhandenen verteilten Transaktion aufgelistet, wenn es ermittelt, dass eine Transaktion aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="04b28-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="04b28-104">Die automatische Eintragung von Transaktionen wird vorgenommen, wenn die Verbindung aus dem Verbindungspool geöffnet oder abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="04b28-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="04b28-105">Die automatische Eintragung kann in vorhandenen Transaktionen deaktiviert werden, indem </span><span class="sxs-lookup"><span data-stu-id="04b28-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```  
Enlist=false  
```  
  
 <span data-ttu-id="04b28-106">als Verbindungszeichenfolgenparameter für die <xref:System.Data.OracleClient.OracleConnection> angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="04b28-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04b28-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04b28-107">See also</span></span>
- [<span data-ttu-id="04b28-108">Oracle und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="04b28-108">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [<span data-ttu-id="04b28-109">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="04b28-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
