---
ms.openlocfilehash: 06424c4fa40343a881356c20003300f65e93efbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496967"
---
### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a><span data-ttu-id="b4a23-101">WF serialisiert Expressions.Literal&lt;T&gt; DateTimes jetzt anders (unterbricht benutzerdefinierte XAML-Parser)</span><span class="sxs-lookup"><span data-stu-id="b4a23-101">WF serializes Expressions.Literal&lt;T&gt; DateTimes differently now (breaks custom XAML parsers)</span></span>

#### <a name="details"></a><span data-ttu-id="b4a23-102">Details</span><span class="sxs-lookup"><span data-stu-id="b4a23-102">Details</span></span>

<span data-ttu-id="b4a23-103">Das zugeordnete <xref:System.Windows.Markup.ValueSerializer>-Objekt konvertiert ein <xref:System.DateTime?displayProperty=fullName>- oder <xref:System.DateTimeOffset?displayProperty=fullName>-Objekt, dessen Second- und <xref:System.DateTime.Millisecond?displayProperty=fullName>-Komponenten (Sekunden und Millisekunden) ungleich 0 (null) sind und (für einen <xref:System.DateTime?displayProperty=fullName>-Wert) dessen <xref:System.DateTime.Kind>-Eigenschaft nicht angegeben ist, in eine Eigenschaftenelementsyntax anstatt in eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b4a23-103">The associated <xref:System.Windows.Markup.ValueSerializer> object will convert a <xref:System.DateTime?displayProperty=fullName> or <xref:System.DateTimeOffset?displayProperty=fullName> object whose Second and <xref:System.DateTime.Millisecond?displayProperty=fullName> components are non-zero and (for a <xref:System.DateTime?displayProperty=fullName> value) whose <xref:System.DateTime.Kind> property is not Unspecified to property element syntax instead of a string.</span></span> <span data-ttu-id="b4a23-104">Durch diese Änderung kann bei <xref:System.DateTime?displayProperty=fullName>- und <xref:System.DateTimeOffset?displayProperty=fullName>-Werten ein Roundtrip ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b4a23-104">This change allows <xref:System.DateTime?displayProperty=fullName> and <xref:System.DateTimeOffset?displayProperty=fullName> values to be round-tripped.</span></span> <span data-ttu-id="b4a23-105">Benutzerdefinierte XAML-Parser, die davon ausgehen, dass sich Eingabe-XAML in der Attributsyntax befindet, funktionieren nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="b4a23-105">Custom XAML parsers that assume that input XAML is in the attribute syntax will not function correctly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b4a23-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b4a23-106">Suggestion</span></span>

<span data-ttu-id="b4a23-107">Durch diese Änderung kann bei <xref:System.DateTime?displayProperty=fullName>- und <xref:System.DateTimeOffset?displayProperty=fullName>-Werten ein Roundtrip ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b4a23-107">This change allows <xref:System.DateTime?displayProperty=fullName> and <xref:System.DateTimeOffset?displayProperty=fullName> values to be round-tripped.</span></span> <span data-ttu-id="b4a23-108">Benutzerdefinierte XAML-Parser, die davon ausgehen, dass sich Eingabe-XAML in der Attributsyntax befindet, funktionieren nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="b4a23-108">Custom XAML parsers that assume that input XAML is in the attribute syntax will not function correctly.</span></span>

| <span data-ttu-id="b4a23-109">name</span><span class="sxs-lookup"><span data-stu-id="b4a23-109">Name</span></span>    | <span data-ttu-id="b4a23-110">Wert</span><span class="sxs-lookup"><span data-stu-id="b4a23-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b4a23-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="b4a23-111">Scope</span></span>   |<span data-ttu-id="b4a23-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b4a23-112">Edge</span></span>|
|<span data-ttu-id="b4a23-113">Version</span><span class="sxs-lookup"><span data-stu-id="b4a23-113">Version</span></span>|<span data-ttu-id="b4a23-114">4.5</span><span class="sxs-lookup"><span data-stu-id="b4a23-114">4.5</span></span>|
|<span data-ttu-id="b4a23-115">Typ</span><span class="sxs-lookup"><span data-stu-id="b4a23-115">Type</span></span>|<span data-ttu-id="b4a23-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b4a23-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b4a23-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b4a23-117">Affected APIs</span></span>

<span data-ttu-id="b4a23-118">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="b4a23-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
