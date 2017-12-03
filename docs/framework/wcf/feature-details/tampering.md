---
title: "Verfälschungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 96ab38de1fb2a932fefd4e37cbfab3d9bfbea616
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="tampering"></a><span data-ttu-id="43953-102">Verfälschungen</span><span class="sxs-lookup"><span data-stu-id="43953-102">Tampering</span></span>
<span data-ttu-id="43953-103">*Manipulationen* dient der Änderung einer Nachricht oder der Lieferung einer Nachricht und die Nutzung der geänderten Nachrichten für einen Zweck als Ihren Zweck wurde.</span><span class="sxs-lookup"><span data-stu-id="43953-103">*Tampering* is the act of altering a message, or the delivery of a message, and using the altered message for a purpose other than what it was intended for.</span></span>  
  
## <a name="do-not-disable-ws-addressing"></a><span data-ttu-id="43953-104">Deaktivieren Sie die WS-Adressierung nicht</span><span class="sxs-lookup"><span data-stu-id="43953-104">Do Not Disable WS-Addressing</span></span>  
 <span data-ttu-id="43953-105">Die WS-Adressierungsspezifikation bietet Adressheader für jede Nachricht, wodurch ein Nachrichtempfänger den Absender einer Nachricht bestätigen kann.</span><span class="sxs-lookup"><span data-stu-id="43953-105">The WS-Addressing specification provides address headers on each message, allowing a message recipient to verify the sender of the message.</span></span> <span data-ttu-id="43953-106">Sie können diese Funktion deaktivieren, indem Sie die <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>-Eigenschaft auf <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> festlegen.</span><span class="sxs-lookup"><span data-stu-id="43953-106">You can disable this feature by setting the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="43953-107">Wenn der Sicherheitsmodus auf "Nachricht" festgelegt ist und die WS-Adressierung deaktiviert, kann ein Angreifer eine Anforderung von einem Client nehmen und diese an einen anderen Dienst senden. Der zweite Dienst kann nicht erkennen, dass die Nachricht vom Original-Client kam.</span><span class="sxs-lookup"><span data-stu-id="43953-107">When the security mode is set to Message, and if WS-Addressing is disabled, an attacker could take a request from a client and send it to another service, and the second service has no way of detecting that the message came from the original client.</span></span> <span data-ttu-id="43953-108">Der erste Dienst kann bei der Kommunikation mit dem zweiten Dienst vorgeben, ein Client zu sein.</span><span class="sxs-lookup"><span data-stu-id="43953-108">In effect, the first service can pretend that it is a client when talking to the second service.</span></span>  
  
 <span data-ttu-id="43953-109">Um dieses Problem zu lösen, sollten Sie nie die <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>-Eigenschaft auf <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> festlegen und die Nutzung von <xref:System.ServiceModel.Channels.MessageVersion> vermeiden, z. B. die statistische <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A>-Eigenschaft, die die <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>-Eigenschaft auf <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> setzt.</span><span class="sxs-lookup"><span data-stu-id="43953-109">To mitigate this, never set the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>, and avoid the use of <xref:System.ServiceModel.Channels.MessageVersion>, such as the static <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> property, which sets the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43953-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43953-110">See Also</span></span>  
 [<span data-ttu-id="43953-111">Überlegungen zur Sicherheit</span><span class="sxs-lookup"><span data-stu-id="43953-111">Security Considerations</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [<span data-ttu-id="43953-112">Offenlegung von Informationen</span><span class="sxs-lookup"><span data-stu-id="43953-112">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 [<span data-ttu-id="43953-113">Ausweitung von Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="43953-113">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [<span data-ttu-id="43953-114">Denial of Service</span><span class="sxs-lookup"><span data-stu-id="43953-114">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [<span data-ttu-id="43953-115">Nicht unterstützte Szenarien</span><span class="sxs-lookup"><span data-stu-id="43953-115">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 [<span data-ttu-id="43953-116">Replay-Angriffe</span><span class="sxs-lookup"><span data-stu-id="43953-116">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
