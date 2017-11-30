---
title: 'Gewusst wie: Roundtrip-Datums- und -Uhrzeitwerte'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 515a29e279cfa8fc100e0612fc19df7abc6a3b36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-trip-date-and-time-values"></a><span data-ttu-id="d65a7-102">Gewusst wie: Roundtrip-Datums- und -Uhrzeitwerte</span><span class="sxs-lookup"><span data-stu-id="d65a7-102">How to: Round-trip Date and Time Values</span></span>
<span data-ttu-id="d65a7-103">In vielen Anwendungen soll ein Datums- und Uhrzeitwert einen bestimmten Zeitpunkt eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d65a7-103">In many applications, a date and time value is intended to unambiguously identify a single point in time.</span></span> <span data-ttu-id="d65a7-104">In diesem Thema wird gezeigt, wie zum Speichern und Wiederherstellen einer <xref:System.DateTime> Wert, einen <xref:System.DateTimeOffset> Wert und einen Wert für Datum und Uhrzeit mit Time zone Informationen, damit die wiederhergestellte Wert zur gleiche Zeit wie der gespeicherte Wert identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d65a7-104">This topic shows how to save and restore a <xref:System.DateTime> value, a <xref:System.DateTimeOffset> value, and a date and time value with time zone information so that the restored value identifies the same time as the saved value.</span></span>  
  
### <a name="to-round-trip-a-datetime-value"></a><span data-ttu-id="d65a7-105">So führen Sie einen Roundtrip für einen DateTime-Wert durch</span><span class="sxs-lookup"><span data-stu-id="d65a7-105">To round-trip a DateTime value</span></span>  
  
1.  <span data-ttu-id="d65a7-106">Konvertieren der <xref:System.DateTime> Wert in seine Zeichenfolgendarstellung durch Aufrufen der <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> Methode mit dem Formatbezeichner "o".</span><span class="sxs-lookup"><span data-stu-id="d65a7-106">Convert the <xref:System.DateTime> value to its string representation by calling the <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>  
  
2.  <span data-ttu-id="d65a7-107">Speichern Sie die Zeichenfolgendarstellung der <xref:System.DateTime> Wert in eine Datei, oder es über einen Prozess, Anwendungsdomäne oder Computergrenze übergeben.</span><span class="sxs-lookup"><span data-stu-id="d65a7-107">Save the string representation of the <xref:System.DateTime> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>  
  
3.  <span data-ttu-id="d65a7-108">Rufen Sie die Zeichenfolge, die stellt die <xref:System.DateTime> Wert.</span><span class="sxs-lookup"><span data-stu-id="d65a7-108">Retrieve the string that represents the <xref:System.DateTime> value.</span></span>  
  
4.  <span data-ttu-id="d65a7-109">Rufen Sie die <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> Methode, und übergeben <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> als Wert für die `styles` Parameter.</span><span class="sxs-lookup"><span data-stu-id="d65a7-109">Call the <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>  
  
 <span data-ttu-id="d65a7-110">Im folgende Beispiel wird veranschaulicht, wie ein Roundtrip eine <xref:System.DateTime> Wert.</span><span class="sxs-lookup"><span data-stu-id="d65a7-110">The following example illustrates how to round-trip a <xref:System.DateTime> value.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 <span data-ttu-id="d65a7-111">Bei der Round-Tripping ein <xref:System.DateTime> Wert dieses Verfahren erfolgreich die Zeit für alle Zeitangaben von lokaler und universeller beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d65a7-111">When round-tripping a <xref:System.DateTime> value, this technique successfully preserves the time for all local and universal times.</span></span> <span data-ttu-id="d65a7-112">Angenommen, eine lokale <xref:System.DateTime> Wert wird auf einem System in den USA gespeichert. Pacific Standard Time gespeichert und auf einem System in der US-Zeitzone Central Standard Time wiederhergestellt wird, liegen das wiederhergestellte Datum und die Uhrzeit zwei Stunden hinter der ursprünglichen Zeit, was dem Zeitunterschied zwischen den beiden Zeitzonen entspricht.</span><span class="sxs-lookup"><span data-stu-id="d65a7-112">For example, if a local <xref:System.DateTime> value is saved on a system in the U.S. Pacific Standard Time zone and is restored on a system in the U.S. Central Standard Time zone, the restored date and time will be two hours later than the original time, which reflects the time difference between the two time zones.</span></span> <span data-ttu-id="d65a7-113">Dieses Verfahren ist für nicht spezifizierte Zeiten jedoch nicht notwendigerweise genau.</span><span class="sxs-lookup"><span data-stu-id="d65a7-113">However, this technique is not necessarily accurate for unspecified times.</span></span> <span data-ttu-id="d65a7-114">Alle <xref:System.DateTime> Werte, deren <xref:System.DateTime.Kind%2A> Eigenschaft <xref:System.DateTimeKind.Unspecified> behandelt, als ob sie lokalen Zeiten sind.</span><span class="sxs-lookup"><span data-stu-id="d65a7-114">All <xref:System.DateTime> values whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified> are treated as if they are local times.</span></span> <span data-ttu-id="d65a7-115">Wenn dies nicht der Fall ist die <xref:System.DateTime> wird nicht erfolgreich identifizieren die richtigen Zeitpunkts.</span><span class="sxs-lookup"><span data-stu-id="d65a7-115">If this is not the case, the <xref:System.DateTime> will not successfully identify the correct point in time.</span></span> <span data-ttu-id="d65a7-116">Die Umgehung für diese Einschränkung besteht darin, einen Datums- und Zeitwert für den Speicher- und Wiederherstellungsvorgang eng an die entsprechende Zeitzone zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="d65a7-116">The workaround for this limitation is to tightly couple a date and time value with its time zone for the save and restore operation.</span></span>  
  
### <a name="to-round-trip-a-datetimeoffset-value"></a><span data-ttu-id="d65a7-117">So führen Sie einen Roundtrip für einen DateTimeOffset-Wert durch</span><span class="sxs-lookup"><span data-stu-id="d65a7-117">To round-trip a DateTimeOffset value</span></span>  
  
1.  <span data-ttu-id="d65a7-118">Konvertieren der <xref:System.DateTimeOffset> Wert in seine Zeichenfolgendarstellung durch Aufrufen der <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> Methode mit dem Formatbezeichner "o".</span><span class="sxs-lookup"><span data-stu-id="d65a7-118">Convert the <xref:System.DateTimeOffset> value to its string representation by calling the <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>  
  
2.  <span data-ttu-id="d65a7-119">Speichern Sie die Zeichenfolgendarstellung der <xref:System.DateTimeOffset> Wert in eine Datei, oder es über einen Prozess, Anwendungsdomäne oder Computergrenze übergeben.</span><span class="sxs-lookup"><span data-stu-id="d65a7-119">Save the string representation of the <xref:System.DateTimeOffset> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>  
  
3.  <span data-ttu-id="d65a7-120">Rufen Sie die Zeichenfolge, die stellt die <xref:System.DateTimeOffset> Wert.</span><span class="sxs-lookup"><span data-stu-id="d65a7-120">Retrieve the string that represents the <xref:System.DateTimeOffset> value.</span></span>  
  
4.  <span data-ttu-id="d65a7-121">Rufen Sie die <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> Methode, und übergeben <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> als Wert für die `styles` Parameter.</span><span class="sxs-lookup"><span data-stu-id="d65a7-121">Call the <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>  
  
 <span data-ttu-id="d65a7-122">Im folgende Beispiel wird veranschaulicht, wie ein Roundtrip eine <xref:System.DateTimeOffset> Wert.</span><span class="sxs-lookup"><span data-stu-id="d65a7-122">The following example illustrates how to round-trip a <xref:System.DateTimeOffset> value.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 <span data-ttu-id="d65a7-123">Diese Technik ist immer eindeutig identifiziert einen <xref:System.DateTimeOffset> Wert als einen einzigen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="d65a7-123">This technique always unambiguously identifies a <xref:System.DateTimeOffset> value as a single point in time.</span></span> <span data-ttu-id="d65a7-124">Der Wert kann dann in die koordinierte Weltzeit (UTC) konvertiert werden, durch Aufrufen der <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> -Methode, oder er kann in die Zeit in einer bestimmten Zeitzone konvertiert werden, durch Aufrufen der <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> oder <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="d65a7-124">The value can then be converted to Coordinated Universal Time (UTC) by calling the <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> method, or it can be converted to the time in a particular time zone by calling the <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> or <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d65a7-125">Die wichtigste Einschränkung für diese Technik ist dieses Datum und die Uhrzeit arithmetischen, beim Ausführen auf einer <xref:System.DateTimeOffset> Wert, der die Zeit in einer bestimmten Zeitzone darstellt, möglicherweise nicht präzise Ergebnisse für diese Zeitzone erstellt.</span><span class="sxs-lookup"><span data-stu-id="d65a7-125">The major limitation of this technique is that date and time arithmetic, when performed on a <xref:System.DateTimeOffset> value that represents the time in a particular time zone, may not produce accurate results for that time zone.</span></span> <span data-ttu-id="d65a7-126">Grund hierfür ist, wenn ein <xref:System.DateTimeOffset> Wert instanziiert wird, wird es seiner Zeitzone aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d65a7-126">This is because when a <xref:System.DateTimeOffset> value is instantiated, it is disassociated from its time zone.</span></span> <span data-ttu-id="d65a7-127">Daher können die Anpassungsregeln für diese Zeitzone bei Datums- und Uhrzeitberechnungen nicht mehr angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d65a7-127">Therefore, that time zone's adjustment rules can no longer be applied when you perform date and time calculations.</span></span> <span data-ttu-id="d65a7-128">Sie können dieses Problem umgehen, indem Sie einen benutzerdefinierten Typ definieren, der sowohl einen Datums- und Uhrzeitwert als auch die dazugehörige Zeitzone enthält.</span><span class="sxs-lookup"><span data-stu-id="d65a7-128">You can work around this problem by defining a custom type that includes both a date and time value and its accompanying time zone.</span></span>  
  
### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a><span data-ttu-id="d65a7-129">Für den roundtripvorgang einen Wert für Datum und Uhrzeit mit seiner Zeitzone</span><span class="sxs-lookup"><span data-stu-id="d65a7-129">To round-trip a date and time value with its time zone</span></span>  
  
1.  <span data-ttu-id="d65a7-130">Definieren Sie eine Klasse oder eine Struktur mit zwei Feldern.</span><span class="sxs-lookup"><span data-stu-id="d65a7-130">Define a class or a structure with two fields.</span></span> <span data-ttu-id="d65a7-131">Das erste Feld handelt es sich um eine <xref:System.DateTime> oder ein <xref:System.DateTimeOffset> Objekt und das zweite ist ein <xref:System.TimeZoneInfo> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d65a7-131">The first field is either a <xref:System.DateTime> or a <xref:System.DateTimeOffset> object, and the second is a <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="d65a7-132">Im folgende Beispiel wird eine einfache Version eines solchen Typs.</span><span class="sxs-lookup"><span data-stu-id="d65a7-132">The following example is a simple version of such a type.</span></span>  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  <span data-ttu-id="d65a7-133">Markieren Sie die Klasse mit dem <xref:System.SerializableAttribute> Attribut.</span><span class="sxs-lookup"><span data-stu-id="d65a7-133">Mark the class with the <xref:System.SerializableAttribute> attribute.</span></span>  
  
3.  <span data-ttu-id="d65a7-134">Serialisiert das Objekt mit der <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="d65a7-134">Serialize the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> method.</span></span>  
  
4.  <span data-ttu-id="d65a7-135">Wiederherstellen, das mit der <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="d65a7-135">Restore the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> method.</span></span>  
  
5.  <span data-ttu-id="d65a7-136">Umgewandelt (in c#) oder konvertieren Sie das deserialisierte Objekt (in Visual Basic) aus, um ein Objekt des entsprechenden Typs.</span><span class="sxs-lookup"><span data-stu-id="d65a7-136">Cast (in C#) or convert (in Visual Basic) the deserialized object to an object of the appropriate type.</span></span>  
  
 <span data-ttu-id="d65a7-137">Im folgende Beispiel wird veranschaulicht, wie für den roundtripvorgang ein Objekt, das sowohl Datum und Uhrzeit und Zeitzone Informationen speichert.</span><span class="sxs-lookup"><span data-stu-id="d65a7-137">The following example illustrates how to round-trip an object that stores both date and time and time zone information.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 <span data-ttu-id="d65a7-138">Diese Technik sollte immer eindeutig richtigen Zeitpunkt Standardzeitintervall sowohl vor und nach dem er gespeichert und wiederhergestellt, die Implementierung des kombinierten Datum und Uhrzeit und Zeitzone Objekts nicht den Date-Wert mit synchron sind zulässig, entsprechen die der Wert der Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="d65a7-138">This technique should always unambiguously reflect the correct point of time both before and after it is saved and restored, provided that the implementation of the combined date and time and time zone object does not allow the date value to become out of sync with the time zone value.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d65a7-139">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d65a7-139">Compiling the Code</span></span>  
 <span data-ttu-id="d65a7-140">Diese Beispiele erfordern Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d65a7-140">These examples require:</span></span>  
  
-   <span data-ttu-id="d65a7-141">Die folgenden Namespaces importiert werden, mit den C#- `using` Anweisungen oder [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="d65a7-141">That the following namespaces be imported with C# `using` statements or [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` statements:</span></span>  
  
    -   <span data-ttu-id="d65a7-142"><xref:System>(Nur c#).</span><span class="sxs-lookup"><span data-stu-id="d65a7-142"><xref:System> (C# only).</span></span>  
  
    -   <span data-ttu-id="d65a7-143"><xref:System.Globalization?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d65a7-143"><xref:System.Globalization?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="d65a7-144"><xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d65a7-144"><xref:System.IO?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="d65a7-145"><xref:System.Runtime.Serialization?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d65a7-145"><xref:System.Runtime.Serialization?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="d65a7-146"><xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d65a7-146"><xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="d65a7-147">Ein Verweis auf "System.Core.dll".</span><span class="sxs-lookup"><span data-stu-id="d65a7-147">A reference to System.Core.dll.</span></span>  
  
-   <span data-ttu-id="d65a7-148">Jedes Codebeispiel, außer die `DateInTimeZone` -Klasse, in einer Klasse oder Visual Basic-Modul enthalten, mit Methoden umschlossen und aus aufgerufen werden sollte die `Main` Methode.</span><span class="sxs-lookup"><span data-stu-id="d65a7-148">Each code example, other than the `DateInTimeZone` class, should be included in a class or Visual Basic module, wrapped in methods, and called from the `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d65a7-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d65a7-149">See Also</span></span>  
 [<span data-ttu-id="d65a7-150">Durchführen von Formatierungsvorgängen</span><span class="sxs-lookup"><span data-stu-id="d65a7-150">Performing Formatting Operations</span></span>](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [<span data-ttu-id="d65a7-151">Auswählen zwischen „DateTime“, „DateTimeOffset“, „TimeSpan“ und „TimeZoneInfo“</span><span class="sxs-lookup"><span data-stu-id="d65a7-151">Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo</span></span>](../../../docs/standard/datetime/choosing-between-datetime.md)  
 [<span data-ttu-id="d65a7-152">Standard Date and Time Format Strings</span><span class="sxs-lookup"><span data-stu-id="d65a7-152">Standard Date and Time Format Strings</span></span>](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
