---
title: Überlegungen zur Sicherheit in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: ed0f018e0151e68afeb9a4747bf8a260faa184b1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601035"
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="0bc8d-102">Überlegungen zur Sicherheit in WCF</span><span class="sxs-lookup"><span data-stu-id="0bc8d-102">Security Considerations in WCF</span></span>
<span data-ttu-id="0bc8d-103">In den Themen in diesem Abschnitt werden verschiedene sicherheitsrelevante Aspekte aufgeführt, die beim Entwerfen einer Windows Communication Foundation (WCF)-Anwendung zu beachten sind.</span><span class="sxs-lookup"><span data-stu-id="0bc8d-103">The topics in this section list various security-related items to consider when designing a Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0bc8d-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0bc8d-104">In This Section</span></span>  
 [<span data-ttu-id="0bc8d-105">Offenlegung von Informationen</span><span class="sxs-lookup"><span data-stu-id="0bc8d-105">Information Disclosure</span></span>](information-disclosure.md)  
 <span data-ttu-id="0bc8d-106">Erläutert, wie Informationen offengelegt und attackiert werden können und wie man diesen Gefahren begegnen kann.</span><span class="sxs-lookup"><span data-stu-id="0bc8d-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="0bc8d-107">Rechte Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="0bc8d-107">Elevation of Privilege</span></span>](elevation-of-privilege.md)  
 <span data-ttu-id="0bc8d-108">Erläutert die Konsequenzen, mit denen zu rechnen ist, wenn einem Angreifer Autorisierungsberechtigungen erteilt werden, die über die ursprünglichen Berechtigungen hinausgehen, und stellt mögliche Gegenmaßnahmen vor.</span><span class="sxs-lookup"><span data-stu-id="0bc8d-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="0bc8d-109">Denial of Service</span><span class="sxs-lookup"><span data-stu-id="0bc8d-109">Denial of Service</span></span>](denial-of-service.md)  
 <span data-ttu-id="0bc8d-110">Erläutert, was geschieht, wenn ein System Nachrichten nicht angemessen verarbeiten kann, und stellt mögliche Gegenmaßnahmen vor.</span><span class="sxs-lookup"><span data-stu-id="0bc8d-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="0bc8d-111">Manipulation</span><span class="sxs-lookup"><span data-stu-id="0bc8d-111">Tampering</span></span>](tampering.md)  
 <span data-ttu-id="0bc8d-112">Erläutert die Manipulation von Nachrichten bzw. des Sendens von Nachrichten und stellt mögliche Gegenmaßnahmen vor.</span><span class="sxs-lookup"><span data-stu-id="0bc8d-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="0bc8d-113">Wiederholungsangriffe</span><span class="sxs-lookup"><span data-stu-id="0bc8d-113">Replay Attacks</span></span>](replay-attacks.md)  
 <span data-ttu-id="0bc8d-114">Erläutert, was geschieht, wenn ein Angreifer einen Nachrichtenstrom zwischen zwei Parteien kopiert und den Strom für eine oder mehrere Parteien wiedergibt, und stellt mögliche Gegenmaßnahmen vor.</span><span class="sxs-lookup"><span data-stu-id="0bc8d-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="0bc8d-115">Sicherheitsüberlegungen für Sicherheitssitzungen</span><span class="sxs-lookup"><span data-stu-id="0bc8d-115">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="0bc8d-116">Erläutert die folgenden Punkte, die sich bei der Implementierung von Sicherheitssitzungen auf die Sicherheit auswirken.</span><span class="sxs-lookup"><span data-stu-id="0bc8d-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="0bc8d-117">Nicht unterstützte Szenarien</span><span class="sxs-lookup"><span data-stu-id="0bc8d-117">Unsupported Scenarios</span></span>](unsupported-scenarios.md)  
 <span data-ttu-id="0bc8d-118">Führt verschiedene Szenarien auf, die einen bestimmten Sicherheitsaspekt nicht unterstützen und vermieden bzw. mit bestimmten Überlegungen angegangen werden sollten.</span><span class="sxs-lookup"><span data-stu-id="0bc8d-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0bc8d-119">Referenz</span><span class="sxs-lookup"><span data-stu-id="0bc8d-119">Reference</span></span>  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="0bc8d-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="0bc8d-120">Related Sections</span></span>  
 [<span data-ttu-id="0bc8d-121">Sicherheitsleitfaden und empfohlene Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="0bc8d-121">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="0bc8d-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0bc8d-122">See also</span></span>

- [<span data-ttu-id="0bc8d-123">Security</span><span class="sxs-lookup"><span data-stu-id="0bc8d-123">Security</span></span>](security.md)
