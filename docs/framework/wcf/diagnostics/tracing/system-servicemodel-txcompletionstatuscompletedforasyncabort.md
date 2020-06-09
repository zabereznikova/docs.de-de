---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: 8371dba79573f480b264ed6185b8cf0098e3cb2a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576576"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="cd992-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="cd992-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="cd992-103">Die angegebene Transaktion für den angegebenen Vorgang wurde aufgrund eines asynchronen Abbruchs abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="cd992-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cd992-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cd992-104">Description</span></span>  
 <span data-ttu-id="cd992-105">Die aktuelle Transaktion wurde abgebrochen, weil ein anderer Teilnehmer für den Abbruch votiert hat, weil Zeitüberschreitungen aufgetreten sind oder weil ein anderer Fehler bei einem Teilnehmer einer Transaktion aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="cd992-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="cd992-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="cd992-106">Troubleshooting</span></span>  
 <span data-ttu-id="cd992-107">Wenn dieser Abbruch unerwartet erfolgt, überprüfen Sie alle Systemprotokolle, um den wirklichen Grund für den Abbruch zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="cd992-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd992-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd992-108">See also</span></span>

- [<span data-ttu-id="cd992-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="cd992-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="cd992-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="cd992-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="cd992-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="cd992-111">Administration and Diagnostics</span></span>](../index.md)
