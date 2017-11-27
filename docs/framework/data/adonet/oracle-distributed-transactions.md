---
title: Verteilte Oracle-Transaktionen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7c48232bb204b71c662a99bf210ad54fc3ee9eb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="7af91-102">Verteilte Oracle-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="7af91-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="7af91-103">Das <xref:System.Data.OracleClient.OracleConnection>-Objekt wird automatisch in einer vorhandenen verteilten Transaktion aufgelistet, wenn es ermittelt, dass eine Transaktion aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="7af91-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="7af91-104">Die automatische Eintragung von Transaktionen wird vorgenommen, wenn die Verbindung aus dem Verbindungspool geöffnet oder abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7af91-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="7af91-105">Die automatische Eintragung kann in vorhandenen Transaktionen deaktiviert werden, indem </span><span class="sxs-lookup"><span data-stu-id="7af91-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```  
Enlist=false  
```  
  
 <span data-ttu-id="7af91-106">als Verbindungszeichenfolgenparameter für die <xref:System.Data.OracleClient.OracleConnection> angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7af91-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7af91-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7af91-107">See Also</span></span>  
 [<span data-ttu-id="7af91-108">Oracle und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7af91-108">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="7af91-109">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="7af91-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
