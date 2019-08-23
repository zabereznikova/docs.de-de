---
title: Sichere Sitzungen
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: d511a45d990e441c5dcfd8405794ec937c0278d1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966075"
---
# <a name="secure-sessions"></a><span data-ttu-id="93f4b-102">Sichere Sitzungen</span><span class="sxs-lookup"><span data-stu-id="93f4b-102">Secure Sessions</span></span>
<span data-ttu-id="93f4b-103">Eine Funktion von Windows Communication Foundation (WCF) sind zuverlässige Sitzungen, die garantieren, dass Nachrichten in der Reihenfolge empfangen werden, in der Sie gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="93f4b-103">A feature of Windows Communication Foundation (WCF) is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="93f4b-104">Die Themen in diesem Abschnitt erläutern die Sicherheitsaspekte, die bei der Erstellung einer zuverlässigen Sitzung beachtet werden sollten.</span><span class="sxs-lookup"><span data-stu-id="93f4b-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="93f4b-105">Weitere Informationen zu zuverlässigen Sitzungen finden Sie unter [Verwenden von Sitzungen](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="93f4b-105">For more information about reliable sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93f4b-106">Wenn ein Identitätswechsel auf Windows XP erforderlich ist, verwenden Sie eine sichere Sitzung ohne zustandsbehaftete Token für den Sicherheitskontext (SCT).</span><span class="sxs-lookup"><span data-stu-id="93f4b-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="93f4b-107">Wenn zustandsbehaftete Token für den Sicherheitskontext (SCTs) mit einem Identitätswechsel verwendet werden, wird ein <xref:System.InvalidOperationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="93f4b-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="93f4b-108">Weitere Informationen finden Sie unter [nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="93f4b-108">For more information, see [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93f4b-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="93f4b-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="93f4b-110">Sichere Unterhaltungen und sichere Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="93f4b-110">Secure Conversations and Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|<span data-ttu-id="93f4b-111">Sichere Konversationen und sichere Sitzungen werden synonym verwendet.</span><span class="sxs-lookup"><span data-stu-id="93f4b-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="93f4b-112">In diesem Thema wird erläutert, wie eine sichere Konversation funktioniert und wann und warum das Muster verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="93f4b-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="93f4b-113">Vorgehensweise: Erstellen einer sicheren Sitzung</span><span class="sxs-lookup"><span data-stu-id="93f4b-113">How to: Create a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|<span data-ttu-id="93f4b-114">Stellt exemplarisch die Grundlagen der Erstellung einer sicheren Sitzung vor.</span><span class="sxs-lookup"><span data-stu-id="93f4b-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="93f4b-115">Vorgehensweise: Erstellen eines Sicherheitskontext Tokens für eine sichere Sitzung</span><span class="sxs-lookup"><span data-stu-id="93f4b-115">How to: Create a Security Context Token for a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="93f4b-116">Stellt exemplarisch die Schritte der Erstellung einer Webfarm vor, die den Zustand und Sitzungen mit Clients beibehält.</span><span class="sxs-lookup"><span data-stu-id="93f4b-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="93f4b-117">Sicherheitsüberlegungen für sichere Sitzungen</span><span class="sxs-lookup"><span data-stu-id="93f4b-117">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|<span data-ttu-id="93f4b-118">Beschreibt besondere Überlegungen für sichere Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="93f4b-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="93f4b-119">Referenz</span><span class="sxs-lookup"><span data-stu-id="93f4b-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="93f4b-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="93f4b-120">Related Sections</span></span>  
 [<span data-ttu-id="93f4b-121">Sitzungen, Instanzerstellung und Parallelität</span><span class="sxs-lookup"><span data-stu-id="93f4b-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="93f4b-122">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="93f4b-122">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="93f4b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93f4b-123">See also</span></span>

- [<span data-ttu-id="93f4b-124">Vorgehensweise: Aktivieren der Erkennung von Nachrichten Wiedergabe</span><span class="sxs-lookup"><span data-stu-id="93f4b-124">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)
- [<span data-ttu-id="93f4b-125">Replayangriffe</span><span class="sxs-lookup"><span data-stu-id="93f4b-125">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
- [<span data-ttu-id="93f4b-126">Vorgehensweise: Erstellen eines Dienstanbieter, der Sitzungen erfordert</span><span class="sxs-lookup"><span data-stu-id="93f4b-126">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
