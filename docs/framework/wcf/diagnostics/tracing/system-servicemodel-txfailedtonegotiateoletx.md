---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 7b468a57409e9a473a5bbf8e3324435e65e8c60b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295313"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="73692-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="73692-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>

<span data-ttu-id="73692-103">Die OleTransactions-Protokollverhandlung wurde nicht für den angegebenen Koordinationskontext abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="73692-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="73692-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="73692-104">Description</span></span>  

 <span data-ttu-id="73692-105">Verfolgt nach, wann eine eingehende Transaktion mit OleTx-Informationen die angehängten OleTx-Informationen nicht verwenden kann und stattdessen wieder zur Nutzung des WS-AT zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="73692-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="73692-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="73692-106">Troubleshooting</span></span>  

 <span data-ttu-id="73692-107">Gibt ein potenzielles Problem mit MSDTC RPC-Kommunikation zwischen den Computern an.</span><span class="sxs-lookup"><span data-stu-id="73692-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="73692-108">Wenn viele dieser Ablaufverfolgungen im Protokoll angezeigt werden, kann sich eine drastische Abnahme der Leistung ergeben.</span><span class="sxs-lookup"><span data-stu-id="73692-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="73692-109">Wenn OleTx nicht gewünscht wird, legen Sie `OleTxUpgradeEnabled` in der WS-AT-Registrierungskonfiguration auf 0 (null) fest.</span><span class="sxs-lookup"><span data-stu-id="73692-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73692-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="73692-110">See also</span></span>

- [<span data-ttu-id="73692-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="73692-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="73692-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="73692-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="73692-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="73692-113">Administration and Diagnostics</span></span>](../index.md)
