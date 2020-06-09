---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 2c9ea77cdd76d4593c2ee5b09a4b917677b8925f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601412"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="2d7cf-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="2d7cf-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>
<span data-ttu-id="2d7cf-103">Die OleTransactions-Protokollverhandlung wurde nicht für den angegebenen Koordinationskontext abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2d7cf-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2d7cf-104">Description</span></span>  
 <span data-ttu-id="2d7cf-105">Verfolgt nach, wann eine eingehende Transaktion mit OleTx-Informationen die angehängten OleTx-Informationen nicht verwenden kann und stattdessen wieder zur Nutzung des WS-AT zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2d7cf-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="2d7cf-106">Troubleshooting</span></span>  
 <span data-ttu-id="2d7cf-107">Gibt ein potenzielles Problem mit MSDTC RPC-Kommunikation zwischen den Computern an.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="2d7cf-108">Wenn viele dieser Ablaufverfolgungen im Protokoll angezeigt werden, kann sich eine drastische Abnahme der Leistung ergeben.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="2d7cf-109">Wenn OleTx nicht gewünscht wird, legen Sie `OleTxUpgradeEnabled` in der WS-AT-Registrierungskonfiguration auf 0 (null) fest.</span><span class="sxs-lookup"><span data-stu-id="2d7cf-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d7cf-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d7cf-110">See also</span></span>

- [<span data-ttu-id="2d7cf-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="2d7cf-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="2d7cf-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="2d7cf-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2d7cf-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="2d7cf-113">Administration and Diagnostics</span></span>](../index.md)
