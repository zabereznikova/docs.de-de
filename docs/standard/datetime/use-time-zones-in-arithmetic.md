---
title: 'Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], adding and subtracting
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f9d326750cdef96be1aa6055d46b4ac08ec7a0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574581"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a><span data-ttu-id="9281c-102">Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen</span><span class="sxs-lookup"><span data-stu-id="9281c-102">How to: Use time zones in date and time arithmetic</span></span>

<span data-ttu-id="9281c-103">Normalerweise beim Ausführen von Datum und Zeit arithmetische <xref:System.DateTime> oder <xref:System.DateTimeOffset> Werte, die das Ergebnis sind keine Regeln zur Anpassung der Zeitzone enthalten.</span><span class="sxs-lookup"><span data-stu-id="9281c-103">Ordinarily, when you perform date and time arithmetic using <xref:System.DateTime> or <xref:System.DateTimeOffset> values, the result does not reflect any time zone adjustment rules.</span></span> <span data-ttu-id="9281c-104">Dies ist "true", selbst wenn der Wert für Datum und Uhrzeit der Zeitzone eindeutig erkennbar ist (z. B. wenn die <xref:System.DateTime.Kind%2A> -Eigenschaftensatz auf <xref:System.DateTimeKind.Local>).</span><span class="sxs-lookup"><span data-stu-id="9281c-104">This is true even when the time zone of the date and time value is clearly identifiable (for example, when the <xref:System.DateTime.Kind%2A> property is set to <xref:System.DateTimeKind.Local>).</span></span> <span data-ttu-id="9281c-105">In diesem Thema wird gezeigt, wie arithmetische Operationen für Datums-und Uhrzeitwerte ausgeführt, die zu einer bestimmten Zeitzone gehören.</span><span class="sxs-lookup"><span data-stu-id="9281c-105">This topic shows how to perform arithmetic operations on date and time values that belong to a particular time zone.</span></span> <span data-ttu-id="9281c-106">Die Ergebnisse der arithmetischen Operationen berücksichtigen die Anpassungsregeln der Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="9281c-106">The results of the arithmetic operations will reflect the time zone's adjustment rules.</span></span>

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a><span data-ttu-id="9281c-107">So wenden Sie Anpassungsregeln auf arithmetische Datums- und Uhrzeitoperationen an</span><span class="sxs-lookup"><span data-stu-id="9281c-107">To apply adjustment rules to date and time arithmetic</span></span>

1. <span data-ttu-id="9281c-108">Implementieren Sie eine beliebige Methode, mit der ein Datums- und Uhrzeitwert eng mit der Zeitzone verknüpft wird, zu der er gehört.</span><span class="sxs-lookup"><span data-stu-id="9281c-108">Implement some method of closely coupling a date and time value with the time zone to which it belongs.</span></span> <span data-ttu-id="9281c-109">Deklarieren Sie z.B. eine Struktur, die sowohl den Datums- als auch den Uhrzeitwert und die Zeitzone einschließt.</span><span class="sxs-lookup"><span data-stu-id="9281c-109">For example, declare a structure that includes both the date and time value and its time zone.</span></span> <span data-ttu-id="9281c-110">Im folgenden Beispiel wird dieser Ansatz zum Verknüpfen einer <xref:System.DateTime> Wert mit seiner Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="9281c-110">The following example uses this approach to link a <xref:System.DateTime> value with its time zone.</span></span>

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. <span data-ttu-id="9281c-111">Konvertiert eine Uhrzeit in Coordinated Universal Time (UTC) durch Aufrufen der <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> Methode oder die <xref:System.TimeZoneInfo.ConvertTime%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="9281c-111">Convert a time to Coordinated Universal Time (UTC) by calling either the <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> method or the <xref:System.TimeZoneInfo.ConvertTime%2A> method.</span></span>

3. <span data-ttu-id="9281c-112">Führen Sie die arithmetische Operation für die UTC-Zeit aus.</span><span class="sxs-lookup"><span data-stu-id="9281c-112">Perform the arithmetic operation on the UTC time.</span></span>

4. <span data-ttu-id="9281c-113">Die Zeit von UTC in die ursprüngliche Uhrzeit zugehörigen Zeitzone zu konvertieren, durch Aufrufen der <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="9281c-113">Convert the time from UTC to the original time's associated time zone by calling the <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span>

## <a name="example"></a><span data-ttu-id="9281c-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9281c-114">Example</span></span>

<span data-ttu-id="9281c-115">Im folgenden Beispiel werden zwei Stunden und 30 Minuten zum 9. März 2008 um 1:30 Uhr</span><span class="sxs-lookup"><span data-stu-id="9281c-115">The following example adds two hours and thirty minutes to March 9, 2008, at 1:30 A.M.</span></span> <span data-ttu-id="9281c-116">Central Standard Time hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9281c-116">Central Standard Time.</span></span> <span data-ttu-id="9281c-117">Die Umstellung auf Sommerzeit erfolgt in der Zeitzone dreißig Minuten später, um 2:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="9281c-117">The time zone's transition to daylight saving time occurs thirty minutes later, at 2:00 A.M.</span></span> <span data-ttu-id="9281c-118">am 9.März 2008.</span><span class="sxs-lookup"><span data-stu-id="9281c-118">on March 9, 2008.</span></span> <span data-ttu-id="9281c-119">Da das Beispiel den vier Schritten folgt, die im vorherigen Abschnitt aufgeführt sind, ist das Ergebnis die richtige Zeit von 5:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="9281c-119">Because the example follows the four steps listed in the previous section, it correctly reports the resulting time as 5:00 A.M.</span></span> <span data-ttu-id="9281c-120">am 9. März 2008.</span><span class="sxs-lookup"><span data-stu-id="9281c-120">on March 9, 2008.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

<span data-ttu-id="9281c-121">Beide <xref:System.DateTime> und <xref:System.DateTimeOffset> Werte werden an eine beliebige Zeitzone, zu dem sie gehören möglicherweise, aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="9281c-121">Both <xref:System.DateTime> and <xref:System.DateTimeOffset> values are disassociated from any time zone to which they might belong.</span></span> <span data-ttu-id="9281c-122">Um arithmetische Datums- und Uhrzeitoperationen so durchführen zu können, dass Anpassungsregeln für Zeitzonen automatisch angewendet werden, muss die Zeitzone, zu der der Datums- und Uhrzeitwert gehört, direkt identifizierbar sein.</span><span class="sxs-lookup"><span data-stu-id="9281c-122">To perform date and time arithmetic in a way that automatically applies a time zone's adjustment rules, the time zone to which any date and time value belongs must be immediately identifiable.</span></span> <span data-ttu-id="9281c-123">Dies bedeutet, dass Datum und Uhrzeit sowie die zugeordnete Zeitzone eng verknüpft sein müssen.</span><span class="sxs-lookup"><span data-stu-id="9281c-123">This means that a date and time and its associated time zone must be tightly coupled.</span></span> <span data-ttu-id="9281c-124">Hierzu gibt es mehrere Möglichkeiten, darunter die folgenden:</span><span class="sxs-lookup"><span data-stu-id="9281c-124">There are several ways to do this, which include the following:</span></span>

* <span data-ttu-id="9281c-125">Nehmen Sie an, dass alle in einer Anwendung verwendeten Uhrzeiten zu einer bestimmten Zeitzone gehören.</span><span class="sxs-lookup"><span data-stu-id="9281c-125">Assume that all times used in an application belong to a particular time zone.</span></span> <span data-ttu-id="9281c-126">Obwohl dieser Ansatz in einigen Fällen geeignet ist, bietet er jedoch nur eingeschränkte Flexibilität sowie möglicherweise eine eingeschränkte Portabilität.</span><span class="sxs-lookup"><span data-stu-id="9281c-126">Although appropriate in some cases, this approach offers limited flexibility and possibly limited portability.</span></span>

* <span data-ttu-id="9281c-127">Definieren Sie einen Typ, der ein Datum und eine Uhrzeit eng mit der zugehörigen Zeitzone verknüpft, indem Sie beide als Felder des Typs einschließen.</span><span class="sxs-lookup"><span data-stu-id="9281c-127">Define a type that tightly couples a date and time with its associated time zone by including both as fields of the type.</span></span> <span data-ttu-id="9281c-128">Dieser Ansatz wird im Codebeispiel verwendet, in dem eine Struktur zum Speichern des Datums und der Uhrzeit sowie der Zeitzone in zwei Memberfeldern definiert wird.</span><span class="sxs-lookup"><span data-stu-id="9281c-128">This approach is used in the code example, which defines a structure to store the date and time and the time zone in two member fields.</span></span>

<span data-ttu-id="9281c-129">Im Beispiel wird veranschaulicht, wie arithmetische Operationen für <xref:System.DateTime> Werte so, dass die Regeln zur Anpassung der Zeitzone auf das Ergebnis angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9281c-129">The example illustrates how to perform arithmetic operations on <xref:System.DateTime> values so that time zone adjustment rules are applied to the result.</span></span> <span data-ttu-id="9281c-130">Allerdings <xref:System.DateTimeOffset> Werte genauso einfach verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9281c-130">However, <xref:System.DateTimeOffset> values can be used just as easily.</span></span> <span data-ttu-id="9281c-131">Im folgende Beispiel wird veranschaulicht, wie der Code im ursprünglichen Beispiel angepasst werden möglicherweise <xref:System.DateTimeOffset> anstelle von <xref:System.DateTime> Werte.</span><span class="sxs-lookup"><span data-stu-id="9281c-131">The following example illustrates how the code in the original example might be adapted to use <xref:System.DateTimeOffset> instead of <xref:System.DateTime> values.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

<span data-ttu-id="9281c-132">Beachten Sie, dass diese Ergänzung einfach nach erfolgt die <xref:System.DateTimeOffset> ohne zuerst in UTC konvertiert, das Ergebnis richtigen Zeitpunkt zeitlich wobei der Offset ist nicht widerspiegelt, die der festgelegten Zeitzone für diese Zeit-Wert.</span><span class="sxs-lookup"><span data-stu-id="9281c-132">Note that if this addition is simply performed on the <xref:System.DateTimeOffset> value without first converting it to UTC, the result reflects the correct point in time but its offset does not reflect that of the designated time zone for that time.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="9281c-133">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9281c-133">Compiling the code</span></span>

<span data-ttu-id="9281c-134">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9281c-134">This example requires:</span></span>

* <span data-ttu-id="9281c-135">Dem Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9281c-135">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="9281c-136">Dass die <xref:System> Namespace importiert werden, mit der `using` -Anweisung (in C#-Code erforderlich).</span><span class="sxs-lookup"><span data-stu-id="9281c-136">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="9281c-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9281c-137">See also</span></span>

<span data-ttu-id="9281c-138">[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[durchführen arithmetischer Datums-und Uhrzeitoperationen](../../../docs/standard/datetime/performing-arithmetic-operations.md)</span><span class="sxs-lookup"><span data-stu-id="9281c-138">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Performing arithmetic operations with dates and times](../../../docs/standard/datetime/performing-arithmetic-operations.md)</span></span>
