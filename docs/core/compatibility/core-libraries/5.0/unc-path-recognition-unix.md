---
title: 'Breaking Change: URI-Erkennung von UNC-Pfaden unter UNIX'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den die Uri-Klasse jetzt Zeichenfolgen, die mit zwei Schrägstrichen beginnen, unter UNIX als UNC-Pfade erkennt.
ms.date: 11/01/2020
ms.openlocfilehash: 0d5d9cd8dd869f24e94d15724e5e16eaddf6ed47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759221"
---
# <a name="uri-recognition-of-unc-paths-on-unix"></a><span data-ttu-id="774e9-103">URI-Erkennung von UNC-Pfaden unter UNIX</span><span class="sxs-lookup"><span data-stu-id="774e9-103">Uri recognition of UNC paths on Unix</span></span>

<span data-ttu-id="774e9-104">Die <xref:System.Uri>-Klasse erkennt jetzt unter UNIX-Betriebssystemen Zeichenfolgen, die mit zwei Schrägstrichen (`//`) beginnen, als UNC-Pfade (Universal Naming Convention).</span><span class="sxs-lookup"><span data-stu-id="774e9-104">The <xref:System.Uri> class now recognizes strings that start with two forward slashes (`//`) as universal naming convention (UNC) paths on Unix operating systems.</span></span> <span data-ttu-id="774e9-105">Diese Änderung hat zur Folge, dass das Verhalten für solche Zeichenfolgen auf allen Plattformen konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="774e9-105">This change makes the behavior for such strings consistent across all platforms.</span></span>

## <a name="change-description"></a><span data-ttu-id="774e9-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="774e9-106">Change description</span></span>

<span data-ttu-id="774e9-107">In früheren .NET-Versionen erkennt die <xref:System.Uri>-Klasse unter UNIX-Betriebssystemen Zeichenfolgen, die mit zwei Schrägstrichen beginnen (z. B. `//contoso`), als absolute Dateipfade.</span><span class="sxs-lookup"><span data-stu-id="774e9-107">In previous versions of .NET, the <xref:System.Uri> class recognizes strings that start with two forward slashes, for example, `//contoso`, as absolute file paths on Unix operating systems.</span></span> <span data-ttu-id="774e9-108">Unter Windows werden solche Zeichenfolgen jedoch als UNC-Pfade erkannt.</span><span class="sxs-lookup"><span data-stu-id="774e9-108">However, on Windows, such strings are recognized as UNC paths.</span></span>

<span data-ttu-id="774e9-109">Ab .NET 5.0 erkennt die <xref:System.Uri>-Klasse Zeichenfolgen, die mit zwei Schrägstrichen beginnen, auf allen Plattformen einschließlich UNIX als UNC-Pfade.</span><span class="sxs-lookup"><span data-stu-id="774e9-109">Starting in .NET 5.0,  the <xref:System.Uri> class recognizes strings that start with two forward slashes as UNC paths on all platforms, including Unix.</span></span> <span data-ttu-id="774e9-110">Außerdem verhalten sich Eigenschaften entsprechend der UNC-Semantik:</span><span class="sxs-lookup"><span data-stu-id="774e9-110">In addition, properties behave according to UNC semantics:</span></span>

- <span data-ttu-id="774e9-111"><xref:System.Uri.IsUnc?displayProperty=nameWithType> gibt `true` zurück.</span><span class="sxs-lookup"><span data-stu-id="774e9-111"><xref:System.Uri.IsUnc?displayProperty=nameWithType> returns `true`.</span></span>
- <span data-ttu-id="774e9-112">Umgekehrte Schrägstriche im Pfad werden durch Schrägstriche ersetzt.</span><span class="sxs-lookup"><span data-stu-id="774e9-112">Backslashes in the path are replaced with forward slashes.</span></span> <span data-ttu-id="774e9-113">`//first\second` wird beispielsweise zu `//first/second`.</span><span class="sxs-lookup"><span data-stu-id="774e9-113">For example, `//first\second` becomes `//first/second`.</span></span>
- <span data-ttu-id="774e9-114">Bei <xref:System.Uri.LocalPath?displayProperty=nameWithType> werden keine Prozentzeichen in Zeichenfolgen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="774e9-114"><xref:System.Uri.LocalPath?displayProperty=nameWithType> doesn't percent-encode characters.</span></span> <span data-ttu-id="774e9-115">`//first/\uFFF0` wird beispielsweise *nicht* in `//first/%EF%BF%B0` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="774e9-115">For example, `//first/\uFFF0` is *not* converted to `//first/%EF%BF%B0`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="774e9-116">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="774e9-116">Version introduced</span></span>

<span data-ttu-id="774e9-117">5.0</span><span class="sxs-lookup"><span data-stu-id="774e9-117">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="774e9-118">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="774e9-118">Recommended action</span></span>

<span data-ttu-id="774e9-119">Auf der Seite des Entwicklers ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="774e9-119">No action is required on the part of the developer.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="774e9-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="774e9-120">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
