---
title: 'Protobuf-skalare Datentypen: GrpC für WCF-Entwickler'
description: Erfahren Sie mehr über die grundlegenden und bekannten Datentypen, die protobuf und GrpC in .net Core unterstützen.
ms.date: 09/09/2019
ms.openlocfilehash: f5215550a6a2d54dfe2e859c574a34f641fdb68d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543156"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="219be-103">Skalare Datentypen für Protobuf</span><span class="sxs-lookup"><span data-stu-id="219be-103">Protobuf scalar data types</span></span>

<span data-ttu-id="219be-104">Der Protokollpuffer (protobuf) unterstützt einen Bereich von systemeigenen skalaren Werttypen.</span><span class="sxs-lookup"><span data-stu-id="219be-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="219be-105">In der folgenden Tabelle sind alle Elemente mit dem C# entsprechenden Typ aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="219be-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="219be-106">Protobuf-Typ</span><span class="sxs-lookup"><span data-stu-id="219be-106">Protobuf type</span></span> | <span data-ttu-id="219be-107">C#-Typ</span><span class="sxs-lookup"><span data-stu-id="219be-107">C# type</span></span>      | <span data-ttu-id="219be-108">Notizen</span><span class="sxs-lookup"><span data-stu-id="219be-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="219be-109">1</span><span class="sxs-lookup"><span data-stu-id="219be-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="219be-110">1</span><span class="sxs-lookup"><span data-stu-id="219be-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="219be-111">1</span><span class="sxs-lookup"><span data-stu-id="219be-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="219be-112">1</span><span class="sxs-lookup"><span data-stu-id="219be-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="219be-113">2</span><span class="sxs-lookup"><span data-stu-id="219be-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="219be-114">2</span><span class="sxs-lookup"><span data-stu-id="219be-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="219be-115">2</span><span class="sxs-lookup"><span data-stu-id="219be-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="219be-116">2</span><span class="sxs-lookup"><span data-stu-id="219be-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="219be-117">3</span><span class="sxs-lookup"><span data-stu-id="219be-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="219be-118">4</span><span class="sxs-lookup"><span data-stu-id="219be-118">4</span></span>     |

<span data-ttu-id="219be-119">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="219be-119">Notes:</span></span>

1. <span data-ttu-id="219be-120">Die Standard Codierung für `int32` und `int64` ist ineffizient, wenn Sie mit signierten Werten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="219be-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="219be-121">Wenn das Feld wahrscheinlich negative Zahlen enthält, verwenden Sie stattdessen `sint32` oder `sint64`.</span><span class="sxs-lookup"><span data-stu-id="219be-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="219be-122">Diese Typen werden den C# `int`-und `long` Typen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="219be-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="219be-123">Die `fixed` Felder verwenden immer dieselbe Anzahl von Bytes, unabhängig davon, was der Wert ist.</span><span class="sxs-lookup"><span data-stu-id="219be-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="219be-124">Dieses Verhalten macht die Serialisierung und Deserialisierung bei größeren Werten schneller.</span><span class="sxs-lookup"><span data-stu-id="219be-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="219be-125">Protobuf-Zeichen folgen sind UTF-8-codiert (oder 7-Bit-ASCII).</span><span class="sxs-lookup"><span data-stu-id="219be-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="219be-126">Die codierte Länge darf nicht größer als 2<sup>32</sup>sein.</span><span class="sxs-lookup"><span data-stu-id="219be-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="219be-127">Die protobuf-Laufzeit stellt einen `ByteString` Typ bereit, der problemlos C# `byte[]` Arrays zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="219be-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="219be-128">Andere .net-primitive Typen</span><span class="sxs-lookup"><span data-stu-id="219be-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="219be-129">Datums- und Zeitangaben</span><span class="sxs-lookup"><span data-stu-id="219be-129">Dates and times</span></span>

<span data-ttu-id="219be-130">Die System C#eigenen skalaren Typen bieten keine Datums-und Uhrzeitwerte, die den <xref:System.DateTimeOffset>, <xref:System.DateTime>und <xref:System.TimeSpan>entsprechen.</span><span class="sxs-lookup"><span data-stu-id="219be-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="219be-131">Sie können diese Typen mithilfe einiger der "Well Known Types"-Erweiterungen von Google angeben.</span><span class="sxs-lookup"><span data-stu-id="219be-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="219be-132">Diese Erweiterungen bieten Codegenerierung und Laufzeitunterstützung für komplexe Feldtypen auf den unterstützten Plattformen.</span><span class="sxs-lookup"><span data-stu-id="219be-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span> 

<span data-ttu-id="219be-133">In der folgenden Tabelle werden die Datums-und Uhrzeit Typen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="219be-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="219be-134">C#-Typ</span><span class="sxs-lookup"><span data-stu-id="219be-134">C# type</span></span> | <span data-ttu-id="219be-135">Typ der protobuf-bekannten Typen</span><span class="sxs-lookup"><span data-stu-id="219be-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="219be-136">Die generierten Eigenschaften in der C# -Klasse sind nicht die .net-Datums-und-Uhrzeit Typen.</span><span class="sxs-lookup"><span data-stu-id="219be-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="219be-137">Die Eigenschaften verwenden die Klassen `Timestamp` und `Duration` im `Google.Protobuf.WellKnownTypes` Namespace.</span><span class="sxs-lookup"><span data-stu-id="219be-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="219be-138">Diese Klassen stellen Methoden zum Wechseln in und aus `DateTimeOffset`, `DateTime`und `TimeSpan`bereit.</span><span class="sxs-lookup"><span data-stu-id="219be-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="219be-139">Der `Timestamp`-Typ funktioniert mit UTC-Zeiten.</span><span class="sxs-lookup"><span data-stu-id="219be-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="219be-140">`DateTimeOffset` Werte haben immer einen Offset von NULL, und die `DateTime.Kind`-Eigenschaft ist immer `DateTimeKind.Utc`.</span><span class="sxs-lookup"><span data-stu-id="219be-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="219be-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="219be-141">System.Guid</span></span>

<span data-ttu-id="219be-142">Protobuf unterstützt den <xref:System.Guid> Typ, der als `UUID` auf anderen Plattformen bezeichnet wird, nicht direkt.</span><span class="sxs-lookup"><span data-stu-id="219be-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="219be-143">Dafür gibt es keinen bekannten Typ.</span><span class="sxs-lookup"><span data-stu-id="219be-143">There's no well-known type for it.</span></span> 

<span data-ttu-id="219be-144">Die beste Vorgehensweise besteht darin, `Guid` Werte als `string` Feld zu behandeln, indem Sie das standardmäßige `8-4-4-4-12` Hexadezimal Format (z. b. `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`) verwenden.</span><span class="sxs-lookup"><span data-stu-id="219be-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="219be-145">Dieses Format kann von allen Sprachen und Plattformen analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="219be-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="219be-146">Verwenden Sie kein `bytes` Feld für `Guid` Werte.</span><span class="sxs-lookup"><span data-stu-id="219be-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="219be-147">Probleme mit *Byte Reihenfolge* ([Wikipedia-Definition](https://en.wikipedia.org/wiki/Endianness)) können zu einem erratischen Verhalten führen, wenn protobuf mit anderen Plattformen wie Java interagiert.</span><span class="sxs-lookup"><span data-stu-id="219be-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="219be-148">Auf NULL festlegbare Typen</span><span class="sxs-lookup"><span data-stu-id="219be-148">Nullable types</span></span>

<span data-ttu-id="219be-149">Die protobuf-Codegenerierung C# für verwendet die systemeigenen Typen, z. b. `int` für `int32`.</span><span class="sxs-lookup"><span data-stu-id="219be-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="219be-150">Daher sind die Werte immer enthalten und dürfen nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="219be-150">So the values are always included and can't be null.</span></span> 

<span data-ttu-id="219be-151">Für Werte, die explizite NULL-Werte erfordern, wie z. C# b. das Verwenden von `int?` in Ihrem Code, enthalten die "bekannten Typen" von protobuf C# Wrapper, die in Werte zulässt-Typen kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="219be-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="219be-152">Wenn Sie diese verwenden möchten, importieren Sie `wrappers.proto` wie folgt in Ihre `.proto` Datei:</span><span class="sxs-lookup"><span data-stu-id="219be-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="219be-153">Protobuf verwendet die einfache `T?` (z. b. `int?`) für die generierte Message-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="219be-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="219be-154">In der folgenden Tabelle wird die komplette Liste der Wrapper Typen mit dem C# entsprechenden Typ angezeigt:</span><span class="sxs-lookup"><span data-stu-id="219be-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="219be-155">C#-Typ</span><span class="sxs-lookup"><span data-stu-id="219be-155">C# type</span></span>   | <span data-ttu-id="219be-156">Bekannter Typwrapper</span><span class="sxs-lookup"><span data-stu-id="219be-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="219be-157">Die bekannten Typen `Timestamp` und `Duration` werden in .net als Klassen dargestellt, sodass keine Version vorhanden ist, die NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="219be-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version.</span></span> <span data-ttu-id="219be-158">Es ist jedoch wichtig, bei Eigenschaften dieser Typen auf NULL zu prüfen, wenn Sie zu `DateTimeOffset` oder `TimeSpan`wechseln.</span><span class="sxs-lookup"><span data-stu-id="219be-158">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="219be-159">Dezimalstellen</span><span class="sxs-lookup"><span data-stu-id="219be-159">Decimals</span></span>

<span data-ttu-id="219be-160">Protobuf unterstützt nicht den .net-`decimal` Typ, sondern nur `double` und `float`.</span><span class="sxs-lookup"><span data-stu-id="219be-160">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="219be-161">Im protobuf-Projekt gibt es eine fortlaufende Diskussion über die Möglichkeit, den bekannten Typen einen Standard `Decimal` Typ hinzuzufügen, mit Platt Form Unterstützung für Sprachen und Frameworks, die diese unterstützen.</span><span class="sxs-lookup"><span data-stu-id="219be-161">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="219be-162">Es wurde noch nichts implementiert.</span><span class="sxs-lookup"><span data-stu-id="219be-162">Nothing has been implemented yet.</span></span>

<span data-ttu-id="219be-163">Es ist möglich, eine Nachrichten Definition zu erstellen, die den `decimal` Typ darstellt, der für die sichere Serialisierung zwischen .NET-Clients und-Servern geeignet wäre.</span><span class="sxs-lookup"><span data-stu-id="219be-163">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="219be-164">Entwickler auf anderen Plattformen müssten jedoch das Format verstehen, das verwendet wird, und ihre eigene Behandlung für die Anwendung implementieren.</span><span class="sxs-lookup"><span data-stu-id="219be-164">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="219be-165">Erstellen eines benutzerdefinierten Dezimal Typs für protobuf</span><span class="sxs-lookup"><span data-stu-id="219be-165">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="219be-166">Eine einfache Implementierung ähnelt möglicherweise dem nicht standardmäßigen `Money`-Typ, den einige Google-APIs verwenden, ohne das `currency` Feld.</span><span class="sxs-lookup"><span data-stu-id="219be-166">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

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

<span data-ttu-id="219be-167">Das `nanos` Feld stellt Werte aus `0.999_999_999` zum `-0.999_999_999`dar.</span><span class="sxs-lookup"><span data-stu-id="219be-167">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="219be-168">Beispielsweise wird der `decimal` Wert `1.5m` als `{ units = 1, nanos = 500_000_000 }`dargestellt.</span><span class="sxs-lookup"><span data-stu-id="219be-168">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="219be-169">Aus diesem Grund verwendet das Feld "`nanos`" in diesem Beispiel den `sfixed32`-Typ, der effizienter als `int32` für größere Werte codiert.</span><span class="sxs-lookup"><span data-stu-id="219be-169">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="219be-170">Wenn das `units` Feld negativ ist, sollte das `nanos` Feld ebenfalls negativ sein.</span><span class="sxs-lookup"><span data-stu-id="219be-170">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="219be-171">Es gibt mehrere andere Algorithmen zum Codieren von `decimal` Werten als Byte Zeichenfolgen, diese Meldung ist jedoch leichter zu verstehen als alle.</span><span class="sxs-lookup"><span data-stu-id="219be-171">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="219be-172">Die Werte sind von der enumalität auf verschiedenen Plattformen nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="219be-172">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="219be-173">Die Konvertierung zwischen diesem Typ und der BCL-`decimal` Typs kann in C# wie folgt implementiert werden:</span><span class="sxs-lookup"><span data-stu-id="219be-173">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

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
> <span data-ttu-id="219be-174">Wenn Sie benutzerdefinierte Nachrichten Typen wie diese verwenden, *müssen* Sie diese mit Kommentaren in `.proto`dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="219be-174">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="219be-175">Andere Entwickler können dann eine Konvertierung in und aus dem entsprechenden Typ in ihrer eigenen Sprache oder in Ihrem eigenen Framework implementieren.</span><span class="sxs-lookup"><span data-stu-id="219be-175">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="219be-176">[Zurück](protobuf-messages.md)
>[Weiter](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="219be-176">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
