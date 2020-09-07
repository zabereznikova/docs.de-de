---
ms.openlocfilehash: e7001fcfdf88fd9e710fbb702f2ed39d63b1e080
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497858"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a><span data-ttu-id="c43d3-101">RFC 3986 kann jetzt verwendet werden, um System.Uri mit Escapezeichen zu versehen</span><span class="sxs-lookup"><span data-stu-id="c43d3-101">System.Uri escaping now supports RFC 3986</span></span>

#### <a name="details"></a><span data-ttu-id="c43d3-102">Details</span><span class="sxs-lookup"><span data-stu-id="c43d3-102">Details</span></span>

<span data-ttu-id="c43d3-103">URI-Escapezeichen in .NET Framework 4.5 wurden geändert, um [RFC 3986](https://tools.ietf.org/html/rfc3986) zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c43d3-103">URI escaping has changed in .NET Framework 4.5 to support [RFC 3986](https://tools.ietf.org/html/rfc3986).</span></span> <span data-ttu-id="c43d3-104">Die speziellen Änderungen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c43d3-104">Specific changes include:</span></span><ul><li><span data-ttu-id="c43d3-105"><xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> versieht reservierte Zeichen basierend auf RFC 3986 mit Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="c43d3-105"><xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> escapes reserved characters based on RFC 3986.</span></span></li><li><span data-ttu-id="c43d3-106"><xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> versieht reservierte Zeichen nicht mit Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="c43d3-106"><xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> does not escape reserved characters.</span></span></li><li><span data-ttu-id="c43d3-107"><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> löst keine Ausnahme aus, wenn eine ungültige Escapesequenz gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="c43d3-107"><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> does not throw an exception if it encounters an invalid escape sequence.</span></span></li><li><span data-ttu-id="c43d3-108">Bei nicht reservierten Zeichen mit Escapezeichen werden letztere entfernt.</span><span class="sxs-lookup"><span data-stu-id="c43d3-108">Unreserved escaped characters are un-escaped.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="c43d3-109">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c43d3-109">Suggestion</span></span>

<ul><li><span data-ttu-id="c43d3-110">Aktualisieren Sie die Anwendungen, um nicht auf <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> angewiesen zu sein, wenn Sie bei einer ungültigen Escapesequenz eine Ausnahme auslösen möchten.</span><span class="sxs-lookup"><span data-stu-id="c43d3-110">Update applications to not rely on <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> to throw in the case of an invalid escape sequence.</span></span> <span data-ttu-id="c43d3-111">Derartige Sequenzen müssen jetzt direkt erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="c43d3-111">Such sequences must be detected directly now.</span></span></li><li><span data-ttu-id="c43d3-112">Erwarten Sie zudem, dass URI- und Datenzeichenfolgen mit und ohne Escapezeichen zwischen .NET Framework 4.0 und .NET Framework 4.5 möglicherweise abweichen und für .NET-Versionen nicht direkt verglichen werden sollten.</span><span class="sxs-lookup"><span data-stu-id="c43d3-112">Similarly, expect that Escaped and Unescaped URI and Data strings may vary from .NET Framework 4.0 and .NET Framework 4.5 and should not be compared across .NET versions directly.</span></span> <span data-ttu-id="c43d3-113">Stattdessen sollten sie in einer einzelnen .NET-Version analysiert und normalisiert werden, bevor Vergleiche durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c43d3-113">Instead, they should be parsed and normalized in a single .NET version before any comparisons are made.</span></span></li></ul>

| <span data-ttu-id="c43d3-114">name</span><span class="sxs-lookup"><span data-stu-id="c43d3-114">Name</span></span>    | <span data-ttu-id="c43d3-115">Wert</span><span class="sxs-lookup"><span data-stu-id="c43d3-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c43d3-116">Bereich</span><span class="sxs-lookup"><span data-stu-id="c43d3-116">Scope</span></span>   |<span data-ttu-id="c43d3-117">Gering</span><span class="sxs-lookup"><span data-stu-id="c43d3-117">Minor</span></span>|
|<span data-ttu-id="c43d3-118">Version</span><span class="sxs-lookup"><span data-stu-id="c43d3-118">Version</span></span>|<span data-ttu-id="c43d3-119">4.5</span><span class="sxs-lookup"><span data-stu-id="c43d3-119">4.5</span></span>|
|<span data-ttu-id="c43d3-120">Typ</span><span class="sxs-lookup"><span data-stu-id="c43d3-120">Type</span></span>|<span data-ttu-id="c43d3-121">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c43d3-121">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c43d3-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c43d3-122">Affected APIs</span></span>

- <xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.EscapeDataString(System.String)`
- `M:System.Uri.EscapeUriString(System.String)`
- `M:System.Uri.UnescapeDataString(System.String)`

-->
