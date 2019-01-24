---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: e36126dcdfcc87a410d200cdf23aac670dc2b5e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596507"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="4fdb9-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="4fdb9-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="4fdb9-103">Die angegebene Transaktion für den angegebenen Vorgang wurde aufgrund einer unbehandelten Ausführungsausnahme abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4fdb9-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4fdb9-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4fdb9-104">Description</span></span>  
 <span data-ttu-id="4fdb9-105">Wird nachverfolgt, wenn ein Fehler während eines Versuchs, die aktuelle Transaktion abzuschließen, auftritt.</span><span class="sxs-lookup"><span data-stu-id="4fdb9-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="4fdb9-106">Dies geschieht, bevor eine Antwort oder ein Fehler an den Aufrufer gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="4fdb9-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="4fdb9-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="4fdb9-107">Troubleshooting</span></span>  
 <span data-ttu-id="4fdb9-108">Überprüfen Sie die verfolgte Nachricht auf die Ausnahmenachricht und alle ausführbaren Elemente.</span><span class="sxs-lookup"><span data-stu-id="4fdb9-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fdb9-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fdb9-109">See also</span></span>
- [<span data-ttu-id="4fdb9-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4fdb9-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="4fdb9-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="4fdb9-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="4fdb9-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="4fdb9-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
