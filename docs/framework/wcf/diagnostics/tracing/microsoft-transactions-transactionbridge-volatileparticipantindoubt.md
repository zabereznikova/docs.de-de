---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: ab1c2c8afe3a66536810a614cc6deac12519cb9b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599632"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="2da04-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="2da04-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="2da04-103">Der WS-AT-Protokolldienst hat eine Prepared- oder eine Replay-Nachricht von einem nicht erkannten flüchtigen Teilnehmer empfangen.</span><span class="sxs-lookup"><span data-stu-id="2da04-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="2da04-104">Dem Teilnehmer wurde ein Fehler zurückgegeben, der aussagt, dass das Ergebnis der Transaktion zweifelhaft ist.</span><span class="sxs-lookup"><span data-stu-id="2da04-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2da04-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2da04-105">Description</span></span>  
 <span data-ttu-id="2da04-106">Verfolgt nach, wann der lokale Transaktions-Manager eine Prepared- oder Replay-Nachricht von einer flüchtigen Eintragung erhält, die er bereits vergessen hat.</span><span class="sxs-lookup"><span data-stu-id="2da04-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2da04-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="2da04-107">Troubleshooting</span></span>  
 <span data-ttu-id="2da04-108">Untersuchen Sie die potenziellen Ursachen von verspätet ankommenden Nachrichten vom flüchtigen Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="2da04-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da04-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2da04-109">See also</span></span>

- [<span data-ttu-id="2da04-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="2da04-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="2da04-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="2da04-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2da04-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="2da04-112">Administration and Diagnostics</span></span>](../index.md)
