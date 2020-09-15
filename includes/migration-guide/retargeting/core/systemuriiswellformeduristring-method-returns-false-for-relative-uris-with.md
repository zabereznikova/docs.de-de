---
ms.openlocfilehash: f7dcf9c4c3dc7ea536ddc847769a1a30f1298bb2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617215"
---
### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a><span data-ttu-id="24d80-101">Die Methode System.Uri.IsWellFormedUriString gibt für relative URIs mit einem Doppelpunktzeichen im ersten Segment FALSE zurück</span><span class="sxs-lookup"><span data-stu-id="24d80-101">System.Uri.IsWellFormedUriString method returns false for relative URIs with a colon char in first segment</span></span>

#### <a name="details"></a><span data-ttu-id="24d80-102">Details</span><span class="sxs-lookup"><span data-stu-id="24d80-102">Details</span></span>

<span data-ttu-id="24d80-103">Ab .NET Framework 4.5 zeigt <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> für relative URIs mit einem `:` im ersten Segment an, dass es sich nicht um einen wohlgeformten relativen URI handelt.</span><span class="sxs-lookup"><span data-stu-id="24d80-103">Beginning with the .NET Framework 4.5, <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> will treat relative URIs with a `:` in their first segment as not well formed.</span></span> <span data-ttu-id="24d80-104">Dies ist eine Änderung des <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName>-Verhaltens in .NET Framework 4.0, die vorgenommen wurde, um eine Übereinstimmung mit RFC3986 sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="24d80-104">This is a change from <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> behavior in the .NET Framework 4.0 that was made to conform to RFC3986.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="24d80-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="24d80-105">Suggestion</span></span>

<span data-ttu-id="24d80-106">Diese Änderung wirkt sich (wie viele andere URI-Änderungen auch) nur auf Anwendungen aus, die auf .NET Framework 4.5 (oder höher) ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="24d80-106">This change (like many other URI changes) will only affect applications targeting the .NET Framework 4.5 (or later).</span></span> <span data-ttu-id="24d80-107">Damit Sie weiterhin das alte Verhalten verwenden können, müssen Sie als Zielplattform für die App NET Framework 4.0 verwenden.</span><span class="sxs-lookup"><span data-stu-id="24d80-107">To keep using the old behavior, target the app against the .NET Framework 4.0.</span></span> <span data-ttu-id="24d80-108">Überprüfen Sie alternativ die URIs, bevor Sie <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> aufrufen, und suchen Sie nach `:`-Zeichen, die Sie für die Überprüfung entfernen sollten, wenn das alte Verhalten bevorzugt wird.</span><span class="sxs-lookup"><span data-stu-id="24d80-108">Alternatively, scan URI's prior to calling <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> looking for `:` characters that you may want to remove for validation purposes, if the old behavior is desirable.</span></span>

| <span data-ttu-id="24d80-109">name</span><span class="sxs-lookup"><span data-stu-id="24d80-109">Name</span></span>    | <span data-ttu-id="24d80-110">Wert</span><span class="sxs-lookup"><span data-stu-id="24d80-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="24d80-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="24d80-111">Scope</span></span>   | <span data-ttu-id="24d80-112">Gering</span><span class="sxs-lookup"><span data-stu-id="24d80-112">Minor</span></span>       |
| <span data-ttu-id="24d80-113">Version</span><span class="sxs-lookup"><span data-stu-id="24d80-113">Version</span></span> | <span data-ttu-id="24d80-114">4.5</span><span class="sxs-lookup"><span data-stu-id="24d80-114">4.5</span></span>         |
| <span data-ttu-id="24d80-115">Typ</span><span class="sxs-lookup"><span data-stu-id="24d80-115">Type</span></span>    | <span data-ttu-id="24d80-116">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="24d80-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="24d80-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="24d80-117">Affected APIs</span></span>

- <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType>
