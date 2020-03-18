---
title: Protobuf skalare Datentypen - gRPC für WCF-Entwickler
description: Erfahren Sie mehr über die grundlegenden und bekannten Datentypen, die Protobuf und gRPC in .NET Core unterstützen.
ms.date: 09/09/2019
ms.openlocfilehash: a40f51fa32ddb97ba417ec01f31e1f0187f0d544
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148126"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="1bace-103">Skalare Datentypen für Protobuf</span><span class="sxs-lookup"><span data-stu-id="1bace-103">Protobuf scalar data types</span></span>

<span data-ttu-id="1bace-104">Der Protokollpuffer (Protobuf) unterstützt eine Reihe systemeigener skalarer Werttypen.</span><span class="sxs-lookup"><span data-stu-id="1bace-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="1bace-105">In der folgenden Tabelle sind sie alle mit dem entsprechenden Typ "C" aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="1bace-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="1bace-106">Protobuf-Typ</span><span class="sxs-lookup"><span data-stu-id="1bace-106">Protobuf type</span></span> | <span data-ttu-id="1bace-107">C#-Typ</span><span class="sxs-lookup"><span data-stu-id="1bace-107">C# type</span></span>      | <span data-ttu-id="1bace-108">Notizen</span><span class="sxs-lookup"><span data-stu-id="1bace-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="1bace-109">1</span><span class="sxs-lookup"><span data-stu-id="1bace-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="1bace-110">1</span><span class="sxs-lookup"><span data-stu-id="1bace-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="1bace-111">1</span><span class="sxs-lookup"><span data-stu-id="1bace-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="1bace-112">1</span><span class="sxs-lookup"><span data-stu-id="1bace-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="1bace-113">2</span><span class="sxs-lookup"><span data-stu-id="1bace-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="1bace-114">2</span><span class="sxs-lookup"><span data-stu-id="1bace-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="1bace-115">2</span><span class="sxs-lookup"><span data-stu-id="1bace-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="1bace-116">2</span><span class="sxs-lookup"><span data-stu-id="1bace-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="1bace-117">3</span><span class="sxs-lookup"><span data-stu-id="1bace-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="1bace-118">4</span><span class="sxs-lookup"><span data-stu-id="1bace-118">4</span></span>     |

<span data-ttu-id="1bace-119">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="1bace-119">Notes:</span></span>

1. <span data-ttu-id="1bace-120">Die Standardcodierung `int32` für `int64` und ist ineffizient, wenn Sie mit signierten Werten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="1bace-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="1bace-121">Wenn Ihr Feld wahrscheinlich negative Zahlen `sint32` `sint64` enthält, verwenden Sie oder stattdessen.</span><span class="sxs-lookup"><span data-stu-id="1bace-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="1bace-122">Diese Typen werden dem `int` `long` C- bzw. den Typen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1bace-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="1bace-123">Die `fixed` Felder verwenden immer die gleiche Anzahl von Bytes, unabhängig vom Wert.</span><span class="sxs-lookup"><span data-stu-id="1bace-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="1bace-124">Dieses Verhalten beschleunigt die Serialisierung und Deserialisierung für größere Werte.</span><span class="sxs-lookup"><span data-stu-id="1bace-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="1bace-125">Protobuf-Zeichenfolgen sind UTF-8 (oder 7-Bit ASCII) codiert.</span><span class="sxs-lookup"><span data-stu-id="1bace-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="1bace-126">Die codierte Länge darf nicht größer als 2<sup>32</sup>sein.</span><span class="sxs-lookup"><span data-stu-id="1bace-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="1bace-127">Die Protobuf-Laufzeit `ByteString` stellt einen Typ bereit, `byte[]` der einfach den und von C-Arrays zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="1bace-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="1bace-128">Andere Primitivetypen von .NET</span><span class="sxs-lookup"><span data-stu-id="1bace-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="1bace-129">Datums- und Zeitangaben</span><span class="sxs-lookup"><span data-stu-id="1bace-129">Dates and times</span></span>

<span data-ttu-id="1bace-130">Die systemeigenen Skalartypen bieten keine Datums- <xref:System.DateTimeOffset>und Uhrzeitwerte, <xref:System.DateTime>die <xref:System.TimeSpan>den C-, - und .</span><span class="sxs-lookup"><span data-stu-id="1bace-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="1bace-131">Sie können diese Typen angeben, indem Sie einige der Google-Erweiterungen "Well Known Types" verwenden.</span><span class="sxs-lookup"><span data-stu-id="1bace-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="1bace-132">Diese Erweiterungen bieten Codegenerierungs- und Laufzeitunterstützung für komplexe Feldtypen auf allen unterstützten Plattformen.</span><span class="sxs-lookup"><span data-stu-id="1bace-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span>

<span data-ttu-id="1bace-133">Die folgende Tabelle zeigt die Datums- und Uhrzeittypen:</span><span class="sxs-lookup"><span data-stu-id="1bace-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="1bace-134">C#-Typ</span><span class="sxs-lookup"><span data-stu-id="1bace-134">C# type</span></span> | <span data-ttu-id="1bace-135">Protobuf bekannter Typ</span><span class="sxs-lookup"><span data-stu-id="1bace-135">Protobuf well-known type</span></span> |
| ------- | ------------------------ |
| `DateTimeOffset` | `google.protobuf.Timestamp` |
| `DateTime` | `google.protobuf.Timestamp` |
| `TimeSpan` | `google.protobuf.Duration` |

```protobuf  
syntax = "proto3"

import "google/protobuf/duration.proto";  
import "google/protobuf/timestamp.proto";

message Meeting {

    string subject = 1;
    google.protobuf.Timestamp time = 2;
    google.protobuf.Duration duration = 3;

}  
```

<span data-ttu-id="1bace-136">Die generierten Eigenschaften in der C-Klasse sind nicht die .NET-Datums- und -Uhrzeittypen.</span><span class="sxs-lookup"><span data-stu-id="1bace-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="1bace-137">Die Eigenschaften `Timestamp` verwenden `Duration` die `Google.Protobuf.WellKnownTypes` und-Klassen im Namespace.</span><span class="sxs-lookup"><span data-stu-id="1bace-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="1bace-138">Diese Klassen stellen Methoden zum `DateTimeOffset`Konvertieren `DateTime`in `TimeSpan`und von , und bereit.</span><span class="sxs-lookup"><span data-stu-id="1bace-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

```csharp
// Create Timestamp and Duration from .NET DateTimeOffset and TimeSpan
var meeting = new Meeting
{
    Time = Timestamp.FromDateTimeOffset(meetingTime), // also FromDateTime()
    Duration = Duration.FromTimeSpan(meetingLength)
};

// Convert Timestamp and Duration to .NET DateTimeOffset and TimeSpan
DateTimeOffset time = meeting.Time.ToDateTimeOffset();
TimeSpan? duration = meeting.Duration?.ToTimeSpan();
```

> [!NOTE]
> <span data-ttu-id="1bace-139">Der `Timestamp` Typ funktioniert mit UTC-Zeiten.</span><span class="sxs-lookup"><span data-stu-id="1bace-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="1bace-140">`DateTimeOffset`Werte haben immer einen Offset `DateTime.Kind` von Null, und die Eigenschaft ist immer `DateTimeKind.Utc`.</span><span class="sxs-lookup"><span data-stu-id="1bace-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="1bace-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="1bace-141">System.Guid</span></span>

<span data-ttu-id="1bace-142">Protobuf unterstützt den <xref:System.Guid> Typ nicht direkt, der auf `UUID` anderen Plattformen bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="1bace-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="1bace-143">Es gibt keinen bekannten Typ dafür.</span><span class="sxs-lookup"><span data-stu-id="1bace-143">There's no well-known type for it.</span></span>

<span data-ttu-id="1bace-144">Der beste Ansatz `Guid` besteht darin, Werte `string` als `8-4-4-4-12` Feld zu behandeln, indem `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`sie das standardmäßige hexadezimale Format (z. B. ) verwenden.</span><span class="sxs-lookup"><span data-stu-id="1bace-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="1bace-145">Alle Sprachen und Plattformen können dieses Format analysieren.</span><span class="sxs-lookup"><span data-stu-id="1bace-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="1bace-146">Verwenden Sie kein `bytes` Feld `Guid` für Werte.</span><span class="sxs-lookup"><span data-stu-id="1bace-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="1bace-147">Probleme mit *der Endianität* ([Wikipedia-Definition](https://en.wikipedia.org/wiki/Endianness)) können zu unregelmäßigem Verhalten führen, wenn Protobuf mit anderen Plattformen wie Java interagiert.</span><span class="sxs-lookup"><span data-stu-id="1bace-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="1bace-148">Auf NULL festlegbare Typen</span><span class="sxs-lookup"><span data-stu-id="1bace-148">Nullable types</span></span>

<span data-ttu-id="1bace-149">Die Protobuf-Codegenerierung für C- verwendet `int` die `int32`systemeigenen Typen, z. B. für .</span><span class="sxs-lookup"><span data-stu-id="1bace-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="1bace-150">Die Werte sind also immer enthalten und können nicht null sein.</span><span class="sxs-lookup"><span data-stu-id="1bace-150">So the values are always included and can't be null.</span></span>

<span data-ttu-id="1bace-151">Für Werte, die explizite `int?` NULL erfordern, z. B. die Verwendung in Ihrem C-Code, enthalten die "Well Known Types" von Protobufs Wrapper, die in nullierbare C-Typen kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="1bace-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="1bace-152">Um sie zu `wrappers.proto` verwenden, importieren Sie in Ihre `.proto` Datei wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1bace-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="1bace-153">Protobuf verwendet die `T?` einfache (z. B. `int?`) für die generierte Nachrichteneigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1bace-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="1bace-154">Die folgende Tabelle zeigt die vollständige Liste der Wrappertypen mit dem entsprechenden Typ "C":</span><span class="sxs-lookup"><span data-stu-id="1bace-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="1bace-155">C#-Typ</span><span class="sxs-lookup"><span data-stu-id="1bace-155">C# type</span></span>   | <span data-ttu-id="1bace-156">Bekannter Typ-Wrapper</span><span class="sxs-lookup"><span data-stu-id="1bace-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="1bace-157">Die bekannten `Timestamp` Typen, `Duration` die in .NET als Klassen dargestellt werden, sodass keine nullierbare Version erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1bace-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version.</span></span> <span data-ttu-id="1bace-158">Es ist jedoch wichtig, beim Konvertieren in `DateTimeOffset` oder `TimeSpan`auf NULL nach Eigenschaften dieser Typen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="1bace-158">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="1bace-159">Dezimalstellen</span><span class="sxs-lookup"><span data-stu-id="1bace-159">Decimals</span></span>

<span data-ttu-id="1bace-160">Protobuf unterstützt nicht nativ den `decimal` .NET-Typ, nur `double` und `float`.</span><span class="sxs-lookup"><span data-stu-id="1bace-160">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="1bace-161">Im Protobuf-Projekt wird derzeit über die Möglichkeit diskutiert, den bekannten Typen einen Standardtyp `Decimal` hinzuzufügen, mit Plattformunterstützung für Sprachen und Frameworks, die ihn unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1bace-161">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="1bace-162">Es wurde noch nichts umgesetzt.</span><span class="sxs-lookup"><span data-stu-id="1bace-162">Nothing has been implemented yet.</span></span>

<span data-ttu-id="1bace-163">Es ist möglich, eine Nachrichtendefinition `decimal` zu erstellen, um den Typ darzustellen, der für die sichere Serialisierung zwischen .NET-Clients und Servern verwendet werden würde.</span><span class="sxs-lookup"><span data-stu-id="1bace-163">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="1bace-164">Aber Entwickler auf anderen Plattformen müssten das verwendete Format verstehen und ihre eigene Handhabung dafür implementieren.</span><span class="sxs-lookup"><span data-stu-id="1bace-164">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="1bace-165">Erstellen eines benutzerdefinierten Dezimaltyps für Protobuf</span><span class="sxs-lookup"><span data-stu-id="1bace-165">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="1bace-166">Eine einfache Implementierung kann dem `Money` nicht standardmäßigen Typ ähneln, `currency` den einige Google-APIs ohne das Feld verwenden.</span><span class="sxs-lookup"><span data-stu-id="1bace-166">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

```protobuf
package CustomTypes;

// Example: 12345.6789 -> { units = 12345, nanos = 678900000 }
message Decimal {

    // Whole units part of the amount
    int64 units = 1;

    // Nano units of the amount (10^-9)
    // Must be same sign as units
    sfixed32 nanos = 2;
}
```

<span data-ttu-id="1bace-167">Das `nanos` Feld stellt `0.999_999_999` `-0.999_999_999`Werte von bis dar.</span><span class="sxs-lookup"><span data-stu-id="1bace-167">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="1bace-168">Der `decimal` Wert `1.5m` wird z. `{ units = 1, nanos = 500_000_000 }`B. als dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1bace-168">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="1bace-169">Aus diesem `nanos` Grund verwendet das `sfixed32` Feld in diesem Beispiel `int32` den Typ, der effizienter codiert als bei größeren Werten.</span><span class="sxs-lookup"><span data-stu-id="1bace-169">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="1bace-170">Wenn `units` das Feld negativ `nanos` ist, sollte das Feld ebenfalls negativ sein.</span><span class="sxs-lookup"><span data-stu-id="1bace-170">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="1bace-171">Es gibt mehrere andere Algorithmen `decimal` für die Codierung von Werten als Bytezeichenfolgen, aber diese Nachricht ist einfacher zu verstehen als jeder andere.</span><span class="sxs-lookup"><span data-stu-id="1bace-171">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="1bace-172">Die Werte werden nicht durch Endianität auf verschiedenen Plattformen beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="1bace-172">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="1bace-173">Die Konvertierung zwischen diesem `decimal` Typ und dem BCL-Typ kann wie folgt in C- implementiert werden:</span><span class="sxs-lookup"><span data-stu-id="1bace-173">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

```csharp
namespace CustomTypes
{
    public partial class GrpcDecimal
    {
        private const decimal NanoFactor = 1_000_000_000;
        public GrpcDecimal(long units, int nanos)
        {
            Units = units;
            Nanos = nanos;
        }

        public long Units { get; }
        public int Nanos { get; }

        public static implicit operator decimal(CustomTypes.Decimal grpcDecimal)
        {
            return grpcDecimal.Units + grpcDecimal.Nanos / NanoFactor;
        }

        public static implicit operator CustomTypes.Decimal(decimal value)
        {
            var units = decimal.ToInt64(value);
            var nanos = decimal.ToInt32((value - units) * NanoFactor);
            return new CustomTypes.Decimal(units, nanos);
        }
    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="1bace-174">Wenn Sie benutzerdefinierte Nachrichtentypen *must* wie diesen verwenden, `.proto`müssen Sie diese mit Kommentaren in dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="1bace-174">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="1bace-175">Andere Entwickler können dann die Konvertierung in und aus dem entsprechenden Typ in ihrer eigenen Sprache oder ihrem Framework implementieren.</span><span class="sxs-lookup"><span data-stu-id="1bace-175">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1bace-176">[VorherigeS](protobuf-messages.md)
>[Weiter](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="1bace-176">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
