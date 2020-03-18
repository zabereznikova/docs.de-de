---
ms.openlocfilehash: 9520f8c6b6671917f5694bc602293a00e2dab82d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568115"
---
### <a name="ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes"></a><span data-ttu-id="b6407-101">ZipArchiveEntry verarbeitet keine Archive mit inkonsistenten Eintragsgrößen mehr</span><span class="sxs-lookup"><span data-stu-id="b6407-101">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>

<span data-ttu-id="b6407-102">ZIP-Archive listen sowohl die komprimierte als auch die unkomprimierte Größe im zentralen Verzeichnis und im lokalen Header auf.</span><span class="sxs-lookup"><span data-stu-id="b6407-102">Zip archives list both compressed size and uncompressed size in the central directory and local header.</span></span>  <span data-ttu-id="b6407-103">Die Eintragsdaten selbst geben die Größe ebenfalls an.</span><span class="sxs-lookup"><span data-stu-id="b6407-103">The entry data itself also indicates its size.</span></span>  <span data-ttu-id="b6407-104">In .NET Core 2.2 und früheren Versionen wurden diese Werte nie auf Konsistenz geprüft.</span><span class="sxs-lookup"><span data-stu-id="b6407-104">In .NET Core 2.2 and earlier versions, these values were never checked for consistency.</span></span> <span data-ttu-id="b6407-105">Ab .NET Core 3.0 ist dies jetzt der Fall.</span><span class="sxs-lookup"><span data-stu-id="b6407-105">Starting with .NET Core 3.0, they now are.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b6407-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="b6407-106">Change description</span></span>

<span data-ttu-id="b6407-107">In .NET Core 2.2 und früheren Versionen ist <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> selbst dann erfolgreich, wenn der lokale Header nicht mit dem zentralen Header der ZIP-Datei übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b6407-107">In .NET Core 2.2 and earlier versions, <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> succeeds even if the local header disagrees with the central header of the zip file.</span></span> <span data-ttu-id="b6407-108">Die Daten werden dekomprimiert, bis das Ende des komprimierten Datenstroms erreicht ist, auch wenn seine Länge die im zentralen Verzeichnis/lokalen Header angegebene unkomprimierte Dateigröße überschreitet.</span><span class="sxs-lookup"><span data-stu-id="b6407-108">Data is decompressed until the end of the compressed stream is reached, even if its length exceeds the uncompressed file size listed in the central directory/local header.</span></span>

<span data-ttu-id="b6407-109">Ab .NET Core 3.0 überprüft die <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType>-Methode, ob der lokale Header und der zentrale Header hinsichtlich der komprimierten und unkomprimierten Größen eines Eintrags übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b6407-109">Starting with .NET Core 3.0, the <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> method checks that local header and central header agree on compressed and uncompressed sizes of an entry.</span></span>  <span data-ttu-id="b6407-110">Wenn dies nicht der Fall ist, löst die Methode eine <xref:System.IO.InvalidDataException> aus, wenn die lokalen Größen der Header- und/oder Datendeskriptorlisten des Archivs nicht mit dem zentralen Verzeichnis der ZIP-Datei übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b6407-110">If they do not, the method throws an <xref:System.IO.InvalidDataException> if the archive's local header and/or data descriptor list sizes that disagree with the central directory of the zip file.</span></span> <span data-ttu-id="b6407-111">Beim Lesen eines Eintrags werden dekomprimierte Daten auf die nicht komprimierte Dateigröße abgeschnitten, die im Header aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="b6407-111">When reading an entry, decompressed data is truncated to the uncompressed file size listed in the header.</span></span>

<span data-ttu-id="b6407-112">Diese Änderung wurde vorgenommen, um sicherzustellen, dass ein <xref:System.IO.Compression.ZipArchiveEntry> die Größe seiner Daten richtig darstellt und nur diese Menge an Daten gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="b6407-112">This change was made to ensure that a <xref:System.IO.Compression.ZipArchiveEntry> correctly represents the size of its data and that only that amount of data is read.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b6407-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="b6407-113">Version introduced</span></span>

<span data-ttu-id="b6407-114">3.0</span><span class="sxs-lookup"><span data-stu-id="b6407-114">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b6407-115">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="b6407-115">Recommended action</span></span>

<span data-ttu-id="b6407-116">Packen Sie jedes ZIP-Archiv neu, das diese Probleme aufweist.</span><span class="sxs-lookup"><span data-stu-id="b6407-116">Repackage any zip archive that exhibits these problems.</span></span>

#### <a name="category"></a><span data-ttu-id="b6407-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="b6407-117">Category</span></span>

<span data-ttu-id="b6407-118">CoreFx</span><span class="sxs-lookup"><span data-stu-id="b6407-118">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b6407-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b6407-119">Affected APIs</span></span>

- <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.ExtractToDirectory%2A?displayProperty=nameWithType>

<!--

### Affected APIs

`M:System.IO.Compression.ZipArchiveEntry.Open`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A`
`Overload:System.IO.Compression.ZipFile.ExtractToDirectory%2A`

-->
