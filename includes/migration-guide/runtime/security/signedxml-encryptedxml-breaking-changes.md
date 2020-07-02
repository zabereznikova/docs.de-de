---
ms.openlocfilehash: 8cc4f2ba2923774ef4e4e6861a89a7797ca988e1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621198"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a><span data-ttu-id="069dc-101">Breaking Changes bei SignedXml und EncryptedXml</span><span class="sxs-lookup"><span data-stu-id="069dc-101">SignedXml and EncryptedXml Breaking Changes</span></span>

#### <a name="details"></a><span data-ttu-id="069dc-102">Details</span><span class="sxs-lookup"><span data-stu-id="069dc-102">Details</span></span>

<span data-ttu-id="069dc-103">In .NET Framework 4.6.2 führen geschlossene Sicherheitslücken in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> und <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> zu Änderungen des Laufzeitverhaltens.</span><span class="sxs-lookup"><span data-stu-id="069dc-103">In .NET Framework 4.6.2, Security fixes in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> and <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> lead to different run-time behaviors.</span></span> <span data-ttu-id="069dc-104">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="069dc-104">For example,</span></span><ul><li><span data-ttu-id="069dc-105">Wenn ein Dokument mehrere Elemente mit demselben <code>id</code>-Attribut enthält und eine Signatur auf eins dieser Elemente als Signaturstamm ausgerichtet ist, wird das Dokument als gültig markiert.</span><span class="sxs-lookup"><span data-stu-id="069dc-105">If a document has multiple elements with the same <code>id</code> attribute and a signature targets one of those elements as the root of the signature, the document will now be considered invalid.</span></span></li><li><span data-ttu-id="069dc-106">Dokumente, die nicht kanonische Transformationsalgorithmen für XPath in Verweisen verwenden, gelten jetzt als gültig.</span><span class="sxs-lookup"><span data-stu-id="069dc-106">Documents using non-canonical XPath transform algorithms in references are now considered invalid.</span></span></li><li><span data-ttu-id="069dc-107">Dokumente, die nicht kanonische Transformationsalgorithmen für XSLT in Verweisen verwenden, gelten jetzt als ungültig.</span><span class="sxs-lookup"><span data-stu-id="069dc-107">Documents using non-canonical XSLT transform algorithms in references are now consider invalid.</span></span></li><li><span data-ttu-id="069dc-108">Programme können keine externen von Ressourcen getrennte Signaturen verwenden.</span><span class="sxs-lookup"><span data-stu-id="069dc-108">Any program making use of external resource detached signatures will be unable to do so.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="069dc-109">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="069dc-109">Suggestion</span></span>

<span data-ttu-id="069dc-110">Entwickler sollten die Verwendung von <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> und <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> sowie von von <xref:System.Security.Cryptography.Xml.Transform> abgeleiteten Typen prüfen, da ein Dokumentempfänger sie möglicherweise nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="069dc-110">Developers might want to review the usage of <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> and <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, as well as types derived from <xref:System.Security.Cryptography.Xml.Transform> since a document receiver may not be able to process it.</span></span>

| <span data-ttu-id="069dc-111">Name</span><span class="sxs-lookup"><span data-stu-id="069dc-111">Name</span></span>    | <span data-ttu-id="069dc-112">Wert</span><span class="sxs-lookup"><span data-stu-id="069dc-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="069dc-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="069dc-113">Scope</span></span>   |<span data-ttu-id="069dc-114">Gering</span><span class="sxs-lookup"><span data-stu-id="069dc-114">Minor</span></span>|
|<span data-ttu-id="069dc-115">Version</span><span class="sxs-lookup"><span data-stu-id="069dc-115">Version</span></span>|<span data-ttu-id="069dc-116">4.6.2</span><span class="sxs-lookup"><span data-stu-id="069dc-116">4.6.2</span></span>|
|<span data-ttu-id="069dc-117">Typ</span><span class="sxs-lookup"><span data-stu-id="069dc-117">Type</span></span>|<span data-ttu-id="069dc-118">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="069dc-118">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="069dc-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="069dc-119">Affected APIs</span></span>

-<xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType></li></ul>|
