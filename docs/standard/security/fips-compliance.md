---
title: Konformität mit der Konformität von .net Core
description: Erläutert die Konformität von .net Core Federal Information Processing Standard (fps).
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: cf640c857e79ae811dd38d57a0e5301b7bc96572
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74205077"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a><span data-ttu-id="fbf41-103">Konformität von .net Core-Federal Information Processing Standard (fps)</span><span class="sxs-lookup"><span data-stu-id="fbf41-103">.NET Core Federal Information Processing Standard (FIPS) compliance</span></span>

<span data-ttu-id="fbf41-104">Die Federal Information Processing Standard ()-Veröffentlichung 140-2 ist ein US-Regierungs Standard, der die minimalen Sicherheitsanforderungen für kryptografische Module in Informationstechnologie Produkten definiert, wie in Abschnitt 5131 der Informationen definiert. Technology Management-Reform Act von 1996.</span><span class="sxs-lookup"><span data-stu-id="fbf41-104">The Federal Information Processing Standard (FIPS) Publication 140-2 is a U.S. government standard that defines minimum security requirements for cryptographic modules in information technology products, as defined in Section 5131 of the Information Technology Management Reform Act of 1996.</span></span>

<span data-ttu-id="fbf41-105">.NET Core:</span><span class="sxs-lookup"><span data-stu-id="fbf41-105">.NET Core:</span></span>

* <span data-ttu-id="fbf41-106">Übergibt kryptografische primitive Aufrufe an die Standardmodule, die das zugrunde liegende Betriebssystem bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="fbf41-106">Passes cryptographic primitives calls through to the standard modules the underlying operating system provides.</span></span>
* <span data-ttu-id="fbf41-107">Erzwingt **nicht** die Verwendung von per PPS genehmigten Algorithmen oder Schlüsselgrößen in .net Core-apps.</span><span class="sxs-lookup"><span data-stu-id="fbf41-107">Does **not** enforce the use of FIPS Approved algorithms or key sizes in .NET Core apps.</span></span>

<span data-ttu-id="fbf41-108">Der Systemadministrator ist für die Konfiguration der Konformität mit der Konformität für ein Betriebssystem verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="fbf41-108">The system administrator is responsible for configuring the FIPS compliance for an operating system.</span></span>

<span data-ttu-id="fbf41-109">Wenn Code für eine mit PPS kompatible Umgebung geschrieben wird, ist der Entwickler dafür verantwortlich, sicherzustellen, dass nicht kompatible, nicht kompatible Filter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbf41-109">If code is written for a FIPS-compliant environment, the developer is responsible for ensuring that non-compliant FIPS algorithms aren't used.</span></span>

<span data-ttu-id="fbf41-110">Weitere Informationen zur Kompatibilität von Standards finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="fbf41-110">For more information on FIPS compliance, see the following articles:</span></span>

* [<span data-ttu-id="fbf41-111">Windows fi-Konformität</span><span class="sxs-lookup"><span data-stu-id="fbf41-111">Windows FIPS Compliance</span></span>](/windows/security/threat-protection/fips-140-validation)
* [<span data-ttu-id="fbf41-112">Konfigurieren von Windows für die Konformität mit dem PPS</span><span class="sxs-lookup"><span data-stu-id="fbf41-112">Configuring Windows for FIPS Compliance</span></span>](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [<span data-ttu-id="fbf41-113">10,2. Federal Information Processing Standard (fps)</span><span class="sxs-lookup"><span data-stu-id="fbf41-113">10.2. FEDERAL INFORMATION PROCESSING STANDARD (FIPS)</span></span>](https://access.redhat.com/documentation/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-federal_standards_and_regulations-federal_information_processing_standard)
