---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5fa64c87bc4cd0c8dc677d8b4c59de45e31d3270
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="478f3-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="478f3-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>
<span data-ttu-id="478f3-103">Der WS-AT-Protokolldienst konnte sich nicht auf einer Transaktion mit dem bereitgestellten Koordinationskontext eintragen.</span><span class="sxs-lookup"><span data-stu-id="478f3-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="478f3-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="478f3-104">Description</span></span>  
 <span data-ttu-id="478f3-105">Wird nachverfolgt, wenn MSDTC sich nicht auf einer Transaktion für ein gegebenes 2pc-Protokoll eintragen konnte.</span><span class="sxs-lookup"><span data-stu-id="478f3-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="478f3-106">Dies kann geschehen, wenn die Transaktion nicht mehr existiert, die Eintragung nicht mehr erlaubt ist oder zu viele Eintragungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="478f3-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="478f3-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="478f3-107">Troubleshooting</span></span>  
 <span data-ttu-id="478f3-108">Überprüfen Sie die Statuszeichenfolge innerhalb der Ablaufverfolgungsnachricht, um zu bestimmen, ob ein ausführbares Element vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="478f3-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="478f3-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="478f3-109">See Also</span></span>  
 [<span data-ttu-id="478f3-110">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="478f3-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="478f3-111">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="478f3-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="478f3-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="478f3-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
