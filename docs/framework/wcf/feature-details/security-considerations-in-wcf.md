---
title: Überlegungen zur Sicherheit in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: 16b3afe9540f3e2953311f602408fce5412be2eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112215"
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="3618c-102">Überlegungen zur Sicherheit in WCF</span><span class="sxs-lookup"><span data-stu-id="3618c-102">Security Considerations in WCF</span></span>
<span data-ttu-id="3618c-103">Die Themen in diesem Abschnitt Liste verschiedene sicherheitsrelevante Punkte beim Entwerfen einer Windows Communication Foundation (WCF)-Anwendung zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="3618c-103">The topics in this section list various security-related items to consider when designing a Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3618c-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3618c-104">In This Section</span></span>  
 [<span data-ttu-id="3618c-105">Veröffentlichung von Informationen</span><span class="sxs-lookup"><span data-stu-id="3618c-105">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 <span data-ttu-id="3618c-106">Erläutert, wie Informationen offengelegt und attackiert werden können und wie man diesen Gefahren begegnen kann.</span><span class="sxs-lookup"><span data-stu-id="3618c-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="3618c-107">Angriffe durch Rechteerweiterung</span><span class="sxs-lookup"><span data-stu-id="3618c-107">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 <span data-ttu-id="3618c-108">Erläutert die Konsequenzen, mit denen zu rechnen ist, wenn einem Angreifer Autorisierungsberechtigungen erteilt werden, die über die ursprünglichen Berechtigungen hinausgehen, und stellt mögliche Gegenmaßnahmen vor.</span><span class="sxs-lookup"><span data-stu-id="3618c-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="3618c-109">Dienstverweigerung (Denial of Service)</span><span class="sxs-lookup"><span data-stu-id="3618c-109">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 <span data-ttu-id="3618c-110">Erläutert, was geschieht, wenn ein System Nachrichten nicht angemessen verarbeiten kann, und stellt mögliche Gegenmaßnahmen vor.</span><span class="sxs-lookup"><span data-stu-id="3618c-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="3618c-111">Verfälschungen</span><span class="sxs-lookup"><span data-stu-id="3618c-111">Tampering</span></span>](../../../../docs/framework/wcf/feature-details/tampering.md)  
 <span data-ttu-id="3618c-112">Erläutert die Manipulation von Nachrichten bzw. des Sendens von Nachrichten und stellt mögliche Gegenmaßnahmen vor.</span><span class="sxs-lookup"><span data-stu-id="3618c-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="3618c-113">Wiederholungsangriffe</span><span class="sxs-lookup"><span data-stu-id="3618c-113">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 <span data-ttu-id="3618c-114">Erläutert, was geschieht, wenn ein Angreifer einen Nachrichtenstrom zwischen zwei Parteien kopiert und den Strom für eine oder mehrere Parteien wiedergibt, und stellt mögliche Gegenmaßnahmen vor.</span><span class="sxs-lookup"><span data-stu-id="3618c-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="3618c-115">Sicherheitsüberlegungen für Sicherheitssitzungen</span><span class="sxs-lookup"><span data-stu-id="3618c-115">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="3618c-116">Erläutert die folgenden Punkte, die sich bei der Implementierung von Sicherheitssitzungen auf die Sicherheit auswirken.</span><span class="sxs-lookup"><span data-stu-id="3618c-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="3618c-117">Nicht unterstützte Szenarien</span><span class="sxs-lookup"><span data-stu-id="3618c-117">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 <span data-ttu-id="3618c-118">Führt verschiedene Szenarien auf, die einen bestimmten Sicherheitsaspekt nicht unterstützen und vermieden bzw. mit bestimmten Überlegungen angegangen werden sollten.</span><span class="sxs-lookup"><span data-stu-id="3618c-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3618c-119">Referenz</span><span class="sxs-lookup"><span data-stu-id="3618c-119">Reference</span></span>  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="3618c-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="3618c-120">Related Sections</span></span>  
 [<span data-ttu-id="3618c-121">Sicherheitsleitfaden und empfohlene Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="3618c-121">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="3618c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3618c-122">See also</span></span>

- [<span data-ttu-id="3618c-123">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3618c-123">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
