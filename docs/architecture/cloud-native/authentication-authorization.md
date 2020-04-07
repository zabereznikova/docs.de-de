---
title: Authentifizierung und Autorisierung in Cloud-nativen Apps
description: Architektur von Cloud Native .NET-Apps für Azure | Authentifizierung und Autorisierung in Cloud Native Apps
ms.date: 03/02/2020
ms.openlocfilehash: 6261a0a72405bc1c984a04a7851aea4dd6664ddf
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805546"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a><span data-ttu-id="74b1e-103">Authentifizierung und Autorisierung in cloudbasierten Apps</span><span class="sxs-lookup"><span data-stu-id="74b1e-103">Authentication and authorization in cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="74b1e-104">Bei der *Authentifizierung* wird die Identität eines Sicherheitsprinzipals ermittelt.</span><span class="sxs-lookup"><span data-stu-id="74b1e-104">*Authentication* is the process of determining the identity of a security principal.</span></span> <span data-ttu-id="74b1e-105">*Die Autorisierung* ist der Akt, bei dem eine authentifizierte Prinzipalberechtigung zum Ausführen einer Aktion oder zum Zugriff auf eine Ressource erteilt wird.</span><span class="sxs-lookup"><span data-stu-id="74b1e-105">*Authorization* is the act of granting an authenticated principal permission to perform an action or access a resource.</span></span> <span data-ttu-id="74b1e-106">Manchmal wird die `AuthN` Authentifizierung verkürzt `AuthZ`und die Autorisierung auf .</span><span class="sxs-lookup"><span data-stu-id="74b1e-106">Sometimes authentication is shortened to `AuthN` and authorization is shortened to `AuthZ`.</span></span> <span data-ttu-id="74b1e-107">Cloud-native Anwendungen müssen sich auf offene HTTP-basierte Protokolle verlassen, um Sicherheitsprinzipale zu authentifizieren, da sowohl Clients als auch Anwendungen auf jeder Plattform oder jedem Gerät überall auf der Welt ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="74b1e-107">Cloud-native applications need to rely on open HTTP-based protocols to authenticate security principals since both clients and applications could be running anywhere in the world on any platform or device.</span></span> <span data-ttu-id="74b1e-108">Der einzige häufige Faktor ist HTTP.</span><span class="sxs-lookup"><span data-stu-id="74b1e-108">The only common factor is HTTP.</span></span>

<span data-ttu-id="74b1e-109">Viele Organisationen verlassen sich weiterhin auf lokale Authentifizierungsdienste wie Active Directory Federation Services (ADFS).</span><span class="sxs-lookup"><span data-stu-id="74b1e-109">Many organizations still rely on local authentication services like Active Directory Federation Services (ADFS).</span></span> <span data-ttu-id="74b1e-110">Während dieser Ansatz Unternehmen traditionell gut für lokale Authentifizierungsanforderungen eignet, profitieren Cloud-native Anwendungen von Systemen, die speziell für die Cloud entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="74b1e-110">While this approach has traditionally served organizations well for on premises authentication needs, cloud-native applications benefit from systems designed specifically for the cloud.</span></span> <span data-ttu-id="74b1e-111">In einer kürzlich veröffentlichten Empfehlung des United Kingdom National Cyber Security Centre (NCSC) aus dem Jahr 2019 heißt es, dass "Organisationen, die Azure AD als primäre Authentifizierungsquelle verwenden, ihr Risiko im Vergleich zu ADFS tatsächlich senken werden."</span><span class="sxs-lookup"><span data-stu-id="74b1e-111">A recent 2019 United Kingdom National Cyber Security Centre (NCSC) advisory states that "organizations using Azure AD as their primary authentication source will actually lower their risk compared to ADFS."</span></span> <span data-ttu-id="74b1e-112">Zu den in [dieser Analyse](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) beschriebenen Gründen gehören:</span><span class="sxs-lookup"><span data-stu-id="74b1e-112">Some reasons outlined in [this analysis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) include:</span></span>

- <span data-ttu-id="74b1e-113">Zugriff auf den vollständigen Satz von Microsoft-Technologien zum Schutz von Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="74b1e-113">Access to full set of Microsoft credential protection technologies.</span></span>
- <span data-ttu-id="74b1e-114">Die meisten Organisationen verlassen sich bereits in gewissem Maße auf Azure AD.</span><span class="sxs-lookup"><span data-stu-id="74b1e-114">Most organizations are already relying on Azure AD to some extent.</span></span>
- <span data-ttu-id="74b1e-115">Doppeltes Hashing von NTLM-Hashes stellt sicher, dass eine Gefährdung keine Anmeldeinformationen zulässt, die in lokalem Active Directory funktionieren.</span><span class="sxs-lookup"><span data-stu-id="74b1e-115">Double hashing of NTLM hashes ensures compromise won't allow credentials that work in local Active Directory.</span></span>

## <a name="references"></a><span data-ttu-id="74b1e-116">References</span><span class="sxs-lookup"><span data-stu-id="74b1e-116">References</span></span>

- [<span data-ttu-id="74b1e-117">Authentifizierungsgrundlagen</span><span class="sxs-lookup"><span data-stu-id="74b1e-117">Authentication basics</span></span>](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [<span data-ttu-id="74b1e-118">Zugriff auf Token und Ansprüche</span><span class="sxs-lookup"><span data-stu-id="74b1e-118">Access tokens and claims</span></span>](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [<span data-ttu-id="74b1e-119">Es kann an der Zeit sein, Ihre lokalen Authentifizierungsdienste zu verwerfen</span><span class="sxs-lookup"><span data-stu-id="74b1e-119">It may be time to ditch your on premises authentication services</span></span>](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
><span data-ttu-id="74b1e-120">[Zurück](identity.md)
>[Weiter](azure-active-directory.md)</span><span class="sxs-lookup"><span data-stu-id="74b1e-120">[Previous](identity.md)
[Next](azure-active-directory.md)</span></span>
