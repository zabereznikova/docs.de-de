---
ms.openlocfilehash: 3d29848e12d496d2d53c204e00ef8604831495e1
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024697"
---
### <a name="intptr-and-uintptr-implement-iformattable"></a><span data-ttu-id="231e1-101">IntPtr und UIntPtr implementieren IFormattable</span><span class="sxs-lookup"><span data-stu-id="231e1-101">IntPtr and UIntPtr implement IFormattable</span></span>

<span data-ttu-id="231e1-102"><xref:System.IntPtr> und <xref:System.UIntPtr> implementieren jetzt <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="231e1-102"><xref:System.IntPtr> and <xref:System.UIntPtr> now implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="231e1-103">Funktionen, die auf <xref:System.IFormattable>-Unterstützung überprüfen, können nun unterschiedliche Ergebnisse für diese Typen zurückgeben, da sie einen Formatbezeichner und eine Kultur übergeben können.</span><span class="sxs-lookup"><span data-stu-id="231e1-103">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

#### <a name="change-description"></a><span data-ttu-id="231e1-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="231e1-104">Change description</span></span>

<span data-ttu-id="231e1-105">In früheren Versionen von .NET haben <xref:System.IntPtr> und <xref:System.UIntPtr> <xref:System.IFormattable> nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="231e1-105">In previous versions of .NET, <xref:System.IntPtr> and <xref:System.UIntPtr> do not implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="231e1-106">Funktionen, die auf <xref:System.IFormattable> überprüfen, können auf das einfache Aufrufen von <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> oder <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType> zurückfallen, was bedeutet, dass Formatbezeichner und Kulturen nicht beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="231e1-106">Functions that check for <xref:System.IFormattable> may fall back to just calling <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> or <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, which means that format specifiers and cultures are not respected.</span></span>

<span data-ttu-id="231e1-107">In .NET 5.0 und höheren Versionen implementieren <xref:System.IntPtr> und <xref:System.UIntPtr> <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="231e1-107">In .NET 5.0 and later versions, <xref:System.IntPtr> and <xref:System.UIntPtr> implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="231e1-108">Funktionen, die auf <xref:System.IFormattable>-Unterstützung überprüfen, können nun unterschiedliche Ergebnisse für diese Typen zurückgeben, da sie einen Formatbezeichner und eine Kultur übergeben können.</span><span class="sxs-lookup"><span data-stu-id="231e1-108">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

<span data-ttu-id="231e1-109">Diese Änderung wirkt sich z. B. auf Szenarien wie interpolierte Zeichenfolgen und <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> aus.</span><span class="sxs-lookup"><span data-stu-id="231e1-109">This change impacts scenarios like interpolated strings and <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, among others.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="231e1-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="231e1-110">Reason for change</span></span>

<span data-ttu-id="231e1-111"><xref:System.IntPtr> und <xref:System.UIntPtr> weisen jetzt Sprachunterstützung in C# durch die Schlüsselwörter `nint` und `nuint` auf.</span><span class="sxs-lookup"><span data-stu-id="231e1-111"><xref:System.IntPtr> and <xref:System.UIntPtr> now have language support in C# through the `nint` and `nuint` keywords.</span></span> <span data-ttu-id="231e1-112">Die Unterstützungstypen wurden aktualisiert, um Nähe der Parität (sofern möglich) mit Funktionen bereitzustellen, die von anderen primitiven Typen wie <xref:System.Int32?displayProperty=nameWithType> zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="231e1-112">The backing types were updated to provide near parity (where possible) with functionality exposed by other primitive types, such as <xref:System.Int32?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="231e1-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="231e1-113">Version introduced</span></span>

<span data-ttu-id="231e1-114">5.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="231e1-114">5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="231e1-115">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="231e1-115">Recommended action</span></span>

<span data-ttu-id="231e1-116">Wenn Sie nicht möchten, dass bei der Anzeige von Werten dieser Art ein Formatbezeichner oder eine benutzerdefinierte Kultur verwendet wird, können Sie die <xref:System.IntPtr.ToString?displayProperty=nameWithType>- und <xref:System.UIntPtr.ToString?displayProperty=nameWithType>-Überladungen von `ToString()` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="231e1-116">If you don't want a format specifier or custom culture to be used when displaying values of these types, you can call the <xref:System.IntPtr.ToString?displayProperty=nameWithType> and <xref:System.UIntPtr.ToString?displayProperty=nameWithType> overloads of `ToString()`.</span></span>

#### <a name="category"></a><span data-ttu-id="231e1-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="231e1-117">Category</span></span>

<span data-ttu-id="231e1-118">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="231e1-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="231e1-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="231e1-119">Affected APIs</span></span>

<span data-ttu-id="231e1-120">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="231e1-120">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
