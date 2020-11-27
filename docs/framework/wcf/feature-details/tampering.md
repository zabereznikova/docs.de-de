---
title: Manipulation
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: c2b0cae1dc57fac486122ca17fc8109ffe62f77d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249799"
---
# <a name="tampering"></a><span data-ttu-id="7c0c3-102">Manipulation</span><span class="sxs-lookup"><span data-stu-id="7c0c3-102">Tampering</span></span>

<span data-ttu-id="7c0c3-103">*Manipulationen* sind das Ändern einer Nachricht oder die Übermittlung einer Nachricht und die Verwendung der geänderten Nachricht für einen anderen Zweck als die für Sie vorgesehene Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="7c0c3-103">*Tampering* is the act of altering a message, or the delivery of a message, and using the altered message for a purpose other than what it was intended for.</span></span>  
  
## <a name="do-not-disable-ws-addressing"></a><span data-ttu-id="7c0c3-104">Deaktivieren Sie die WS-Adressierung nicht</span><span class="sxs-lookup"><span data-stu-id="7c0c3-104">Do Not Disable WS-Addressing</span></span>  

 <span data-ttu-id="7c0c3-105">Die WS-Adressierungsspezifikation bietet Adressheader für jede Nachricht, wodurch ein Nachrichtempfänger den Absender einer Nachricht bestätigen kann.</span><span class="sxs-lookup"><span data-stu-id="7c0c3-105">The WS-Addressing specification provides address headers on each message, allowing a message recipient to verify the sender of the message.</span></span> <span data-ttu-id="7c0c3-106">Sie können diese Funktion deaktivieren, indem Sie die <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>-Eigenschaft auf <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> festlegen.</span><span class="sxs-lookup"><span data-stu-id="7c0c3-106">You can disable this feature by setting the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="7c0c3-107">Wenn der Sicherheitsmodus auf "Nachricht" festgelegt ist und die WS-Adressierung deaktiviert, kann ein Angreifer eine Anforderung von einem Client nehmen und diese an einen anderen Dienst senden. Der zweite Dienst kann nicht erkennen, dass die Nachricht vom Original-Client kam.</span><span class="sxs-lookup"><span data-stu-id="7c0c3-107">When the security mode is set to Message, and if WS-Addressing is disabled, an attacker could take a request from a client and send it to another service, and the second service has no way of detecting that the message came from the original client.</span></span> <span data-ttu-id="7c0c3-108">Der erste Dienst kann bei der Kommunikation mit dem zweiten Dienst vorgeben, ein Client zu sein.</span><span class="sxs-lookup"><span data-stu-id="7c0c3-108">In effect, the first service can pretend that it is a client when talking to the second service.</span></span>  
  
 <span data-ttu-id="7c0c3-109">Um dieses Problem zu lösen, sollten Sie nie die <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>-Eigenschaft auf <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> festlegen und die Nutzung von <xref:System.ServiceModel.Channels.MessageVersion> vermeiden, z. B. die statistische <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A>-Eigenschaft, die die <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>-Eigenschaft auf <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> setzt.</span><span class="sxs-lookup"><span data-stu-id="7c0c3-109">To mitigate this, never set the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>, and avoid the use of <xref:System.ServiceModel.Channels.MessageVersion>, such as the static <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> property, which sets the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c0c3-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7c0c3-110">See also</span></span>

- [<span data-ttu-id="7c0c3-111">Sicherheitshinweise</span><span class="sxs-lookup"><span data-stu-id="7c0c3-111">Security Considerations</span></span>](security-considerations-in-wcf.md)
- [<span data-ttu-id="7c0c3-112">Veröffentlichung von Informationen</span><span class="sxs-lookup"><span data-stu-id="7c0c3-112">Information Disclosure</span></span>](information-disclosure.md)
- [<span data-ttu-id="7c0c3-113">Erhöhung von Rechten</span><span class="sxs-lookup"><span data-stu-id="7c0c3-113">Elevation of Privilege</span></span>](elevation-of-privilege.md)
- [<span data-ttu-id="7c0c3-114">Denial-of-Service</span><span class="sxs-lookup"><span data-stu-id="7c0c3-114">Denial of Service</span></span>](denial-of-service.md)
- [<span data-ttu-id="7c0c3-115">Nicht unterstützte Szenarien</span><span class="sxs-lookup"><span data-stu-id="7c0c3-115">Unsupported Scenarios</span></span>](unsupported-scenarios.md)
- [<span data-ttu-id="7c0c3-116">Wiederholungsangriffe</span><span class="sxs-lookup"><span data-stu-id="7c0c3-116">Replay Attacks</span></span>](replay-attacks.md)
