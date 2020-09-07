---
ms.openlocfilehash: eb5c032a020799fa19cc0a8cfaabb56e01417ff4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496454"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a><span data-ttu-id="663ed-101">Die DateTime-Elemente von „ContentDisposition“ geben eine etwas andere Zeichenfolge zurück</span><span class="sxs-lookup"><span data-stu-id="663ed-101">ContentDisposition DateTimes returns slightly different string</span></span>

#### <a name="details"></a><span data-ttu-id="663ed-102">Details</span><span class="sxs-lookup"><span data-stu-id="663ed-102">Details</span></span>

<span data-ttu-id="663ed-103">Zeichenfolgendarstellungen von <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName> wurden ab Version 4.6 aktualisiert, um die Stundenkomponente von <xref:System.DateTime?displayProperty=fullName> immer durch zwei Ziffern darzustellen.</span><span class="sxs-lookup"><span data-stu-id="663ed-103">String representations of <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>'s have been updated, beginning in 4.6, to always represent the hour component of a <xref:System.DateTime?displayProperty=fullName> with two digits.</span></span> <span data-ttu-id="663ed-104">Dies dient zur Einhaltung von [RFC822](https://www.ietf.org/rfc/rfc0822.txt) und [RFC2822](https://www.ietf.org/rfc/rfc2822.txt).</span><span class="sxs-lookup"><span data-stu-id="663ed-104">This is to comply with [RFC822](https://www.ietf.org/rfc/rfc0822.txt) and [RFC2822](https://www.ietf.org/rfc/rfc2822.txt).</span></span> <span data-ttu-id="663ed-105">Dies bewirkt, dass <xref:System.Net.Mime.ContentDisposition.ToString> in Version 4.6 eine etwas andere Zeichenfolge in Szenarien zurückgibt, bei denen eines der Zeitelemente der Anordnung vor 10:00 Uhr liegt.</span><span class="sxs-lookup"><span data-stu-id="663ed-105">This causes <xref:System.Net.Mime.ContentDisposition.ToString> to return a slightly different string in 4.6 in scenarios where one of the disposition's time elements was before 10:00 AM.</span></span> <span data-ttu-id="663ed-106">Beachten Sie, dass ContentDisposition-Klassen manchmal durch Konvertierung in Zeichenfolgen serialisiert werden, daher sollten alle <xref:System.Net.Mime.ContentDisposition.ToString>-Vorgänge, Serialisierungen oder GetHashCode-Aufrufe überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="663ed-106">Note that ContentDispositions are sometimes serialized via converting them to strings, so any <xref:System.Net.Mime.ContentDisposition.ToString> operations, serialization, or GetHashCode calls should be reviewed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="663ed-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="663ed-107">Suggestion</span></span>

<span data-ttu-id="663ed-108">Erwarten Sie nicht, dass die Zeichenfolgendarstellungen von „ContentDispositions“ aus verschiedenen Versionen von .NET Framework ordnungsgemäß miteinander verglichen werden können.</span><span class="sxs-lookup"><span data-stu-id="663ed-108">Do not expect that string representations of ContentDispositions from different .NET Framework versions will correctly compare to one another.</span></span> <span data-ttu-id="663ed-109">Konvertieren Sie die Zeichenfolgen wieder in „ContentDispositions“, sofern möglich, bevor Sie einen Vergleich durchführen.</span><span class="sxs-lookup"><span data-stu-id="663ed-109">Convert the strings back to ContentDispositions, if possible, before conducting a comparison.</span></span>

| <span data-ttu-id="663ed-110">name</span><span class="sxs-lookup"><span data-stu-id="663ed-110">Name</span></span>    | <span data-ttu-id="663ed-111">Wert</span><span class="sxs-lookup"><span data-stu-id="663ed-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="663ed-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="663ed-112">Scope</span></span>   |<span data-ttu-id="663ed-113">Gering</span><span class="sxs-lookup"><span data-stu-id="663ed-113">Minor</span></span>|
|<span data-ttu-id="663ed-114">Version</span><span class="sxs-lookup"><span data-stu-id="663ed-114">Version</span></span>|<span data-ttu-id="663ed-115">4.6</span><span class="sxs-lookup"><span data-stu-id="663ed-115">4.6</span></span>|
|<span data-ttu-id="663ed-116">Typ</span><span class="sxs-lookup"><span data-stu-id="663ed-116">Type</span></span>|<span data-ttu-id="663ed-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="663ed-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="663ed-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="663ed-118">Affected APIs</span></span>

- <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType>
- <xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Net.Mime.ContentDisposition.ToString`
- `M:System.Net.Mime.ContentDisposition.GetHashCode`

-->
