---
ms.openlocfilehash: e4d9efe7d2a06a1e501b070c23184dcd913dba71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621282"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a><span data-ttu-id="282ec-101">Der persische Kalender verwendet jetzt den Hijri-Solaralgorithmus</span><span class="sxs-lookup"><span data-stu-id="282ec-101">Persian calendar now uses the Hijri solar algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="282ec-102">Details</span><span class="sxs-lookup"><span data-stu-id="282ec-102">Details</span></span>

<span data-ttu-id="282ec-103">Ab .NET Framework 4.6 verwendet die <xref:System.Globalization.PersianCalendar?displayProperty=fullName>-Klasse den Hijri-Solaralgorithmus.</span><span class="sxs-lookup"><span data-stu-id="282ec-103">Starting with the .NET Framework 4.6, the <xref:System.Globalization.PersianCalendar?displayProperty=fullName> class uses the Hijri solar algorithm.</span></span> <span data-ttu-id="282ec-104">Das Konvertieren von Datumsangaben zwischen <xref:System.Globalization.PersianCalendar?displayProperty=fullName> und anderen Kalendern erzeugt ab .NET Framework 4.6 für Datumsangaben vor 1800 oder nach 2023 (gregorianisch) möglicherweise ein etwas anderes Ergebnis. Darüber hinaus entspricht <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> nun <code>March 22, 0622</code> anstatt <code>March 21, 0622</code>.</span><span class="sxs-lookup"><span data-stu-id="282ec-104">Converting dates between the <xref:System.Globalization.PersianCalendar?displayProperty=fullName> and other calendars may produce a slightly different result beginning with the .NET Framework 4.6 for dates earlier than 1800 or later than 2023 (Gregorian).Also, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> is now <code>March 22, 0622</code> instead of <code>March 21, 0622</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="282ec-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="282ec-105">Suggestion</span></span>

<span data-ttu-id="282ec-106">Beachten Sie, dass einige frühe oder späte Datumsangaben bei der Verwendung des persischen Kalenders in .NET Framework 4.6 möglicherweise etwas anders aussehen.</span><span class="sxs-lookup"><span data-stu-id="282ec-106">Be aware that some early or late dates may be slightly different when using the PersianCalendar in .NET Framework 4.6.</span></span> <span data-ttu-id="282ec-107">Speichern Sie zudem beim Serialisieren von Daten zwischen Prozessen, die möglicherweise unter verschiedenen Versionen von .NET Framework ausgeführt werden, die Daten nicht als PersionCalendar-Datumszeichenfolgen (da diese Werte abweichen können).</span><span class="sxs-lookup"><span data-stu-id="282ec-107">Also, when serializing dates between processes which may run on different .NET Framework versions, do not store them as PersianCalendar date strings (since those values may be different).</span></span>

| <span data-ttu-id="282ec-108">name</span><span class="sxs-lookup"><span data-stu-id="282ec-108">Name</span></span>    | <span data-ttu-id="282ec-109">Wert</span><span class="sxs-lookup"><span data-stu-id="282ec-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="282ec-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="282ec-110">Scope</span></span>   |<span data-ttu-id="282ec-111">Gering</span><span class="sxs-lookup"><span data-stu-id="282ec-111">Minor</span></span>|
|<span data-ttu-id="282ec-112">Version</span><span class="sxs-lookup"><span data-stu-id="282ec-112">Version</span></span>|<span data-ttu-id="282ec-113">4.6</span><span class="sxs-lookup"><span data-stu-id="282ec-113">4.6</span></span>|
|<span data-ttu-id="282ec-114">Typ</span><span class="sxs-lookup"><span data-stu-id="282ec-114">Type</span></span>|<span data-ttu-id="282ec-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="282ec-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="282ec-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="282ec-116">Affected APIs</span></span>

-<xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|
