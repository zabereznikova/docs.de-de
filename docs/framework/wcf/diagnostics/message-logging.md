---
title: Nachrichtenprotokollierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6bce0682-75ef-4d65-a659-b328fba4a8b5
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 04e1b881d9aab1c35195794394cddf5172288cc1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="message-logging"></a><span data-ttu-id="ba9ab-102">Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="ba9ab-102">Message Logging</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="ba9ab-103"> ermöglicht das Protokollieren eingehender und ausgehender Nachrichten, um diese offline zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba9ab-103"> provides the capability to log incoming and outgoing messages for offline consumption.</span></span> <span data-ttu-id="ba9ab-104">Bei der Nachrichtenprotokollierung können Sie die Nachricht und den Nachrichtentext sehen.</span><span class="sxs-lookup"><span data-stu-id="ba9ab-104">Message logging enables you to see what the message and message body looks like.</span></span> <span data-ttu-id="ba9ab-105">Diese Art der Protokollierung ist besonders hilfreich, um zu sehen, welche Argumente übergeben und wie diese vom empfangenden Endpunkt als XML empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="ba9ab-105">This type of logging is particularly helpful in letting you know what arguments were passed in and how the receiving endpoint saw the arguments expressed as XML.</span></span> <span data-ttu-id="ba9ab-106">Indem Sie die Nachricht protokollieren, wie sie empfangen wurde, können Sie außerdem falsch formatierte Nachrichten erkennen und sehen, wie die Nachricht empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba9ab-106">In addition, logging the message as it was received allows you to diagnose malformed messages as well as to see how the message arrived.</span></span> <span data-ttu-id="ba9ab-107">Außerdem können Sie die verwendeten Sicherheitstoken, verschlüsselte und signierte Nachrichtenteile sowie unveränderte Nachrichtenteile untersuchen.</span><span class="sxs-lookup"><span data-stu-id="ba9ab-107">You can also examine the security tokens used, parts encrypted and signed, and parts left intact.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba9ab-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ba9ab-108">In This Section</span></span>  
 [<span data-ttu-id="ba9ab-109">Übersicht über den Nachrichtenfluss</span><span class="sxs-lookup"><span data-stu-id="ba9ab-109">Message Flow Overview</span></span>](../../../../docs/framework/wcf/diagnostics/message-flow-overview.md)  
  
 <span data-ttu-id="ba9ab-110">In diesem Thema wird beschrieben, wie sich Ereignisprotokollnachrichten Client- und Serverereignissen zuordnen lassen.</span><span class="sxs-lookup"><span data-stu-id="ba9ab-110">This topic describes how event log messages correspond to client and service events.</span></span>  
  
 [<span data-ttu-id="ba9ab-111">Konfigurieren der Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="ba9ab-111">Configuring Message Logging</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
  
 <span data-ttu-id="ba9ab-112">In diesem Thema wird beschrieben, wie Sie die Nachrichtenprotokollierung für verschiedene Szenarien konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="ba9ab-112">This topic describes how you can configure message logging for different scenarios.</span></span>  
  
 [<span data-ttu-id="ba9ab-113">Anzeigen von Nachrichtenprotokollen</span><span class="sxs-lookup"><span data-stu-id="ba9ab-113">Viewing Message Logs</span></span>](../../../../docs/framework/wcf/diagnostics/viewing-message-logs.md)  
  
 <span data-ttu-id="ba9ab-114">In diesem Thema wird beschrieben, wie Sie Nachrichtenprotokolle anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="ba9ab-114">This topic describes how you can view message logs.</span></span>  
  
 [<span data-ttu-id="ba9ab-115">Sicherheitsaspekte für Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="ba9ab-115">Security Concerns for Message Logging</span></span>](../../../../docs/framework/wcf/diagnostics/security-concerns-for-message-logging.md)  
  
 <span data-ttu-id="ba9ab-116">In diesem Thema wird beschrieben, wie Sie vertrauliche Daten davor schützen, in Nachrichtenprotokollen verfügbar gemacht zu werden, wie auch Ereignisse, die von der Nachrichtenprotokollierung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="ba9ab-116">This topic describes how you can protect sensitive data from being exposed in message logs, as well as events generated by message logging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba9ab-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba9ab-117">See Also</span></span>  
 [<span data-ttu-id="ba9ab-118">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="ba9ab-118">Administration and Diagnostics</span></span>](../../../../docs/framework/wcf/diagnostics/index.md)
