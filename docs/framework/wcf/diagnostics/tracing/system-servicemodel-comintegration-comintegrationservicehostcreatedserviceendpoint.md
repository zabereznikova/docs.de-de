---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: f89dd1373d67714046f8cb958582c3a5dea04456
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674791"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="fc1f9-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="fc1f9-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="fc1f9-103">Nachricht kann nicht verschoben oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="fc1f9-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="fc1f9-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc1f9-104">Description</span></span>  
 <span data-ttu-id="fc1f9-105">Die Ablaufverfolgung gibt an, dass beim Versuch, eine MSMQ-Nachricht zu verschieben, zu löschen oder abzulehnen ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="fc1f9-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="fc1f9-106">MSMQ-Nachrichten werden von Windows Communication Foundation (WCF) verwendet (wenn sie entweder mit NetMsmqBinding oder MsmqIntegrationBinding verwendet werden). Diese Ablaufverfolgung bezieht sich auf `ReceiveErrorHandling` den ausgewählten Wert der Eigenschaft auf der NetMsmqBinding oder MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="fc1f9-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="fc1f9-107">Diese Ablaufverfolgung weist nicht auf einen Fehler des gesamten Systems hin.</span><span class="sxs-lookup"><span data-stu-id="fc1f9-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="fc1f9-108">Sie gibt jedoch an, dass die ausgewählte Disposition für nicht verarbeitbare Nachrichten für eine Nachricht fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="fc1f9-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="fc1f9-109">Weitere Informationen dazu, wann Nachrichten zu Gift werden und wie Sie Ihren Dienst so konfigurieren, dass er entsprechend behandelt wird, finden Sie unter [Gift-Nachrichten-Handhabung](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="fc1f9-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc1f9-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc1f9-110">See also</span></span>

- [<span data-ttu-id="fc1f9-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="fc1f9-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="fc1f9-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="fc1f9-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="fc1f9-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="fc1f9-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
