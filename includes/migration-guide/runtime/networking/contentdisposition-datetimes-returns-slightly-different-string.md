---
ms.openlocfilehash: c103dff320ae30d02c12ea5c585a47b589da8237
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621306"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a><span data-ttu-id="0e611-101">Die DateTime-Elemente von „ContentDisposition“ geben eine etwas andere Zeichenfolge zurück</span><span class="sxs-lookup"><span data-stu-id="0e611-101">ContentDisposition DateTimes returns slightly different string</span></span>

#### <a name="details"></a><span data-ttu-id="0e611-102">Details</span><span class="sxs-lookup"><span data-stu-id="0e611-102">Details</span></span>

<span data-ttu-id="0e611-103">Zeichenfolgendarstellungen von <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName> wurden ab Version 4.6 aktualisiert, um die Stundenkomponente von <xref:System.DateTime?displayProperty=fullName> immer durch zwei Ziffern darzustellen.</span><span class="sxs-lookup"><span data-stu-id="0e611-103">String representations of <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>'s have been updated, beginning in 4.6, to always represent the hour component of a <xref:System.DateTime?displayProperty=fullName> with two digits.</span></span> <span data-ttu-id="0e611-104">Dies dient zur Einhaltung von [RFC822](https://www.ietf.org/rfc/rfc0822.txt) und [RFC2822](https://www.ietf.org/rfc/rfc2822.txt).</span><span class="sxs-lookup"><span data-stu-id="0e611-104">This is to comply with [RFC822](https://www.ietf.org/rfc/rfc0822.txt) and [RFC2822](https://www.ietf.org/rfc/rfc2822.txt).</span></span> <span data-ttu-id="0e611-105">Dies bewirkt, dass <xref:System.Net.Mime.ContentDisposition.ToString> in Version 4.6 eine etwas andere Zeichenfolge in Szenarien zurückgibt, bei denen eines der Zeitelemente der Anordnung vor 10:00 Uhr liegt.</span><span class="sxs-lookup"><span data-stu-id="0e611-105">This causes <xref:System.Net.Mime.ContentDisposition.ToString> to return a slightly different string in 4.6 in scenarios where one of the disposition's time elements was before 10:00 AM.</span></span> <span data-ttu-id="0e611-106">Beachten Sie, dass ContentDisposition-Klassen manchmal durch Konvertierung in Zeichenfolgen serialisiert werden, daher sollten alle <xref:System.Net.Mime.ContentDisposition.ToString>-Vorgänge, Serialisierungen oder GetHashCode-Aufrufe überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="0e611-106">Note that ContentDispositions are sometimes serialized via converting them to strings, so any <xref:System.Net.Mime.ContentDisposition.ToString> operations, serialization, or GetHashCode calls should be reviewed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0e611-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="0e611-107">Suggestion</span></span>

<span data-ttu-id="0e611-108">Erwarten Sie nicht, dass die Zeichenfolgendarstellungen von „ContentDispositions“ aus verschiedenen Versionen von .NET Framework ordnungsgemäß miteinander verglichen werden können.</span><span class="sxs-lookup"><span data-stu-id="0e611-108">Do not expect that string representations of ContentDispositions from different .NET Framework versions will correctly compare to one another.</span></span> <span data-ttu-id="0e611-109">Konvertieren Sie die Zeichenfolgen wieder in „ContentDispositions“, sofern möglich, bevor Sie einen Vergleich durchführen.</span><span class="sxs-lookup"><span data-stu-id="0e611-109">Convert the strings back to ContentDispositions, if possible, before conducting a comparison.</span></span>

| <span data-ttu-id="0e611-110">name</span><span class="sxs-lookup"><span data-stu-id="0e611-110">Name</span></span>    | <span data-ttu-id="0e611-111">Wert</span><span class="sxs-lookup"><span data-stu-id="0e611-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0e611-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="0e611-112">Scope</span></span>   |<span data-ttu-id="0e611-113">Gering</span><span class="sxs-lookup"><span data-stu-id="0e611-113">Minor</span></span>|
|<span data-ttu-id="0e611-114">Version</span><span class="sxs-lookup"><span data-stu-id="0e611-114">Version</span></span>|<span data-ttu-id="0e611-115">4.6</span><span class="sxs-lookup"><span data-stu-id="0e611-115">4.6</span></span>|
|<span data-ttu-id="0e611-116">Typ</span><span class="sxs-lookup"><span data-stu-id="0e611-116">Type</span></span>|<span data-ttu-id="0e611-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="0e611-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0e611-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0e611-118">Affected APIs</span></span>

-<xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType></li><li><xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType></li></ul>|
