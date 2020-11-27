---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: e4466df2ce96760db4790b6545484704c22f0842
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254297"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="cdcda-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="cdcda-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>

<span data-ttu-id="cdcda-103">Die angegebene Transaktion für den angegebenen Vorgang wurde aufgrund einer unbehandelten Ausführungsausnahme abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="cdcda-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cdcda-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cdcda-104">Description</span></span>  

 <span data-ttu-id="cdcda-105">Wird nachverfolgt, wenn ein Fehler während eines Versuchs, die aktuelle Transaktion abzuschließen, auftritt.</span><span class="sxs-lookup"><span data-stu-id="cdcda-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="cdcda-106">Dies geschieht, bevor eine Antwort oder ein Fehler an den Aufrufer gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="cdcda-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="cdcda-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="cdcda-107">Troubleshooting</span></span>  

 <span data-ttu-id="cdcda-108">Überprüfen Sie die verfolgte Nachricht auf die Ausnahmenachricht und alle ausführbaren Elemente.</span><span class="sxs-lookup"><span data-stu-id="cdcda-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdcda-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cdcda-109">See also</span></span>

- [<span data-ttu-id="cdcda-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="cdcda-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="cdcda-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="cdcda-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="cdcda-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="cdcda-112">Administration and Diagnostics</span></span>](../index.md)
