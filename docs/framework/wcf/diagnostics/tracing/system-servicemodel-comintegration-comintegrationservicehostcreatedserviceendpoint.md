---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: 0a28eec659b48d5add4c53bc8c16972892e65099
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487905"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="b01c0-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="b01c0-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="b01c0-103">Nachricht kann nicht verschoben oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b01c0-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b01c0-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b01c0-104">Description</span></span>  
 <span data-ttu-id="b01c0-105">Die Ablaufverfolgung gibt an, dass beim Versuch, eine MSMQ-Nachricht zu verschieben, zu löschen oder abzulehnen ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b01c0-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="b01c0-106">MSMQ-Nachrichten werden von Windows Communication Foundation (WCF) (bei Verwendung mit der NetMsmqBinding oder MsmqIntegrationBinding) verwendet. Diese Ablaufverfolgung ist bezieht sich auf den ausgewählten Wert von der `ReceiveErrorHandling` -Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="b01c0-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="b01c0-107">Diese Ablaufverfolgung weist nicht auf einen Fehler des gesamten Systems hin.</span><span class="sxs-lookup"><span data-stu-id="b01c0-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="b01c0-108">Sie gibt jedoch an, dass die ausgewählte Disposition für nicht verarbeitbare Nachrichten für eine Nachricht fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="b01c0-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="b01c0-109">Finden Sie unter [verarbeitbarer Behandlung von](http://go.microsoft.com/fwlink/?LinkID=99546) detaillierte Informationen auf, wenn Nachrichten werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b01c0-109">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b01c0-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b01c0-110">See Also</span></span>  
 [<span data-ttu-id="b01c0-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="b01c0-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="b01c0-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="b01c0-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="b01c0-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="b01c0-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
