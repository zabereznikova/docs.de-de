---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6c0e688e1f24171494b4adaae964ac1fc2be2309
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="f0a67-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="f0a67-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>
<span data-ttu-id="f0a67-103">Die OleTransactions-Protokollverhandlung wurde nicht für den angegebenen Koordinationskontext abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f0a67-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f0a67-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0a67-104">Description</span></span>  
 <span data-ttu-id="f0a67-105">Verfolgt nach, wann eine eingehende Transaktion mit OleTx-Informationen die angehängten OleTx-Informationen nicht verwenden kann und stattdessen wieder zur Nutzung des WS-AT zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="f0a67-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="f0a67-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="f0a67-106">Troubleshooting</span></span>  
 <span data-ttu-id="f0a67-107">Gibt ein potenzielles Problem mit MSDTC RPC-Kommunikation zwischen den Computern an.</span><span class="sxs-lookup"><span data-stu-id="f0a67-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="f0a67-108">Wenn viele dieser Ablaufverfolgungen im Protokoll angezeigt werden, kann sich eine drastische Abnahme der Leistung ergeben.</span><span class="sxs-lookup"><span data-stu-id="f0a67-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="f0a67-109">Wenn OleTx nicht gewünscht wird, legen Sie `OleTxUpgradeEnabled` in der WS-AT-Registrierungskonfiguration auf 0 (null) fest.</span><span class="sxs-lookup"><span data-stu-id="f0a67-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a67-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0a67-110">See Also</span></span>  
 [<span data-ttu-id="f0a67-111">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f0a67-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f0a67-112">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="f0a67-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f0a67-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="f0a67-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
