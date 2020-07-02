---
ms.openlocfilehash: 7e42a294b151d07a6fdc61308cdf92df7a31a1d6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614487"
---
### <a name="deflatestream-uses-native-apis-for-decompression"></a><span data-ttu-id="5533a-101">DeflateStream verwendet native APIs für die Dekomprimierung</span><span class="sxs-lookup"><span data-stu-id="5533a-101">DeflateStream uses native APIs for decompression</span></span>

#### <a name="details"></a><span data-ttu-id="5533a-102">Details</span><span class="sxs-lookup"><span data-stu-id="5533a-102">Details</span></span>

<span data-ttu-id="5533a-103">Ab .NET Framework 4.7.2 hat sich die Implementierung der Dekomprimierung in der `T:System.IO.Compression.DeflateStream`-Klasse so geändert, dass standardmäßig native Windows-APIs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5533a-103">Starting with the .NET Framework 4.7.2, the implementation of decompression in the `T:System.IO.Compression.DeflateStream` class has changed to use native Windows APIs by default.</span></span> <span data-ttu-id="5533a-104">In der Regel führt dies zu einer beträchtlichen Leistungssteigerung.</span><span class="sxs-lookup"><span data-stu-id="5533a-104">Typically, this results in a substantial performance improvement.</span></span> <span data-ttu-id="5533a-105">Alle .NET-Anwendungen für .NET Framework Version 4.7.2 oder höher verwenden die native Implementierung. Diese Änderung kann zu einigen Unterschieden im Verhalten führen, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="5533a-105">All .NET applications targeting the .NET Framework version 4.7.2 or higher use the native implementation.This change might result in some differences in behavior, which include:</span></span>

- <span data-ttu-id="5533a-106">Die Ausnahmemeldungen können sich unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="5533a-106">Exception messages may be different.</span></span> <span data-ttu-id="5533a-107">Der Typ der ausgelösten Ausnahme bleibt jedoch gleich.</span><span class="sxs-lookup"><span data-stu-id="5533a-107">However, the type of exception thrown remains the same.</span></span>
- <span data-ttu-id="5533a-108">Einige besondere Situationen (z.B. nicht ausreichender Speicher zum Abschließen eines Vorgangs) werden möglicherweise anders behandelt.</span><span class="sxs-lookup"><span data-stu-id="5533a-108">Some special situations, such as not having enough memory to complete an operation, may be handled differently.</span></span>
- <span data-ttu-id="5533a-109">Es gibt bekannte Unterschiede für die Analyse von GZip-Headern (Hinweis: nur `GZipStream` für die Dekomprimierung ist davon betroffen):</span><span class="sxs-lookup"><span data-stu-id="5533a-109">There are known differences for parsing gzip header (note: only `GZipStream` set for decompression is affected):</span></span>
- <span data-ttu-id="5533a-110">Ausnahmen beim Analysieren ungültiger Header werden möglicherweise zu anderen Zeiten ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5533a-110">Exceptions when parsing invalid headers may be thrown at different times.</span></span>
- <span data-ttu-id="5533a-111">Die native Implementierung führt dazu, dass Werte für einige reservierte Flags im GZip-Header (d.h. [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) gemäß der Spezifikation festgelegt werden. Dies kann dazu führen, dass in Fällen möglicherweise eine Ausnahme ausgelöst wird, in denen zuvor ungültige Werte ignoriert wurden.</span><span class="sxs-lookup"><span data-stu-id="5533a-111">The native implementation enforces that values for some reserved flags inside the gzip header (i.e. [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) are set according to the specification, which may cause it to throw an exception where previously invalid values were ignored.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5533a-112">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="5533a-112">Suggestion</span></span>

<span data-ttu-id="5533a-113">Wenn sich die Dekomprimierung mit nativen APIs negativ auf das Verhalten Ihrer App ausgewirkt hat, können Sie diese Funktion durch Hinzufügen des `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression`-Schalters zum Abschnitt `runtime` der Datei „app.config“ und Festlegen des Werts auf `true` deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="5533a-113">If decompression with native APIs has adversely affected the behavior of your app, you can opt out of this feature by adding the `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression` switch to the `runtime` section of your app.config file and setting it to `true`:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="5533a-114">name</span><span class="sxs-lookup"><span data-stu-id="5533a-114">Name</span></span>    | <span data-ttu-id="5533a-115">Wert</span><span class="sxs-lookup"><span data-stu-id="5533a-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5533a-116">Bereich</span><span class="sxs-lookup"><span data-stu-id="5533a-116">Scope</span></span>   | <span data-ttu-id="5533a-117">Gering</span><span class="sxs-lookup"><span data-stu-id="5533a-117">Minor</span></span>       |
| <span data-ttu-id="5533a-118">Version</span><span class="sxs-lookup"><span data-stu-id="5533a-118">Version</span></span> | <span data-ttu-id="5533a-119">4.7.2</span><span class="sxs-lookup"><span data-stu-id="5533a-119">4.7.2</span></span>       |
| <span data-ttu-id="5533a-120">Typ</span><span class="sxs-lookup"><span data-stu-id="5533a-120">Type</span></span>    | <span data-ttu-id="5533a-121">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="5533a-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="5533a-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5533a-122">Affected APIs</span></span>

- <xref:System.IO.Compression.DeflateStream?displayProperty=nameWithType>
- <xref:System.IO.Compression.GZipStream?displayProperty=nameWithType>
