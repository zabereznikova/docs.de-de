---
title: Transactions2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79970ad1220e3aab393a18cf52f94487702f37d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="transactions"></a><span data-ttu-id="b8126-102">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="b8126-102">Transactions</span></span>
<span data-ttu-id="b8126-103">Dieser Abschnitt enthält Beispiele, in denen Workflowtransaktionen in [!INCLUDE[wf](../../../../includes/wf-md.md)] veranschaulicht werden.</span><span class="sxs-lookup"><span data-stu-id="b8126-103">This section contains samples that demonstrate workflow transactions in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b8126-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b8126-104">In This Section</span></span>  
 [<span data-ttu-id="b8126-105">Grundlegender TransactionScope</span><span class="sxs-lookup"><span data-stu-id="b8126-105">Basic TransactionScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 <span data-ttu-id="b8126-106">Besteht aus vier Szenarien, die zeigen, wie <xref:System.Activities.Statements.TransactionScope>-Instanzen geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="b8126-106">Consists of four scenarios that show how to nest <xref:System.Activities.Statements.TransactionScope> instances.</span></span>  
  
 [<span data-ttu-id="b8126-107">Verwendung von TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="b8126-107">Use of TransactedReceiveScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 <span data-ttu-id="b8126-108">Veranschaulicht, wie eine Transaktion mit <xref:System.Activities.Statements.TransactionScope> von einem Client auf einen Server übertragen wird, um eine neue Transaktion auf dem Client und ein <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Element zu erstellen, sodass eine Meldung mit einem Transaktionsfluss empfangen und die Lebensdauer der Transaktion auf dem Server mit einem Bereich versehen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b8126-108">Demonstrates how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span>  
  
 [<span data-ttu-id="b8126-109">Schachteln von TransactionScope innerhalb eines Diensts</span><span class="sxs-lookup"><span data-stu-id="b8126-109">Nesting of TransactionScope within a service</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 <span data-ttu-id="b8126-110">Besteht aus zwei Szenarien, die zeigen, wie <xref:System.Activities.Statements.TransactionScope>-Aktivitätsinstanzen innerhalb eines Diensts behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="b8126-110">Consists of two scenarios that show how to handle <xref:System.Activities.Statements.TransactionScope> activity instances within a service.</span></span>
