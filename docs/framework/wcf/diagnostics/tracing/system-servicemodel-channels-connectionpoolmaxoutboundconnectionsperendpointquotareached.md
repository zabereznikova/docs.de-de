---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 4f51777ae690178b83d353f72e63a6f2958b1592
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674582"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="2fec2-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="2fec2-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>
<span data-ttu-id="2fec2-103">Der WS-AT-Protokolldienst konnte sich nicht auf einer Transaktion mit dem bereitgestellten Koordinationskontext eintragen.</span><span class="sxs-lookup"><span data-stu-id="2fec2-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2fec2-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fec2-104">Description</span></span>  
 <span data-ttu-id="2fec2-105">Wird nachverfolgt, wenn MSDTC sich nicht auf einer Transaktion für ein gegebenes 2pc-Protokoll eintragen konnte.</span><span class="sxs-lookup"><span data-stu-id="2fec2-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="2fec2-106">Dies kann geschehen, wenn die Transaktion nicht mehr existiert, die Eintragung nicht mehr erlaubt ist oder zu viele Eintragungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2fec2-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2fec2-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="2fec2-107">Troubleshooting</span></span>  
 <span data-ttu-id="2fec2-108">Überprüfen Sie die Statuszeichenfolge innerhalb der Ablaufverfolgungsnachricht, um zu bestimmen, ob ein ausführbares Element vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2fec2-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fec2-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fec2-109">See also</span></span>
- [<span data-ttu-id="2fec2-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="2fec2-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="2fec2-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="2fec2-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2fec2-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="2fec2-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
