---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 742e80a3115e8f8caa728e0d8c460ee8b964ddc9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84588716"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="26daf-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="26daf-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>
<span data-ttu-id="26daf-103">Der WS-AT-Protokolldienst konnte sich nicht auf einer Transaktion mit dem bereitgestellten Koordinationskontext eintragen.</span><span class="sxs-lookup"><span data-stu-id="26daf-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="26daf-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="26daf-104">Description</span></span>  
 <span data-ttu-id="26daf-105">Wird nachverfolgt, wenn MSDTC sich nicht auf einer Transaktion für ein gegebenes 2pc-Protokoll eintragen konnte.</span><span class="sxs-lookup"><span data-stu-id="26daf-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="26daf-106">Dies kann geschehen, wenn die Transaktion nicht mehr existiert, die Eintragung nicht mehr erlaubt ist oder zu viele Eintragungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="26daf-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="26daf-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="26daf-107">Troubleshooting</span></span>  
 <span data-ttu-id="26daf-108">Überprüfen Sie die Statuszeichenfolge innerhalb der Ablaufverfolgungsnachricht, um zu bestimmen, ob ein ausführbares Element vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="26daf-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26daf-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26daf-109">See also</span></span>

- [<span data-ttu-id="26daf-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="26daf-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="26daf-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="26daf-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="26daf-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="26daf-112">Administration and Diagnostics</span></span>](../index.md)
