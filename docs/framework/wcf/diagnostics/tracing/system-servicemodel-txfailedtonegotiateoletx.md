---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 7f376244343a75c16d5d2355642d626f666e42bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33483830"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="f4e62-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="f4e62-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>
<span data-ttu-id="f4e62-103">Die OleTransactions-Protokollverhandlung wurde nicht für den angegebenen Koordinationskontext abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f4e62-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f4e62-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4e62-104">Description</span></span>  
 <span data-ttu-id="f4e62-105">Verfolgt nach, wann eine eingehende Transaktion mit OleTx-Informationen die angehängten OleTx-Informationen nicht verwenden kann und stattdessen wieder zur Nutzung des WS-AT zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="f4e62-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="f4e62-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="f4e62-106">Troubleshooting</span></span>  
 <span data-ttu-id="f4e62-107">Gibt ein potenzielles Problem mit MSDTC RPC-Kommunikation zwischen den Computern an.</span><span class="sxs-lookup"><span data-stu-id="f4e62-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="f4e62-108">Wenn viele dieser Ablaufverfolgungen im Protokoll angezeigt werden, kann sich eine drastische Abnahme der Leistung ergeben.</span><span class="sxs-lookup"><span data-stu-id="f4e62-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="f4e62-109">Wenn OleTx nicht gewünscht wird, legen Sie `OleTxUpgradeEnabled` in der WS-AT-Registrierungskonfiguration auf 0 (null) fest.</span><span class="sxs-lookup"><span data-stu-id="f4e62-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4e62-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4e62-110">See Also</span></span>  
 [<span data-ttu-id="f4e62-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f4e62-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f4e62-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="f4e62-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f4e62-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="f4e62-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
