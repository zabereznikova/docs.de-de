---
ms.openlocfilehash: 47d0aa554d88726caca35fa6bebe4d863fdc0695
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235229"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="60148-101">„EventSource.WriteEvent impls“ muss denselben Parameter (inklusive einer ID) an WriteEvent übergeben, den es erhalten hat</span><span class="sxs-lookup"><span data-stu-id="60148-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

|   |   |
|---|---|
|<span data-ttu-id="60148-102">Details</span><span class="sxs-lookup"><span data-stu-id="60148-102">Details</span></span>|<span data-ttu-id="60148-103">Die Runtime erzwingt jetzt den Vertrag, der Folgendes angibt: Eine Klasse, die von <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> abgeleitet wird und eine ETW-Ereignismethode definiert, muss die <code>EventSource.WriteEvent</code>-Methode der Basisklasse mit der Ereignis-ID, gefolgt von den gleichen Argumenten, die an die ETW-Ereignismethode übergeben wurden, aufrufen.</span><span class="sxs-lookup"><span data-stu-id="60148-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>|
|<span data-ttu-id="60148-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="60148-104">Suggestion</span></span>|<span data-ttu-id="60148-105">Eine <xref:System.IndexOutOfRangeException?displayProperty=name>-Ausnahme wird ausgelöst, wenn <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name>-Daten im Prozess für eine Ereignisquelle liest, die gegen diesen Vertrag verstößt.</span><span class="sxs-lookup"><span data-stu-id="60148-105">An <xref:System.IndexOutOfRangeException?displayProperty=name> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> data in process for an event source that violates this contract.</span></span>|
|<span data-ttu-id="60148-106">Bereich</span><span class="sxs-lookup"><span data-stu-id="60148-106">Scope</span></span>|<span data-ttu-id="60148-107">Gering</span><span class="sxs-lookup"><span data-stu-id="60148-107">Minor</span></span>|
|<span data-ttu-id="60148-108">Version</span><span class="sxs-lookup"><span data-stu-id="60148-108">Version</span></span>|<span data-ttu-id="60148-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="60148-109">4.5.1</span></span>|
|<span data-ttu-id="60148-110">Typ</span><span class="sxs-lookup"><span data-stu-id="60148-110">Type</span></span>|<span data-ttu-id="60148-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="60148-111">Runtime</span></span>|
