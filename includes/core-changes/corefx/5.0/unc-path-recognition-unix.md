---
ms.openlocfilehash: 0246f325a6274082b7fb0d5590cec7c80687ae85
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720190"
---
### <a name="uri-recognition-of-unc-paths-on-unix"></a><span data-ttu-id="26dc6-101">URI-Erkennung von UNC-Pfaden unter UNIX</span><span class="sxs-lookup"><span data-stu-id="26dc6-101">Uri recognition of UNC paths on Unix</span></span>

<span data-ttu-id="26dc6-102">Die <xref:System.Uri>-Klasse erkennt jetzt unter UNIX-Betriebssystemen Zeichenfolgen, die mit zwei Schrägstrichen (`//`) beginnen, als UNC-Pfade (Universal Naming Convention).</span><span class="sxs-lookup"><span data-stu-id="26dc6-102">The <xref:System.Uri> class now recognizes strings that start with two forward slashes (`//`) as universal naming convention (UNC) paths on Unix operating systems.</span></span> <span data-ttu-id="26dc6-103">Diese Änderung hat zur Folge, dass das Verhalten für solche Zeichenfolgen auf allen Plattformen konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="26dc6-103">This change makes the behavior for such strings consistent across all platforms.</span></span>

#### <a name="change-description"></a><span data-ttu-id="26dc6-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="26dc6-104">Change description</span></span>

<span data-ttu-id="26dc6-105">In früheren .NET-Versionen erkennt die <xref:System.Uri>-Klasse unter UNIX-Betriebssystemen Zeichenfolgen, die mit zwei Schrägstrichen beginnen (z. B. `//contoso`), als absolute Dateipfade.</span><span class="sxs-lookup"><span data-stu-id="26dc6-105">In previous versions of .NET, the <xref:System.Uri> class recognizes strings that start with with two forward slashes, for example, `//contoso`, as absolute file paths on Unix operating systems.</span></span> <span data-ttu-id="26dc6-106">Unter Windows werden solche Zeichenfolgen jedoch als UNC-Pfade erkannt.</span><span class="sxs-lookup"><span data-stu-id="26dc6-106">However, on Windows, such strings are recognized as UNC paths.</span></span>

<span data-ttu-id="26dc6-107">Ab .NET 5.0 erkennt die <xref:System.Uri>-Klasse Zeichenfolgen, die mit zwei Schrägstrichen beginnen, auf allen Plattformen einschließlich UNIX als UNC-Pfade.</span><span class="sxs-lookup"><span data-stu-id="26dc6-107">Starting in .NET 5.0,  the <xref:System.Uri> class recognizes strings that start with with two forward slashes as UNC paths on all platforms, including Unix.</span></span> <span data-ttu-id="26dc6-108">Außerdem verhalten sich Eigenschaften entsprechend der UNC-Semantik:</span><span class="sxs-lookup"><span data-stu-id="26dc6-108">In addition, properties behave according to UNC semantics:</span></span>

- <span data-ttu-id="26dc6-109"><xref:System.Uri.IsUnc?displayProperty=nameWithType> gibt `true` zurück.</span><span class="sxs-lookup"><span data-stu-id="26dc6-109"><xref:System.Uri.IsUnc?displayProperty=nameWithType> returns `true`.</span></span>
- <span data-ttu-id="26dc6-110">Umgekehrte Schrägstriche im Pfad werden durch Schrägstriche ersetzt.</span><span class="sxs-lookup"><span data-stu-id="26dc6-110">Backslashes in the path are replaced with forward slashes.</span></span> <span data-ttu-id="26dc6-111">`//first\second` wird beispielsweise zu `//first/second`.</span><span class="sxs-lookup"><span data-stu-id="26dc6-111">For example, `//first\second` becomes `//first/second`.</span></span>
- <span data-ttu-id="26dc6-112">Bei <xref:System.Uri.LocalPath?displayProperty=nameWithType> werden keine Prozentzeichen in Zeichenfolgen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="26dc6-112"><xref:System.Uri.LocalPath?displayProperty=nameWithType> doesn't percent-encode characters.</span></span> <span data-ttu-id="26dc6-113">`//first/\uFFF0` wird beispielsweise *nicht* in `//first/%EF%BF%B0` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="26dc6-113">For example, `//first/\uFFF0` is *not* converted to `//first/%EF%BF%B0`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="26dc6-114">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="26dc6-114">Version introduced</span></span>

<span data-ttu-id="26dc6-115">5.0</span><span class="sxs-lookup"><span data-stu-id="26dc6-115">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="26dc6-116">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="26dc6-116">Recommended action</span></span>

<span data-ttu-id="26dc6-117">Auf der Seite des Entwicklers ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="26dc6-117">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="26dc6-118">Kategorie</span><span class="sxs-lookup"><span data-stu-id="26dc6-118">Category</span></span>

<span data-ttu-id="26dc6-119">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="26dc6-119">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="26dc6-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="26dc6-120">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
