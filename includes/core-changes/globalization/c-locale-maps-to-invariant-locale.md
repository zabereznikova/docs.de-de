---
ms.openlocfilehash: 9e9e443be9ea51d214e95c676fc28f0d8790af8b
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117258"
---
### <a name="c-locale-maps-to-the-invariant-locale"></a><span data-ttu-id="9d0b4-101">Gebietsschema „C“ wird dem invarianten Gebietsschema zugeordnet</span><span class="sxs-lookup"><span data-stu-id="9d0b4-101">"C" locale maps to the invariant locale</span></span>

<span data-ttu-id="9d0b4-102">.NET Core 2.2 und frühere Versionen hängen von dem ICU-Standardverhalten ab, das das Gebietsschema „C“ zum Gebietsschema „en_US_POSIX“ zuordnet.</span><span class="sxs-lookup"><span data-stu-id="9d0b4-102">.NET Core 2.2 and earlier versions depend on the default ICU behavior, which maps the "C" locale to the en_US_POSIX locale.</span></span> <span data-ttu-id="9d0b4-103">Das Gebietsschema „en_US_POSIX“ weist ein unerwünschtes Sortierverhalten auf, da es keine Zeichenfolgenvergleiche ohne Berücksichtigung der Groß-/Kleinschreibung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9d0b4-103">The en_US_POSIX locale has an undesirable collation behavior, because it doesn't support case-insensitive string comparisons.</span></span> <span data-ttu-id="9d0b4-104">Da einige Linux-Verteilungen das Gebietsschema „C“ als Standardgebietsschema festlegen, kam es bei einigen Benutzern zu unerwartetem Verhalten.</span><span class="sxs-lookup"><span data-stu-id="9d0b4-104">Because some Linux distributions set the "C" locale as the default locale, users were experiencing unexpected behavior.</span></span> 

#### <a name="details"></a><span data-ttu-id="9d0b4-105">Details</span><span class="sxs-lookup"><span data-stu-id="9d0b4-105">Details</span></span>

<span data-ttu-id="9d0b4-106">Die Zuordnung des Gebietsschemas „C“ wurde ab .NET Core 3.0 geändert, sodass das invariante Gebietsschema anstelle von „en_US_POSIX“ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9d0b4-106">Starting with .NET Core 3.0, the "C" locale mapping has changed to use the Invariant locale instead of en_US_POSIX.</span></span> <span data-ttu-id="9d0b4-107">Die Zuordnung des Gebietsschemas „C“ zum invarianten Gebietsschema wird zur Gewährleistung der Konsistenz auch auf Windows angewendet.</span><span class="sxs-lookup"><span data-stu-id="9d0b4-107">The "C" locale to Invariant mapping is also applied to Windows for consistency.</span></span>

<span data-ttu-id="9d0b4-108">Die Zuordnung von „C“ zu „en_US_POSIX“ sorgte bei Kunden für Verwirrung, da „en_US_POSIX“ keine Sortier- und Suchvorgänge für Zeichenfolgen ohne Beachtung der Groß-/Kleinschreibung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9d0b4-108">Mapping "C" to en_US_POSIX culture caused customer confusion, because en_US_POSIX doesn't support case insensitive sorting/searching string operations.</span></span> <span data-ttu-id="9d0b4-109">Da das Gebietsschema „C“ in einigen Linux-Verteilungen als Standardgebietsschema verwendet wird, trat dieses unerwünschte Verhalten bei Kunden mit diesen Betriebssystemen auf.</span><span class="sxs-lookup"><span data-stu-id="9d0b4-109">Because the "C" locale is used as a default locale in some of the Linux distros, customers experienced this undesired behavior on these operating systems.</span></span> 

#### <a name="version-introduced"></a><span data-ttu-id="9d0b4-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9d0b4-110">Version introduced</span></span>

<span data-ttu-id="9d0b4-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9d0b4-111">.NET Core 3.0</span></span>

### <a name="recommended-action"></a><span data-ttu-id="9d0b4-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="9d0b4-112">Recommended action</span></span>

<span data-ttu-id="9d0b4-113">Es ist keine spezifische Maßnahme erforderlich. Sie sollten lediglich über die Änderung informiert sein.</span><span class="sxs-lookup"><span data-stu-id="9d0b4-113">Nothing specific more than the awareness of this change.</span></span> <span data-ttu-id="9d0b4-114">Diese Änderung wirkt sich nur auf Anwendungen aus, die die Zuordnung des Gebietsschemas „C“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d0b4-114">This change affects only applications that use the "C" locale mapping.</span></span>

### <a name="category"></a><span data-ttu-id="9d0b4-115">Category (Kategorie)</span><span class="sxs-lookup"><span data-stu-id="9d0b4-115">Category</span></span>

<span data-ttu-id="9d0b4-116">Globalisierung</span><span class="sxs-lookup"><span data-stu-id="9d0b4-116">Globalization</span></span> 

### <a name="affected-apis"></a><span data-ttu-id="9d0b4-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="9d0b4-117">Affected APIs</span></span>

<span data-ttu-id="9d0b4-118">Diese Änderung wirkt sich auf alle Sortierungs- und Kultur-APIs aus.</span><span class="sxs-lookup"><span data-stu-id="9d0b4-118">All collation and culture APIs are affected by this change.</span></span>

<!--

-->
