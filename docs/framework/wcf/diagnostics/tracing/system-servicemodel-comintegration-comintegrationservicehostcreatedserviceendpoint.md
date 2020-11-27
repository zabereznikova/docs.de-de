---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: aeeba38eaf674453f4c87cf62f5088c55b5fde2d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290815"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="9c01c-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="9c01c-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>

<span data-ttu-id="9c01c-103">Nachricht kann nicht verschoben oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="9c01c-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9c01c-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9c01c-104">Description</span></span>  

 <span data-ttu-id="9c01c-105">Die Ablaufverfolgung gibt an, dass beim Versuch, eine MSMQ-Nachricht zu verschieben, zu löschen oder abzulehnen ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9c01c-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="9c01c-106">MSMQ-Nachrichten werden von Windows Communication Foundation (WCF) eingesetzt (bei Verwendung mit NetMsmqBinding oder MsmqIntegrationBinding). Diese Ablauf Verfolgung bezieht sich auf den ausgewählten Wert der `ReceiveErrorHandling` Eigenschaft auf NetMsmqBinding oder MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="9c01c-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="9c01c-107">Diese Ablaufverfolgung weist nicht auf einen Fehler des gesamten Systems hin.</span><span class="sxs-lookup"><span data-stu-id="9c01c-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="9c01c-108">Sie gibt jedoch an, dass die ausgewählte Disposition für nicht verarbeitbare Nachrichten für eine Nachricht fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="9c01c-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="9c01c-109">Weitere Informationen darüber, wann Nachrichten beschädigt werden und wie Sie den Dienst so konfigurieren, dass Sie entsprechend behandelt werden, finden Sie unter [Behandlung](../../feature-details/poison-message-handling.md)nicht verarbeitbarer Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="9c01c-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c01c-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c01c-110">See also</span></span>

- [<span data-ttu-id="9c01c-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="9c01c-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="9c01c-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="9c01c-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="9c01c-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="9c01c-113">Administration and Diagnostics</span></span>](../index.md)
