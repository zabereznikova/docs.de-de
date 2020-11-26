---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: 9ad9dc9fd078f7ad4c0934c8bf9bb73feb935014
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236649"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="12991-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="12991-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>

<span data-ttu-id="12991-103">Der WS-AT-Protokolldienst hat eine Prepared- oder eine Replay-Nachricht von einem nicht erkannten flüchtigen Teilnehmer empfangen.</span><span class="sxs-lookup"><span data-stu-id="12991-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="12991-104">Dem Teilnehmer wurde ein Fehler zurückgegeben, der aussagt, dass das Ergebnis der Transaktion zweifelhaft ist.</span><span class="sxs-lookup"><span data-stu-id="12991-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="12991-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="12991-105">Description</span></span>  

 <span data-ttu-id="12991-106">Verfolgt nach, wann der lokale Transaktions-Manager eine Prepared- oder Replay-Nachricht von einer flüchtigen Eintragung erhält, die er bereits vergessen hat.</span><span class="sxs-lookup"><span data-stu-id="12991-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="12991-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="12991-107">Troubleshooting</span></span>  

 <span data-ttu-id="12991-108">Untersuchen Sie die potenziellen Ursachen von verspätet ankommenden Nachrichten vom flüchtigen Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="12991-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12991-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12991-109">See also</span></span>

- [<span data-ttu-id="12991-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="12991-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="12991-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="12991-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="12991-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="12991-112">Administration and Diagnostics</span></span>](../index.md)
