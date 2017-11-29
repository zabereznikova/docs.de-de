---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4cecacdcc9ec1155fbb374bb763f6858da6ccc57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="f4171-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="f4171-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="f4171-103">Nachricht kann nicht verschoben oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f4171-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f4171-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4171-104">Description</span></span>  
 <span data-ttu-id="f4171-105">Die Ablaufverfolgung gibt an, dass beim Versuch, eine MSMQ-Nachricht zu verschieben, zu löschen oder abzulehnen ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f4171-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="f4171-106">MSMQ-Nachrichten werden von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] verwendet (wenn entweder mit der NetMsmqBinding oder der MsmqIntegrationBinding benutzt). Diese Ablaufverfolgung ist bezieht sich auf den ausgewählten Wert der `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="f4171-106">MSMQ messages are employed by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="f4171-107">Diese Ablaufverfolgung weist nicht auf einen Fehler des gesamten Systems hin.</span><span class="sxs-lookup"><span data-stu-id="f4171-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="f4171-108">Sie gibt jedoch an, dass die ausgewählte Disposition für nicht verarbeitbare Nachrichten für eine Nachricht fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="f4171-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="f4171-109">Finden Sie unter [verarbeitbarer Behandlung von](http://go.microsoft.com/fwlink/?LinkID=99546) detaillierte Informationen auf, wenn Nachrichten werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f4171-109">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4171-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4171-110">See Also</span></span>  
 [<span data-ttu-id="f4171-111">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f4171-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f4171-112">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="f4171-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f4171-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="f4171-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
