---
title: Verteilte Oracle-Transaktionen
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: edd06b94ce4157e90d334ee7feac2a449f7ee74b
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040477"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="4e2e6-102">Verteilte Oracle-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="4e2e6-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="4e2e6-103">Das <xref:System.Data.OracleClient.OracleConnection>-Objekt wird automatisch in einer vorhandenen verteilten Transaktion aufgelistet, wenn es ermittelt, dass eine Transaktion aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="4e2e6-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="4e2e6-104">Die automatische Eintragung von Transaktionen wird vorgenommen, wenn die Verbindung aus dem Verbindungspool geöffnet oder abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4e2e6-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="4e2e6-105">Die automatische Eintragung kann in vorhandenen Transaktionen deaktiviert werden, indem</span><span class="sxs-lookup"><span data-stu-id="4e2e6-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```csharp  
Enlist=false  
```  
  
 <span data-ttu-id="4e2e6-106">als Verbindungszeichenfolgenparameter für die <xref:System.Data.OracleClient.OracleConnection> angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4e2e6-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e2e6-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e2e6-107">See also</span></span>

- [<span data-ttu-id="4e2e6-108">Oracle und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4e2e6-108">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="4e2e6-109">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4e2e6-109">ADO.NET Overview</span></span>](ado-net-overview.md)
