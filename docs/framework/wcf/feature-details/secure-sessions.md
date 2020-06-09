---
title: Sichere Sitzungen
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: cb02adc7514e27175088e7664b12e45bc8ca5cd9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590084"
---
# <a name="secure-sessions"></a><span data-ttu-id="66aca-102">Sichere Sitzungen</span><span class="sxs-lookup"><span data-stu-id="66aca-102">Secure Sessions</span></span>
<span data-ttu-id="66aca-103">Eine Funktion von Windows Communication Foundation (WCF) sind zuverlässige Sitzungen, die garantieren, dass Nachrichten in der Reihenfolge empfangen werden, in der Sie gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="66aca-103">A feature of Windows Communication Foundation (WCF) is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="66aca-104">Die Themen in diesem Abschnitt erläutern die Sicherheitsaspekte, die bei der Erstellung einer zuverlässigen Sitzung beachtet werden sollten.</span><span class="sxs-lookup"><span data-stu-id="66aca-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="66aca-105">Weitere Informationen zu zuverlässigen Sitzungen finden Sie unter [Verwenden von Sitzungen](../using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="66aca-105">For more information about reliable sessions, see [Using Sessions](../using-sessions.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66aca-106">Wenn ein Identitätswechsel auf Windows XP erforderlich ist, verwenden Sie eine sichere Sitzung ohne zustandsbehaftete Token für den Sicherheitskontext (SCT).</span><span class="sxs-lookup"><span data-stu-id="66aca-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="66aca-107">Wenn zustandsbehaftete Token für den Sicherheitskontext (SCTs) mit einem Identitätswechsel verwendet werden, wird ein <xref:System.InvalidOperationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="66aca-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="66aca-108">Weitere Informationen finden Sie unter [nicht unterstützte Szenarien](unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="66aca-108">For more information, see [Unsupported Scenarios](unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66aca-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="66aca-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="66aca-110">Sichere Unterhaltungen und sichere Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="66aca-110">Secure Conversations and Secure Sessions</span></span>](secure-conversations-and-secure-sessions.md)|<span data-ttu-id="66aca-111">Sichere Konversationen und sichere Sitzungen werden synonym verwendet.</span><span class="sxs-lookup"><span data-stu-id="66aca-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="66aca-112">In diesem Thema wird erläutert, wie eine sichere Konversation funktioniert und wann und warum das Muster verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66aca-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="66aca-113">Vorgehensweise: Erstellen einer sicheren Sitzung</span><span class="sxs-lookup"><span data-stu-id="66aca-113">How to: Create a Secure Session</span></span>](how-to-create-a-secure-session.md)|<span data-ttu-id="66aca-114">Stellt exemplarisch die Grundlagen der Erstellung einer sicheren Sitzung vor.</span><span class="sxs-lookup"><span data-stu-id="66aca-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="66aca-115">Vorgehensweise: Erstellen eines Tokens für den Sicherheitskontext einer sicheren Sitzung</span><span class="sxs-lookup"><span data-stu-id="66aca-115">How to: Create a Security Context Token for a Secure Session</span></span>](how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="66aca-116">Stellt exemplarisch die Schritte der Erstellung einer Webfarm vor, die den Zustand und Sitzungen mit Clients beibehält.</span><span class="sxs-lookup"><span data-stu-id="66aca-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="66aca-117">Sicherheitsüberlegungen für Sicherheitssitzungen</span><span class="sxs-lookup"><span data-stu-id="66aca-117">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)|<span data-ttu-id="66aca-118">Beschreibt besondere Überlegungen für sichere Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="66aca-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="66aca-119">Referenz</span><span class="sxs-lookup"><span data-stu-id="66aca-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="66aca-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="66aca-120">Related Sections</span></span>  
 [<span data-ttu-id="66aca-121">Sitzungen, Instanziierung und Parallelität</span><span class="sxs-lookup"><span data-stu-id="66aca-121">Sessions, Instancing, and Concurrency</span></span>](sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="66aca-122">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="66aca-122">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="66aca-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66aca-123">See also</span></span>

- [<span data-ttu-id="66aca-124">Vorgehensweise: Aktivieren der Nachrichtenreplay-Erkennung</span><span class="sxs-lookup"><span data-stu-id="66aca-124">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)
- [<span data-ttu-id="66aca-125">Wiederholungsangriffe</span><span class="sxs-lookup"><span data-stu-id="66aca-125">Replay Attacks</span></span>](replay-attacks.md)
- [<span data-ttu-id="66aca-126">Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert</span><span class="sxs-lookup"><span data-stu-id="66aca-126">How to: Create a Service That Requires Sessions</span></span>](how-to-create-a-service-that-requires-sessions.md)
