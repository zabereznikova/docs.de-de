---
ms.openlocfilehash: 30580b3fde5b8a99862896bb7d31c6c4024f97e8
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198438"
---
### <a name="floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception"></a><span data-ttu-id="32f40-101">Gleitkomma-Analysevorgänge lösen keinen Fehler und keine OverflowException mehr aus</span><span class="sxs-lookup"><span data-stu-id="32f40-101">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>

<span data-ttu-id="32f40-102">Die Gleitkomma-Analysemethoden lösen keine <xref:System.OverflowException> mehr aus und geben auch nicht `false` zurück, wenn sie eine Zeichenfolge analysieren, deren Zahlenwert außerhalb des Bereichs des Gleitkommatyps <xref:System.Single> oder <xref:System.Double> liegt.</span><span class="sxs-lookup"><span data-stu-id="32f40-102">The floating-point parsing methods no longer throw an <xref:System.OverflowException> or return `false` when they parse a string whose numeric value is outside the range of the <xref:System.Single> or <xref:System.Double> floating-point type.</span></span>

#### <a name="change-description"></a><span data-ttu-id="32f40-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="32f40-103">Change description</span></span>

<span data-ttu-id="32f40-104">In .NET Core 2.2 und früheren Versionen lösen die Methoden <xref:System.Double.Parse%2A?displayProperty=nameWithType> und <xref:System.Single.Parse%2A?displayProperty=nameWithType> eine <xref:System.OverflowException> für Werte aus, die außerhalb des Bereichs ihres jeweiligen Typs liegen.</span><span class="sxs-lookup"><span data-stu-id="32f40-104">In .NET Core 2.2 and earlier versions, the <xref:System.Double.Parse%2A?displayProperty=nameWithType> and <xref:System.Single.Parse%2A?displayProperty=nameWithType> methods throw an <xref:System.OverflowException> for values that outside the range of their respective type.</span></span> <span data-ttu-id="32f40-105">Die Methoden <xref:System.Double.TryParse%2A?displayProperty=nameWithType> und <xref:System.Single.TryParse%2A?displayProperty=nameWithType> geben `false` für die Zeichenfolgendarstellungen von numerischen Werten außerhalb des gültigen Bereichs zurück.</span><span class="sxs-lookup"><span data-stu-id="32f40-105">The <xref:System.Double.TryParse%2A?displayProperty=nameWithType> and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> methods return `false` for the string representations of out-of-range numeric values.</span></span>

<span data-ttu-id="32f40-106">Ab .NET Core 3.0 schlagen die Methoden <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType> und <xref:System.Single.TryParse%2A?displayProperty=nameWithType> nicht mehr fehl, wenn Sie außerhalb des gültigen Bereichs liegende numerische Zeichenfolgen analysieren.</span><span class="sxs-lookup"><span data-stu-id="32f40-106">Starting with .NET Core 3.0, the <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType>, and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> methods no longer fail when parsing out-of-range numeric strings.</span></span> <span data-ttu-id="32f40-107">Stattdessen geben die <xref:System.Double>-Analysemethoden <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> für Werte, die <xref:System.Double.MaxValue?displayProperty=nameWithType> überschreiten, und <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> für Werte zurück, die kleiner als <xref:System.Double.MinValue?displayProperty=nameWithType> sind.</span><span class="sxs-lookup"><span data-stu-id="32f40-107">Instead, the <xref:System.Double> parsing methods return <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> for values that exceed <xref:System.Double.MaxValue?displayProperty=nameWithType>, and they return <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> for values that are less than <xref:System.Double.MinValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="32f40-108">Analog dazu geben die <xref:System.Single>-Analysemethoden <xref:System.Single.PositiveInfinity?displayProperty=nameWithType> für Werte, die <xref:System.Single.MaxValue?displayProperty=nameWithType> überschreiten, und <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> für Werte zurück, die kleiner als <xref:System.Single.MinValue?displayProperty=nameWithType> sind.</span><span class="sxs-lookup"><span data-stu-id="32f40-108">Similarly, the <xref:System.Single> parsing methods return <xref:System.Single.PositiveInfinity?displayProperty=nameWithType> for values that exceed <xref:System.Single.MaxValue?displayProperty=nameWithType>, and they return <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> for values that are less than <xref:System.Single.MinValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="32f40-109">Diese Änderung wurde vorgenommen, um die Konformität mit IEEE 754:2008 zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="32f40-109">This change was made for improved IEEE 754:2008 compliance.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="32f40-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="32f40-110">Version introduced</span></span>

<span data-ttu-id="32f40-111">3.0</span><span class="sxs-lookup"><span data-stu-id="32f40-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="32f40-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="32f40-112">Recommended action</span></span>

<span data-ttu-id="32f40-113">Diese Änderung kann sich auf zwei Arten auf den Code auswirken:</span><span class="sxs-lookup"><span data-stu-id="32f40-113">This change can affect your code in either of two ways:</span></span>

- <span data-ttu-id="32f40-114">Der Code hängt vom Handler für die <xref:System.OverflowException> ab, der ausgeführt wird, wenn ein Überlauf auftritt.</span><span class="sxs-lookup"><span data-stu-id="32f40-114">Your code depends on the handler for the <xref:System.OverflowException> to execute when an overflow occurs.</span></span> <span data-ttu-id="32f40-115">In diesem Fall sollten Sie die `catch`-Anweisung entfernen und erforderlichen Code in einer `If`-Anweisung platzieren, die testet, ob <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> oder <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> `true` ist.</span><span class="sxs-lookup"><span data-stu-id="32f40-115">In this case, you should remove the `catch` statement and place any necessary code in an `If` statement that tests whether <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> or <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> is `true`.</span></span>

- <span data-ttu-id="32f40-116">Ihr Code geht davon aus, dass Gleitkommawerte nicht `Infinity` sind.</span><span class="sxs-lookup"><span data-stu-id="32f40-116">Your code assumes that floating-point values are not `Infinity`.</span></span> <span data-ttu-id="32f40-117">In diesem Fall sollten Sie den erforderlichen Code hinzufügen, um auf Gleitkommawerte des Typs `PositiveInfinity` und `NegativeInfinity` zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="32f40-117">In this case, you should add the necessary code to check for floating-point values of `PositiveInfinity` and `NegativeInfinity`.</span></span>

#### <a name="category"></a><span data-ttu-id="32f40-118">Kategorie</span><span class="sxs-lookup"><span data-stu-id="32f40-118">Category</span></span>

<span data-ttu-id="32f40-119">CoreFx</span><span class="sxs-lookup"><span data-stu-id="32f40-119">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="32f40-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="32f40-120">Affected APIs</span></span>

- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
