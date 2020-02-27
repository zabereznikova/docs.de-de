---
title: Konformität mit der Konformität von .net Core
description: Erläutert die Konformität von .net Core Federal Information Processing Standard (fps).
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: 84d6edc6975af0484bb67999ad5891eaf4db057d
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626957"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a><span data-ttu-id="84da2-103">Konformität von .net Core-Federal Information Processing Standard (fps)</span><span class="sxs-lookup"><span data-stu-id="84da2-103">.NET Core Federal Information Processing Standard (FIPS) compliance</span></span>

<span data-ttu-id="84da2-104">Die Federal Information Processing Standard ()-Veröffentlichung 140-2 ist ein US-Regierungs Standard, der die minimalen Sicherheitsanforderungen für kryptografische Module in Informationstechnologie Produkten definiert, wie in Abschnitt 5131 der Informationen definiert. Technology Management-Reform Act von 1996.</span><span class="sxs-lookup"><span data-stu-id="84da2-104">The Federal Information Processing Standard (FIPS) Publication 140-2 is a U.S. government standard that defines minimum security requirements for cryptographic modules in information technology products, as defined in Section 5131 of the Information Technology Management Reform Act of 1996.</span></span>

<span data-ttu-id="84da2-105">.NET Core:</span><span class="sxs-lookup"><span data-stu-id="84da2-105">.NET Core:</span></span>

* <span data-ttu-id="84da2-106">Übergibt kryptografische primitive Aufrufe an die Standardmodule, die das zugrunde liegende Betriebssystem bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="84da2-106">Passes cryptographic primitives calls through to the standard modules the underlying operating system provides.</span></span>
* <span data-ttu-id="84da2-107">Erzwingt **nicht** die Verwendung von per PPS genehmigten Algorithmen oder Schlüsselgrößen in .net Core-apps.</span><span class="sxs-lookup"><span data-stu-id="84da2-107">Does **not** enforce the use of FIPS Approved algorithms or key sizes in .NET Core apps.</span></span>

<span data-ttu-id="84da2-108">Der Systemadministrator ist für die Konfiguration der Konformität mit der Konformität für ein Betriebssystem verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="84da2-108">The system administrator is responsible for configuring the FIPS compliance for an operating system.</span></span>

<span data-ttu-id="84da2-109">Wenn Code für eine mit PPS kompatible Umgebung geschrieben wird, ist der Entwickler dafür verantwortlich, sicherzustellen, dass nicht kompatible, nicht kompatible Filter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="84da2-109">If code is written for a FIPS-compliant environment, the developer is responsible for ensuring that non-compliant FIPS algorithms aren't used.</span></span>

<span data-ttu-id="84da2-110">Weitere Informationen zur Kompatibilität von Standards finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="84da2-110">For more information on FIPS compliance, see the following articles:</span></span>

* [<span data-ttu-id="84da2-111">Windows fi-Konformität</span><span class="sxs-lookup"><span data-stu-id="84da2-111">Windows FIPS Compliance</span></span>](/windows/security/threat-protection/fips-140-validation)
* [<span data-ttu-id="84da2-112">Konfigurieren von Windows für die Konformität mit dem PPS</span><span class="sxs-lookup"><span data-stu-id="84da2-112">Configuring Windows for FIPS Compliance</span></span>](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [<span data-ttu-id="84da2-113">Kapitel 8. Bundes Standards und Bestimmungen Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="84da2-113">Chapter 8. Federal Standards and Regulations Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/security_guide/chap-federal_standards_and_regulations)
