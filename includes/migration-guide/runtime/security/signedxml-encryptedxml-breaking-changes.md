---
ms.openlocfilehash: 5c8ea3565fbe599dd53a71ba8bd339704f7d7f8a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497352"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a><span data-ttu-id="995b6-101">Breaking Changes bei SignedXml und EncryptedXml</span><span class="sxs-lookup"><span data-stu-id="995b6-101">SignedXml and EncryptedXml Breaking Changes</span></span>

#### <a name="details"></a><span data-ttu-id="995b6-102">Details</span><span class="sxs-lookup"><span data-stu-id="995b6-102">Details</span></span>

<span data-ttu-id="995b6-103">In .NET Framework 4.6.2 führen geschlossene Sicherheitslücken in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> und <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> zu Änderungen des Laufzeitverhaltens.</span><span class="sxs-lookup"><span data-stu-id="995b6-103">In .NET Framework 4.6.2, Security fixes in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> and <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> lead to different run-time behaviors.</span></span> <span data-ttu-id="995b6-104">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="995b6-104">For example,</span></span><ul><li><span data-ttu-id="995b6-105">Wenn ein Dokument mehrere Elemente mit demselben <code>id</code>-Attribut enthält und eine Signatur auf eins dieser Elemente als Signaturstamm ausgerichtet ist, wird das Dokument als gültig markiert.</span><span class="sxs-lookup"><span data-stu-id="995b6-105">If a document has multiple elements with the same <code>id</code> attribute and a signature targets one of those elements as the root of the signature, the document will now be considered invalid.</span></span></li><li><span data-ttu-id="995b6-106">Dokumente, die nicht kanonische Transformationsalgorithmen für XPath in Verweisen verwenden, gelten jetzt als gültig.</span><span class="sxs-lookup"><span data-stu-id="995b6-106">Documents using non-canonical XPath transform algorithms in references are now considered invalid.</span></span></li><li><span data-ttu-id="995b6-107">Dokumente, die nicht kanonische Transformationsalgorithmen für XSLT in Verweisen verwenden, gelten jetzt als ungültig.</span><span class="sxs-lookup"><span data-stu-id="995b6-107">Documents using non-canonical XSLT transform algorithms in references are now consider invalid.</span></span></li><li><span data-ttu-id="995b6-108">Programme können keine externen von Ressourcen getrennte Signaturen verwenden.</span><span class="sxs-lookup"><span data-stu-id="995b6-108">Any program making use of external resource detached signatures will be unable to do so.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="995b6-109">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="995b6-109">Suggestion</span></span>

<span data-ttu-id="995b6-110">Entwickler sollten die Verwendung von <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> und <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> sowie von von <xref:System.Security.Cryptography.Xml.Transform> abgeleiteten Typen prüfen, da ein Dokumentempfänger sie möglicherweise nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="995b6-110">Developers might want to review the usage of <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> and <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, as well as types derived from <xref:System.Security.Cryptography.Xml.Transform> since a document receiver may not be able to process it.</span></span>

| <span data-ttu-id="995b6-111">Name</span><span class="sxs-lookup"><span data-stu-id="995b6-111">Name</span></span>    | <span data-ttu-id="995b6-112">Wert</span><span class="sxs-lookup"><span data-stu-id="995b6-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="995b6-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="995b6-113">Scope</span></span>   |<span data-ttu-id="995b6-114">Gering</span><span class="sxs-lookup"><span data-stu-id="995b6-114">Minor</span></span>|
|<span data-ttu-id="995b6-115">Version</span><span class="sxs-lookup"><span data-stu-id="995b6-115">Version</span></span>|<span data-ttu-id="995b6-116">4.6.2</span><span class="sxs-lookup"><span data-stu-id="995b6-116">4.6.2</span></span>|
|<span data-ttu-id="995b6-117">Typ</span><span class="sxs-lookup"><span data-stu-id="995b6-117">Type</span></span>|<span data-ttu-id="995b6-118">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="995b6-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="995b6-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="995b6-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.Xml.Transform`
- `T:System.Security.Cryptography.Xml.XmlDsigXPathTransform`
- `T:System.Security.Cryptography.Xml.XmlDsigXsltTransform`

-->
