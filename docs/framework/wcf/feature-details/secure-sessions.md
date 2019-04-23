---
title: Sichere Sitzungen
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: 8f5cf9a965951bcc1049c2e96ae6cfa80b0113ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084959"
---
# <a name="secure-sessions"></a><span data-ttu-id="d1296-102">Sichere Sitzungen</span><span class="sxs-lookup"><span data-stu-id="d1296-102">Secure Sessions</span></span>
<span data-ttu-id="d1296-103">Ein Feature von Windows Communication Foundation (WCF) ist die zuverlässige Sitzungen, die garantieren, dass Nachrichten in der Reihenfolge empfangen werden, die sie gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="d1296-103">A feature of Windows Communication Foundation (WCF) is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="d1296-104">Die Themen in diesem Abschnitt erläutern die Sicherheitsaspekte, die bei der Erstellung einer zuverlässigen Sitzung beachtet werden sollten.</span><span class="sxs-lookup"><span data-stu-id="d1296-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="d1296-105">Weitere Informationen zu zuverlässigen Sitzungen finden Sie unter [mithilfe von Sitzungen](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="d1296-105">For more information about reliable sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1296-106">Wenn ein Identitätswechsel auf Windows XP erforderlich ist, verwenden Sie eine sichere Sitzung ohne zustandsbehaftete Token für den Sicherheitskontext (SCT).</span><span class="sxs-lookup"><span data-stu-id="d1296-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="d1296-107">Wenn zustandsbehaftete Token für den Sicherheitskontext (SCTs) mit einem Identitätswechsel verwendet werden, wird ein <xref:System.InvalidOperationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d1296-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="d1296-108">Weitere Informationen finden Sie unter [nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="d1296-108">For more information, see [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1296-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d1296-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="d1296-110">Sichere Unterhaltungen und sichere Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="d1296-110">Secure Conversations and Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|<span data-ttu-id="d1296-111">Sichere Konversationen und sichere Sitzungen werden synonym verwendet.</span><span class="sxs-lookup"><span data-stu-id="d1296-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="d1296-112">In diesem Thema wird erläutert, wie eine sichere Konversation funktioniert und wann und warum das Muster verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d1296-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="d1296-113">Vorgehensweise: Erstellen einer sicheren Sitzung</span><span class="sxs-lookup"><span data-stu-id="d1296-113">How to: Create a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|<span data-ttu-id="d1296-114">Stellt exemplarisch die Grundlagen der Erstellung einer sicheren Sitzung vor.</span><span class="sxs-lookup"><span data-stu-id="d1296-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="d1296-115">Vorgehensweise: Erstellen Sie einen Sicherheitskontext für eine sichere Sitzung Token</span><span class="sxs-lookup"><span data-stu-id="d1296-115">How to: Create a Security Context Token for a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="d1296-116">Stellt exemplarisch die Schritte der Erstellung einer Webfarm vor, die den Zustand und Sitzungen mit Clients beibehält.</span><span class="sxs-lookup"><span data-stu-id="d1296-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="d1296-117">Sicherheitsüberlegungen für sichere Sitzungen</span><span class="sxs-lookup"><span data-stu-id="d1296-117">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|<span data-ttu-id="d1296-118">Beschreibt besondere Überlegungen für sichere Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="d1296-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="d1296-119">Referenz</span><span class="sxs-lookup"><span data-stu-id="d1296-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="d1296-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d1296-120">Related Sections</span></span>  
 [<span data-ttu-id="d1296-121">Sitzungen, Instanzerstellung und Parallelität</span><span class="sxs-lookup"><span data-stu-id="d1296-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="d1296-122">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="d1296-122">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="d1296-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1296-123">See also</span></span>

- [<span data-ttu-id="d1296-124">Vorgehensweise: Aktivieren der Nachrichtenreplay-Erkennung</span><span class="sxs-lookup"><span data-stu-id="d1296-124">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)
- [<span data-ttu-id="d1296-125">Replayangriffe</span><span class="sxs-lookup"><span data-stu-id="d1296-125">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
- [<span data-ttu-id="d1296-126">Vorgehensweise: Erstellen Sie einen Dienst, der Sitzungen erfordert</span><span class="sxs-lookup"><span data-stu-id="d1296-126">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
