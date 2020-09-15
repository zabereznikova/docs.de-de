---
ms.openlocfilehash: 9c3c0bf7fbd8d45eba84eaa8634fd2d834195702
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617205"
---
### <a name="systemuri-parsing-adheres-to-rfc-3987"></a><span data-ttu-id="d210e-101">Die System.Uri-Analyse entspricht den Vorgaben in RFC 3987</span><span class="sxs-lookup"><span data-stu-id="d210e-101">System.Uri parsing adheres to RFC 3987</span></span>

#### <a name="details"></a><span data-ttu-id="d210e-102">Details</span><span class="sxs-lookup"><span data-stu-id="d210e-102">Details</span></span>

<span data-ttu-id="d210e-103">Die URI-Analyse hat sich seit .NET Framework 4.5 auf verschiedene Weisen geändert.</span><span class="sxs-lookup"><span data-stu-id="d210e-103">URI parsing has changed in several ways in .NET Framework 4.5.</span></span> <span data-ttu-id="d210e-104">Beachten Sie jedoch, dass sich diese Änderungen nur auf Code auswirken, der auf .NET Framework 4.5 ausgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d210e-104">Note, however, that these changes only affect code targeting .NET Framework 4.5.</span></span> <span data-ttu-id="d210e-105">Wenn eine Binärdatei auf .NET Framework 4.0 ausgelegt ist, wird das alte Verhalten beachtet.</span><span class="sxs-lookup"><span data-stu-id="d210e-105">If a binary targets .NET Framework 4.0, the old behavior will be observed.</span></span> <span data-ttu-id="d210e-106">Änderungen an der URI-Analyse in .NET Framework 4.5 umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d210e-106">Changes to URI parsing in .NET Framework 4.5 include:</span></span>

- <span data-ttu-id="d210e-107">Die URI-Analyse führt die Normalisierung und Zeichenüberprüfung gemäß den neuesten IRI-Regeln in RFC 3987 aus.</span><span class="sxs-lookup"><span data-stu-id="d210e-107">URI parsing will perform normalization and character checking according to the latest IRI rules in RFC 3987.</span></span>
- <span data-ttu-id="d210e-108">Die Unicode-Normalisierungsform C wird nur für den Hostteil des URIs ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d210e-108">Unicode normalization form C will only be performed on the host portion of the URI.</span></span>
- <span data-ttu-id="d210e-109">Ungültige Angabe für „Mailto“: URIs lösen nun eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="d210e-109">Invalid mailto: URIs will now cause an exception.</span></span>
- <span data-ttu-id="d210e-110">Nachgestellte Punkte am Ende eines Pfadsegments bleiben nun erhalten.</span><span class="sxs-lookup"><span data-stu-id="d210e-110">Trailing dots at the end of a path segment are now preserved.</span></span>
- <span data-ttu-id="d210e-111">`file://`-URIs versehen das `?`-Zeichen nicht mit einem Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="d210e-111">`file://` URIs do not escape the `?` character.</span></span>
- <span data-ttu-id="d210e-112">Die Unicode-Steuerzeichen `U+0080` bis `U+009F` werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d210e-112">Unicode control characters `U+0080` through `U+009F` are not supported.</span></span>
- <span data-ttu-id="d210e-113">Für die Kommazeichen `,` und `%2c` wird das Escapezeichen nicht automatisch entfernt.</span><span class="sxs-lookup"><span data-stu-id="d210e-113">Comma characters `,` or `%2c` are not automatically unescaped.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d210e-114">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d210e-114">Suggestion</span></span>

<span data-ttu-id="d210e-115">Wenn die alte Semantik der .NET Framework 4.0-URI-Analyse erforderlich ist (was nicht häufig der Fall ist), kann sie durch Ausrichtung auf .NET Framework 4.0 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d210e-115">If the old .NET Framework 4.0 URI parsing semantics are necessary (they often aren't), they can be used by targeting .NET Framework 4.0.</span></span> <span data-ttu-id="d210e-116">Dies kann mithilfe von <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> für die Assembly oder auf der Seite „Projekteigenschaften“ über die Benutzeroberfläche des Projektsystems von Visual Studio erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="d210e-116">This can be accomplished by using a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> on the assembly, or through Visual Studio's project system UI in the 'project properties' page.</span></span>

| <span data-ttu-id="d210e-117">name</span><span class="sxs-lookup"><span data-stu-id="d210e-117">Name</span></span>    | <span data-ttu-id="d210e-118">Wert</span><span class="sxs-lookup"><span data-stu-id="d210e-118">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d210e-119">Bereich</span><span class="sxs-lookup"><span data-stu-id="d210e-119">Scope</span></span>   | <span data-ttu-id="d210e-120">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="d210e-120">Major</span></span>       |
| <span data-ttu-id="d210e-121">Version</span><span class="sxs-lookup"><span data-stu-id="d210e-121">Version</span></span> | <span data-ttu-id="d210e-122">4.5</span><span class="sxs-lookup"><span data-stu-id="d210e-122">4.5</span></span>         |
| <span data-ttu-id="d210e-123">Typ</span><span class="sxs-lookup"><span data-stu-id="d210e-123">Type</span></span>    | <span data-ttu-id="d210e-124">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="d210e-124">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d210e-125">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d210e-125">Affected APIs</span></span>

- <xref:System.Uri.%23ctor(System.String)>
- <xref:System.Uri.%23ctor(System.String,System.Boolean)>
- <xref:System.Uri.%23ctor(System.String,System.UriKind)>
- <xref:System.Uri.%23ctor(System.Uri,System.String)>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
