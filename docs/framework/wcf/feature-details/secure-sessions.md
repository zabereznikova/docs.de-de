---
title: Sichere Sitzungen
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: fd8406af0c37981b2ddc7ab8ddb0c82c63cbc0b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288545"
---
# <a name="secure-sessions"></a><span data-ttu-id="3cc95-102">Sichere Sitzungen</span><span class="sxs-lookup"><span data-stu-id="3cc95-102">Secure Sessions</span></span>

<span data-ttu-id="3cc95-103">Eine Funktion von Windows Communication Foundation (WCF) sind zuverlässige Sitzungen, die garantieren, dass Nachrichten in der Reihenfolge empfangen werden, in der Sie gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="3cc95-103">A feature of Windows Communication Foundation (WCF) is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="3cc95-104">Die Themen in diesem Abschnitt erläutern die Sicherheitsaspekte, die bei der Erstellung einer zuverlässigen Sitzung beachtet werden sollten.</span><span class="sxs-lookup"><span data-stu-id="3cc95-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="3cc95-105">Weitere Informationen zu zuverlässigen Sitzungen finden Sie unter [Verwenden von Sitzungen](../using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="3cc95-105">For more information about reliable sessions, see [Using Sessions](../using-sessions.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3cc95-106">Wenn ein Identitätswechsel auf Windows XP erforderlich ist, verwenden Sie eine sichere Sitzung ohne zustandsbehaftete Token für den Sicherheitskontext (SCT).</span><span class="sxs-lookup"><span data-stu-id="3cc95-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="3cc95-107">Wenn zustandsbehaftete Token für den Sicherheitskontext (SCTs) mit einem Identitätswechsel verwendet werden, wird ein <xref:System.InvalidOperationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="3cc95-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="3cc95-108">Weitere Informationen finden Sie unter [nicht unterstützte Szenarien](unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="3cc95-108">For more information, see [Unsupported Scenarios](unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3cc95-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3cc95-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="3cc95-110">Sichere Unterhaltungen und sichere Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="3cc95-110">Secure Conversations and Secure Sessions</span></span>](secure-conversations-and-secure-sessions.md)|<span data-ttu-id="3cc95-111">Sichere Konversationen und sichere Sitzungen werden synonym verwendet.</span><span class="sxs-lookup"><span data-stu-id="3cc95-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="3cc95-112">In diesem Thema wird erläutert, wie eine sichere Konversation funktioniert und wann und warum das Muster verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3cc95-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="3cc95-113">Vorgehensweise: Erstellen einer sicheren Sitzung</span><span class="sxs-lookup"><span data-stu-id="3cc95-113">How to: Create a Secure Session</span></span>](how-to-create-a-secure-session.md)|<span data-ttu-id="3cc95-114">Stellt exemplarisch die Grundlagen der Erstellung einer sicheren Sitzung vor.</span><span class="sxs-lookup"><span data-stu-id="3cc95-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="3cc95-115">Vorgehensweise: Erstellen eines Tokens für den Sicherheitskontext einer sicheren Sitzung</span><span class="sxs-lookup"><span data-stu-id="3cc95-115">How to: Create a Security Context Token for a Secure Session</span></span>](how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="3cc95-116">Stellt exemplarisch die Schritte der Erstellung einer Webfarm vor, die den Zustand und Sitzungen mit Clients beibehält.</span><span class="sxs-lookup"><span data-stu-id="3cc95-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="3cc95-117">Sicherheitsüberlegungen für Sicherheitssitzungen</span><span class="sxs-lookup"><span data-stu-id="3cc95-117">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)|<span data-ttu-id="3cc95-118">Beschreibt besondere Überlegungen für sichere Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="3cc95-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="3cc95-119">Referenz</span><span class="sxs-lookup"><span data-stu-id="3cc95-119">Reference</span></span>  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="3cc95-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="3cc95-120">Related Sections</span></span>  

 [<span data-ttu-id="3cc95-121">Sitzungen, Instanziierung und Parallelität</span><span class="sxs-lookup"><span data-stu-id="3cc95-121">Sessions, Instancing, and Concurrency</span></span>](sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="3cc95-122">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="3cc95-122">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="3cc95-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3cc95-123">See also</span></span>

- [<span data-ttu-id="3cc95-124">Vorgehensweise: Aktivieren der Nachrichtenreplay-Erkennung</span><span class="sxs-lookup"><span data-stu-id="3cc95-124">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)
- [<span data-ttu-id="3cc95-125">Wiederholungsangriffe</span><span class="sxs-lookup"><span data-stu-id="3cc95-125">Replay Attacks</span></span>](replay-attacks.md)
- [<span data-ttu-id="3cc95-126">Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert</span><span class="sxs-lookup"><span data-stu-id="3cc95-126">How to: Create a Service That Requires Sessions</span></span>](how-to-create-a-service-that-requires-sessions.md)
