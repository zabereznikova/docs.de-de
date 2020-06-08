---
title: 'Vorgehensweise: Roundtrip-Datums- und -Uhrzeitwerte'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- round-trip date and time values
- dates [.NET Framework], round-trip values
- time zones [.NET Framework], round-trip date and time values
- time [.NET Framework], round-trip values
- formatting strings [.NET Framework], round-trip values
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
ms.openlocfilehash: 60483a6e29c65fc0c5803e8084053d53d9fc3c37
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290447"
---
# <a name="how-to-round-trip-date-and-time-values"></a><span data-ttu-id="e7d64-102">Vorgehensweise: Roundtrip-Datums- und -Uhrzeitwerte</span><span class="sxs-lookup"><span data-stu-id="e7d64-102">How to: Round-trip Date and Time Values</span></span>

<span data-ttu-id="e7d64-103">In vielen Anwendungen soll ein Datums- und Uhrzeitwert einen bestimmten Zeitpunkt eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e7d64-103">In many applications, a date and time value is intended to unambiguously identify a single point in time.</span></span> <span data-ttu-id="e7d64-104">In diesem Artikel wird gezeigt, wie ein <xref:System.DateTime>-Wert, ein <xref:System.DateTimeOffset>-Wert sowie ein Datums- und Uhrzeitwert mit Zeitzoneninformationen so gespeichert und wiederhergestellt werden, dass der wiederhergestellte Wert denselben Zeitpunkt bezeichnet wie der gespeicherte Wert.</span><span class="sxs-lookup"><span data-stu-id="e7d64-104">This article shows how to save and restore a <xref:System.DateTime> value, a <xref:System.DateTimeOffset> value, and a date and time value with time zone information so that the restored value identifies the same time as the saved value.</span></span>

## <a name="round-trip-a-datetime-value"></a><span data-ttu-id="e7d64-105">Durchführen eines Roundtrips für einen DateTime-Wert</span><span class="sxs-lookup"><span data-stu-id="e7d64-105">Round-trip a DateTime value</span></span>

1. <span data-ttu-id="e7d64-106">Konvertieren Sie den <xref:System.DateTime>-Wert in seine Zeichenfolgendarstellung, indem Sie die <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType>-Methode mit dem Formatbezeichner „o“ aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e7d64-106">Convert the <xref:System.DateTime> value to its string representation by calling the <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>

2. <span data-ttu-id="e7d64-107">Speichern Sie die Zeichenfolgendarstellung des <xref:System.DateTime>-Werts in einer Datei, oder übergeben Sie sie über einen Prozess, eine Anwendungsdomäne oder eine Computergrenze.</span><span class="sxs-lookup"><span data-stu-id="e7d64-107">Save the string representation of the <xref:System.DateTime> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>

3. <span data-ttu-id="e7d64-108">Rufen Sie die Zeichenfolge ab, die den <xref:System.DateTime>-Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="e7d64-108">Retrieve the string that represents the <xref:System.DateTime> value.</span></span>

4. <span data-ttu-id="e7d64-109">Rufen Sie die <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType>-Methode auf, und übergeben Sie <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> als Wert für den `styles`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="e7d64-109">Call the <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>

<span data-ttu-id="e7d64-110">Das folgende Beispiel veranschaulicht, wie ein Roundtrip für einen <xref:System.DateTime>-Wert ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7d64-110">The following example illustrates how to round-trip a <xref:System.DateTime> value.</span></span>

[!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
[!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]

<span data-ttu-id="e7d64-111">Beim Ausführen von Roundtrips für einen <xref:System.DateTime>-Wert wird durch diese Methode erfolgreich die Uhrzeit für alle Orts- und Weltzeiten beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e7d64-111">When round-tripping a <xref:System.DateTime> value, this technique successfully preserves the time for all local and universal times.</span></span> <span data-ttu-id="e7d64-112">Wenn beispielsweise ein lokaler <xref:System.DateTime>-Wert auf einem System in der US-Zeitzone Pacific Standard Time gespeichert und auf einem System in der US-Zeitzone Central Standard Time wiederhergestellt wird, liegen das wiederhergestellte Datum und die Uhrzeit zwei Stunden hinter der ursprünglichen Zeit, was dem Zeitunterschied zwischen den beiden Zeitzonen entspricht.</span><span class="sxs-lookup"><span data-stu-id="e7d64-112">For example, if a local <xref:System.DateTime> value is saved on a system in the U.S. Pacific Standard Time zone and is restored on a system in the U.S. Central Standard Time zone, the restored date and time will be two hours later than the original time, which reflects the time difference between the two time zones.</span></span> <span data-ttu-id="e7d64-113">Dieses Verfahren ist für nicht spezifizierte Zeiten jedoch nicht notwendigerweise genau.</span><span class="sxs-lookup"><span data-stu-id="e7d64-113">However, this technique is not necessarily accurate for unspecified times.</span></span> <span data-ttu-id="e7d64-114">Alle <xref:System.DateTime>-Werte, deren <xref:System.DateTime.Kind%2A>-Eigenschaft auf <xref:System.DateTimeKind.Unspecified> festgelegt ist, werden als Ortszeiten behandelt.</span><span class="sxs-lookup"><span data-stu-id="e7d64-114">All <xref:System.DateTime> values whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified> are treated as if they are local times.</span></span> <span data-ttu-id="e7d64-115">Wenn es sich nicht um die lokale Zeit handelt, kann der richtige Zeitpunkt durch <xref:System.DateTime> nicht erfolgreich identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="e7d64-115">If it's not a local time, the <xref:System.DateTime> doesn't successfully identify the correct point in time.</span></span> <span data-ttu-id="e7d64-116">Die Umgehung für diese Einschränkung besteht darin, einen Datums- und Zeitwert für den Speicher- und Wiederherstellungsvorgang eng an die entsprechende Zeitzone zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="e7d64-116">The workaround for this limitation is to tightly couple a date and time value with its time zone for the save and restore operation.</span></span>

## <a name="round-trip-a-datetimeoffset-value"></a><span data-ttu-id="e7d64-117">Durchführen eines Roundtrips für einen DateTimeOffset-Wert</span><span class="sxs-lookup"><span data-stu-id="e7d64-117">Round-trip a DateTimeOffset value</span></span>

1. <span data-ttu-id="e7d64-118">Konvertieren Sie den <xref:System.DateTimeOffset>-Wert in seine Zeichenfolgendarstellung, indem Sie die <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType>-Methode mit dem Formatbezeichner „o“ aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e7d64-118">Convert the <xref:System.DateTimeOffset> value to its string representation by calling the <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>

2. <span data-ttu-id="e7d64-119">Speichern Sie die Zeichenfolgendarstellung des <xref:System.DateTimeOffset>-Werts in einer Datei, oder übergeben Sie sie über einen Prozess, eine Anwendungsdomäne oder eine Computergrenze.</span><span class="sxs-lookup"><span data-stu-id="e7d64-119">Save the string representation of the <xref:System.DateTimeOffset> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>

3. <span data-ttu-id="e7d64-120">Rufen Sie die Zeichenfolge ab, die den <xref:System.DateTimeOffset>-Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="e7d64-120">Retrieve the string that represents the <xref:System.DateTimeOffset> value.</span></span>

4. <span data-ttu-id="e7d64-121">Rufen Sie die <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType>-Methode auf, und übergeben Sie <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> als Wert für den `styles`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="e7d64-121">Call the <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>

<span data-ttu-id="e7d64-122">Das folgende Beispiel veranschaulicht, wie ein Roundtrip für einen <xref:System.DateTimeOffset>-Wert ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7d64-122">The following example illustrates how to round-trip a <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
[!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]

<span data-ttu-id="e7d64-123">Durch diese Methode wird ein <xref:System.DateTimeOffset>-Wert immer eindeutig als ein einziger Zeitpunkt identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e7d64-123">This technique always unambiguously identifies a <xref:System.DateTimeOffset> value as a single point in time.</span></span> <span data-ttu-id="e7d64-124">Der Wert kann dann durch Aufrufen der <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType>-Methode in die koordinierte Weltzeit (UTC) oder durch Aufrufen der <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType>- oder <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>-Methode in die Zeit einer bestimmten Zeitzone konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7d64-124">The value can then be converted to Coordinated Universal Time (UTC) by calling the <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> method, or it can be converted to the time in a particular time zone by calling the <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> or <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e7d64-125">Die wesentliche Einschränkung dieser Methode liegt darin, dass die Datums- und Uhrzeitarithmetik möglicherweise keine genauen Ergebnisse für die jeweilige Zeitzone liefert, wenn sie bei einem <xref:System.DateTimeOffset>-Wert durchgeführt wird, der die Zeit in einer bestimmten Zeitzone darstellt.</span><span class="sxs-lookup"><span data-stu-id="e7d64-125">The major limitation of this technique is that date and time arithmetic, when performed on a <xref:System.DateTimeOffset> value that represents the time in a particular time zone, may not produce accurate results for that time zone.</span></span> <span data-ttu-id="e7d64-126">Grund hierfür ist, dass die Zuordnung eines <xref:System.DateTimeOffset>-Werts zu seiner Zeitzone bei seiner Instanziierung aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="e7d64-126">This is because when a <xref:System.DateTimeOffset> value is instantiated, it is disassociated from its time zone.</span></span> <span data-ttu-id="e7d64-127">Daher können die Anpassungsregeln für diese Zeitzone bei Datums- und Uhrzeitberechnungen nicht mehr angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7d64-127">Therefore, that time zone's adjustment rules can no longer be applied when you perform date and time calculations.</span></span> <span data-ttu-id="e7d64-128">Sie können dieses Problem umgehen, indem Sie einen benutzerdefinierten Typ definieren, der sowohl einen Datums- und Uhrzeitwert als auch die dazugehörige Zeitzone enthält.</span><span class="sxs-lookup"><span data-stu-id="e7d64-128">You can work around this problem by defining a custom type that includes both a date and time value and its accompanying time zone.</span></span>

## <a name="round-trip-a-date-and-time-value-with-its-time-zone"></a><span data-ttu-id="e7d64-129">Durchführen eines Roundtrips für einen Datums- und Uhrzeitwert mit der jeweiligen Zeitzone</span><span class="sxs-lookup"><span data-stu-id="e7d64-129">Round-trip a date and time value with its time zone</span></span>

1. <span data-ttu-id="e7d64-130">Definieren Sie eine Klasse oder Struktur mit zwei Feldern.</span><span class="sxs-lookup"><span data-stu-id="e7d64-130">Define a class or a structure with two fields.</span></span> <span data-ttu-id="e7d64-131">Beim ersten Feld handelt es sich entweder um ein <xref:System.DateTime>- oder ein <xref:System.DateTimeOffset>-Objekt und beim zweiten um ein <xref:System.TimeZoneInfo>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="e7d64-131">The first field is either a <xref:System.DateTime> or a <xref:System.DateTimeOffset> object, and the second is a <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="e7d64-132">Im folgenden Beispiel wird eine einfache Version eines solchen Typs gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7d64-132">The following example is a simple version of such a type.</span></span>

    [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
    [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]

2. <span data-ttu-id="e7d64-133">Markieren Sie die Klasse mit dem Attribut <xref:System.SerializableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e7d64-133">Mark the class with the <xref:System.SerializableAttribute> attribute.</span></span>

3. <span data-ttu-id="e7d64-134">Serialisieren Sie das Objekt mit der Methode <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e7d64-134">Serialize the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="e7d64-135">Stellen Sie das Objekt mit der Methode <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> wieder her.</span><span class="sxs-lookup"><span data-stu-id="e7d64-135">Restore the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> method.</span></span>

5. <span data-ttu-id="e7d64-136">Wandeln Sie (in C#) das deserialisierte Objekt in ein Objekt des entsprechenden Typs um, oder konvertieren Sie es (in Visual Basic) in diesen Typ.</span><span class="sxs-lookup"><span data-stu-id="e7d64-136">Cast (in C#) or convert (in Visual Basic) the deserialized object to an object of the appropriate type.</span></span>

<span data-ttu-id="e7d64-137">Im folgenden Beispiel wird veranschaulicht, wie ein Roundtrip für ein Objekt durchgeführt wird, das sowohl Zeitzonen- als auch Datums- und Uhrzeitinformationen speichert.</span><span class="sxs-lookup"><span data-stu-id="e7d64-137">The following example illustrates how to round-trip an object that stores both time zone and date and time information.</span></span>

[!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
[!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]

<span data-ttu-id="e7d64-138">Diese Methode sollte stets eindeutig den richtigen Zeitpunkt darstellen, bevor und nachdem dieser gespeichert und wiederhergestellt wurde, vorausgesetzt, dass die Implementierung des kombinierten Objekts aus Datum und Uhrzeit sowie Zeitzone sicherstellt, dass der Datumswert mit dem Zeitzonenwert synchron ist.</span><span class="sxs-lookup"><span data-stu-id="e7d64-138">This technique should always unambiguously reflect the correct point of time both before and after it is saved and restored, provided that the implementation of the combined date and time and time zone object does not allow the date value to become out of sync with the time zone value.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="e7d64-139">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e7d64-139">Compile the code</span></span>

<span data-ttu-id="e7d64-140">Diese Beispiele erfordern Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e7d64-140">These examples require that:</span></span>

- <span data-ttu-id="e7d64-141">Importieren der folgenden Namespaces mithilfe von `using`-Direktiven (C#) oder `Imports`-Anweisungen (Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="e7d64-141">The following namespaces be imported with C# `using` directives or Visual Basic `Imports` statements:</span></span>

  - <span data-ttu-id="e7d64-142"><xref:System> (nur C#)</span><span class="sxs-lookup"><span data-stu-id="e7d64-142"><xref:System> (C# only)</span></span>

  - <xref:System.Globalization?displayProperty=nameWithType>

  - <xref:System.IO?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>

- <span data-ttu-id="e7d64-143">Jedes Codebeispiel, ausgenommen der `DateInTimeZone`-Klasse, muss in eine Klasse oder ein Visual Basic-Modul eingefügt, in Methoden umschlossen und über die `Main`-Methode aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e7d64-143">Each code example, other than the `DateInTimeZone` class, be included in a class or Visual Basic module, wrapped in methods, and called from the `Main` method.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7d64-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7d64-144">See also</span></span>

- [<span data-ttu-id="e7d64-145">Auswählen zwischen „DateTime“, „DateTimeOffset“, „TimeSpan“ und „TimeZoneInfo“</span><span class="sxs-lookup"><span data-stu-id="e7d64-145">Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo</span></span>](../datetime/choosing-between-datetime.md)
- [<span data-ttu-id="e7d64-146">Standard-Formatzeichenfolgen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="e7d64-146">Standard Date and Time Format Strings</span></span>](standard-date-and-time-format-strings.md)
