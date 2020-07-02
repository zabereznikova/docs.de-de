---
ms.openlocfilehash: 662c140f019add66ff6605d47ad1f32c3f50d711
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620242"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="c2f1a-101">„EventSource.WriteEvent impls“ muss denselben Parameter (inklusive einer ID) an WriteEvent übergeben, den es erhalten hat</span><span class="sxs-lookup"><span data-stu-id="c2f1a-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

#### <a name="details"></a><span data-ttu-id="c2f1a-102">Details</span><span class="sxs-lookup"><span data-stu-id="c2f1a-102">Details</span></span>

<span data-ttu-id="c2f1a-103">Die Runtime erzwingt jetzt den Vertrag, der Folgendes angibt: Eine Klasse, die von <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> abgeleitet wird und eine ETW-Ereignismethode definiert, muss die <code>EventSource.WriteEvent</code>-Methode der Basisklasse mit der Ereignis-ID, gefolgt von den gleichen Argumenten, die an die ETW-Ereignismethode übergeben wurden, aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c2f1a-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c2f1a-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c2f1a-104">Suggestion</span></span>

<span data-ttu-id="c2f1a-105">Eine <xref:System.IndexOutOfRangeException?displayProperty=fullName>-Ausnahme wird ausgelöst, wenn <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>-Daten im Prozess für eine Ereignisquelle liest, die gegen diesen Vertrag verstößt.</span><span class="sxs-lookup"><span data-stu-id="c2f1a-105">An <xref:System.IndexOutOfRangeException?displayProperty=fullName> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process for an event source that violates this contract.</span></span>

| <span data-ttu-id="c2f1a-106">name</span><span class="sxs-lookup"><span data-stu-id="c2f1a-106">Name</span></span>    | <span data-ttu-id="c2f1a-107">Wert</span><span class="sxs-lookup"><span data-stu-id="c2f1a-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c2f1a-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="c2f1a-108">Scope</span></span>   |<span data-ttu-id="c2f1a-109">Gering</span><span class="sxs-lookup"><span data-stu-id="c2f1a-109">Minor</span></span>|
|<span data-ttu-id="c2f1a-110">Version</span><span class="sxs-lookup"><span data-stu-id="c2f1a-110">Version</span></span>|<span data-ttu-id="c2f1a-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="c2f1a-111">4.5.1</span></span>|
|<span data-ttu-id="c2f1a-112">Typ</span><span class="sxs-lookup"><span data-stu-id="c2f1a-112">Type</span></span>|<span data-ttu-id="c2f1a-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c2f1a-113">Runtime</span></span>|
