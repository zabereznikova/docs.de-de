---
ms.openlocfilehash: 99a7fa0fcfce6d490a182f85709b5dd0e0e8c86f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496097"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="90553-101">„EventSource.WriteEvent impls“ muss denselben Parameter (inklusive einer ID) an WriteEvent übergeben, den es erhalten hat</span><span class="sxs-lookup"><span data-stu-id="90553-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

#### <a name="details"></a><span data-ttu-id="90553-102">Details</span><span class="sxs-lookup"><span data-stu-id="90553-102">Details</span></span>

<span data-ttu-id="90553-103">Die Runtime erzwingt jetzt den Vertrag, der Folgendes angibt: Eine Klasse, die von <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> abgeleitet wird und eine ETW-Ereignismethode definiert, muss die <code>EventSource.WriteEvent</code>-Methode der Basisklasse mit der Ereignis-ID, gefolgt von den gleichen Argumenten, die an die ETW-Ereignismethode übergeben wurden, aufrufen.</span><span class="sxs-lookup"><span data-stu-id="90553-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="90553-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="90553-104">Suggestion</span></span>

<span data-ttu-id="90553-105">Eine <xref:System.IndexOutOfRangeException?displayProperty=fullName>-Ausnahme wird ausgelöst, wenn <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>-Daten im Prozess für eine Ereignisquelle liest, die gegen diesen Vertrag verstößt.</span><span class="sxs-lookup"><span data-stu-id="90553-105">An <xref:System.IndexOutOfRangeException?displayProperty=fullName> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process for an event source that violates this contract.</span></span>

| <span data-ttu-id="90553-106">name</span><span class="sxs-lookup"><span data-stu-id="90553-106">Name</span></span>    | <span data-ttu-id="90553-107">Wert</span><span class="sxs-lookup"><span data-stu-id="90553-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="90553-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="90553-108">Scope</span></span>   |<span data-ttu-id="90553-109">Gering</span><span class="sxs-lookup"><span data-stu-id="90553-109">Minor</span></span>|
|<span data-ttu-id="90553-110">Version</span><span class="sxs-lookup"><span data-stu-id="90553-110">Version</span></span>|<span data-ttu-id="90553-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="90553-111">4.5.1</span></span>|
|<span data-ttu-id="90553-112">Typ</span><span class="sxs-lookup"><span data-stu-id="90553-112">Type</span></span>|<span data-ttu-id="90553-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="90553-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="90553-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="90553-114">Affected APIs</span></span>

<span data-ttu-id="90553-115">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="90553-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
