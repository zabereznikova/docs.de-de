---
ms.openlocfilehash: abef47c64a7cfd99c5b50bf2100401a2d5fcc5c3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614495"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a><span data-ttu-id="3157f-101">X509CertificateClaimSet.FindClaims berücksichtigt alle claimTypes (Anspruchstypen)</span><span class="sxs-lookup"><span data-stu-id="3157f-101">X509CertificateClaimSet.FindClaims Considers All claimTypes</span></span>

#### <a name="details"></a><span data-ttu-id="3157f-102">Details</span><span class="sxs-lookup"><span data-stu-id="3157f-102">Details</span></span>

<span data-ttu-id="3157f-103">Wenn in Apps, die auf .NET Framework 4.6.1 ausgerichtet sind, ein X509-Anspruchssatz über ein Zertifikat mit mehreren DNS-Einträge im SAN-Feld initialisiert wird, versucht die <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName>-Methode, das claimType-Argument mit allen DNS-Einträgen abzugleichen. Bei Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, versucht die Methode <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName>, das claimType-Argument nur mit dem neuesten DNS-Eintrag abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="3157f-103">In apps that target the .NET Framework 4.6.1, if an X509 claim set is initialized from a certificate that has multiple DNS entries in its SAN field, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> method attempts to match the claimType argument with all the DNS entries.For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> method attempts to match the claimType argument only with the last DNS entry.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3157f-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="3157f-104">Suggestion</span></span>

<span data-ttu-id="3157f-105">Diese Änderung wirkt sich nur auf Anwendungen aus, die auf .NET Framework 4.6.1 ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="3157f-105">This change only affects applications targeting the .NET Framework 4.6.1.</span></span> <span data-ttu-id="3157f-106">Diese Änderung kann mit dem [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation)-Kompatibilitätsschalter deaktiviert werden (oder bei Versionen vor 4.6.1 aktiviert werden).</span><span class="sxs-lookup"><span data-stu-id="3157f-106">This change may be disabled (or enabled if targeting pre-4.6.1) with the [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation) compatibility switch.</span></span>

| <span data-ttu-id="3157f-107">name</span><span class="sxs-lookup"><span data-stu-id="3157f-107">Name</span></span>    | <span data-ttu-id="3157f-108">Wert</span><span class="sxs-lookup"><span data-stu-id="3157f-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3157f-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="3157f-109">Scope</span></span>   | <span data-ttu-id="3157f-110">Gering</span><span class="sxs-lookup"><span data-stu-id="3157f-110">Minor</span></span>       |
| <span data-ttu-id="3157f-111">Version</span><span class="sxs-lookup"><span data-stu-id="3157f-111">Version</span></span> | <span data-ttu-id="3157f-112">4.6.1</span><span class="sxs-lookup"><span data-stu-id="3157f-112">4.6.1</span></span>       |
| <span data-ttu-id="3157f-113">Typ</span><span class="sxs-lookup"><span data-stu-id="3157f-113">Type</span></span>    | <span data-ttu-id="3157f-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="3157f-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="3157f-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3157f-115">Affected APIs</span></span>

- <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType>
