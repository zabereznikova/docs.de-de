---
title: 'Protobuf-skalare Datentypen: GrpC für WCF-Entwickler'
description: Erfahren Sie mehr über die grundlegenden und bekannten Datentypen, die von protobuf und GrpC in .net Core unterstützt werden.
ms.date: 09/09/2019
ms.openlocfilehash: ae7f5f48099000dff0eefb36e23cb9b9f2ac517c
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971555"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="9c11f-103">Skalare Datentypen für Protobuf</span><span class="sxs-lookup"><span data-stu-id="9c11f-103">Protobuf scalar data types</span></span>

<span data-ttu-id="9c11f-104">Protobuf unterstützt einen Bereich von systemeigenen skalaren Werttypen.</span><span class="sxs-lookup"><span data-stu-id="9c11f-104">Protobuf supports a range of native scalar value types.</span></span> <span data-ttu-id="9c11f-105">In der folgenden Tabelle sind alle Elemente mit dem C# entsprechenden Typ aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="9c11f-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="9c11f-106">Protobuf-Typ</span><span class="sxs-lookup"><span data-stu-id="9c11f-106">Protobuf type</span></span> | <span data-ttu-id="9c11f-107">C#-Typ</span><span class="sxs-lookup"><span data-stu-id="9c11f-107">C# type</span></span>      | <span data-ttu-id="9c11f-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c11f-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="9c11f-109">1</span><span class="sxs-lookup"><span data-stu-id="9c11f-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="9c11f-110">1</span><span class="sxs-lookup"><span data-stu-id="9c11f-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="9c11f-111">1</span><span class="sxs-lookup"><span data-stu-id="9c11f-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="9c11f-112">1</span><span class="sxs-lookup"><span data-stu-id="9c11f-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="9c11f-113">2</span><span class="sxs-lookup"><span data-stu-id="9c11f-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="9c11f-114">2</span><span class="sxs-lookup"><span data-stu-id="9c11f-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="9c11f-115">2</span><span class="sxs-lookup"><span data-stu-id="9c11f-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="9c11f-116">2</span><span class="sxs-lookup"><span data-stu-id="9c11f-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="9c11f-117">3</span><span class="sxs-lookup"><span data-stu-id="9c11f-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="9c11f-118">4</span><span class="sxs-lookup"><span data-stu-id="9c11f-118">4</span></span>     |

## <a name="notes"></a><span data-ttu-id="9c11f-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c11f-119">Notes</span></span>

1. <span data-ttu-id="9c11f-120">Beim Arbeiten mit signierten Werten ist die Standard Codierung für `int32` und `int64` ineffizient.</span><span class="sxs-lookup"><span data-stu-id="9c11f-120">The standard encoding for `int32` and `int64` is inefficient when working with signed values.</span></span> <span data-ttu-id="9c11f-121">Wenn das Feld wahrscheinlich negative Zahlen enthält, verwenden Sie stattdessen `sint32` oder `sint64`.</span><span class="sxs-lookup"><span data-stu-id="9c11f-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="9c11f-122">Beide Typen werden den C# Typen `int` und `long` zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9c11f-122">Both types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="9c11f-123">Die `fixed` Felder verwenden immer dieselbe Anzahl von Bytes, unabhängig davon, was der Wert ist.</span><span class="sxs-lookup"><span data-stu-id="9c11f-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="9c11f-124">Dieses Verhalten macht die Serialisierung und Deserialisierung bei größeren Werten schneller.</span><span class="sxs-lookup"><span data-stu-id="9c11f-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="9c11f-125">Protobuf-Zeichen folgen sind UTF-8-codiert (oder 7-Bit-ASCII), und die codierte Länge darf nicht größer als 2<sup>32</sup>sein.</span><span class="sxs-lookup"><span data-stu-id="9c11f-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded, and the encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="9c11f-126">Die protobuf-Laufzeit stellt einen `ByteString` Typ bereit, der problemlos C# `byte[]` Arrays zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9c11f-126">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="9c11f-127">Andere .net-primitive Typen</span><span class="sxs-lookup"><span data-stu-id="9c11f-127">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="9c11f-128">Datums- und Uhrzeitwerte</span><span class="sxs-lookup"><span data-stu-id="9c11f-128">Dates and times</span></span>

<span data-ttu-id="9c11f-129">Die System C#eigenen skalaren Typen bieten keine Datums-und Uhrzeitwerte, die den <xref:System.DateTimeOffset>, <xref:System.DateTime>und <xref:System.TimeSpan>entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9c11f-129">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="9c11f-130">Diese Typen können mithilfe einiger der "Well Known Types"-Erweiterungen von Google angegeben werden, die die Codegenerierung und Laufzeitunterstützung für komplexere Feldtypen auf den unterstützten Plattformen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9c11f-130">These types can be specified using some of Google's "Well Known Types" extensions, which provide code generation and runtime support for more complex field types across the supported platforms.</span></span> <span data-ttu-id="9c11f-131">In der folgenden Tabelle werden die Datums-und Uhrzeit Typen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9c11f-131">The following table shows the date and time types:</span></span>

| <span data-ttu-id="9c11f-132">C#-Typ</span><span class="sxs-lookup"><span data-stu-id="9c11f-132">C# type</span></span> | <span data-ttu-id="9c11f-133">Typ der protobuf-bekannten Typen</span><span class="sxs-lookup"><span data-stu-id="9c11f-133">Protobuf well-known type</span></span> |
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

<span data-ttu-id="9c11f-134">Die generierten Eigenschaften in der C# -Klasse sind nicht die .net-Datums-und-Uhrzeit Typen.</span><span class="sxs-lookup"><span data-stu-id="9c11f-134">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="9c11f-135">Die Eigenschaften verwenden die Klassen `Timestamp` und `Duration` im `Google.Protobuf.WellKnownTypes`-Namespace, die Methoden zum Wechseln in und aus `DateTimeOffset`, `DateTime`und `TimeSpan`bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9c11f-135">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace, which provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="9c11f-136">Der `Timestamp` Typ funktioniert mit UTC-Zeiten. `DateTimeOffset` Werte haben immer einen Offset von NULL, und die `DateTime.Kind`-Eigenschaft wird immer `DateTimeKind.Utc`.</span><span class="sxs-lookup"><span data-stu-id="9c11f-136">The `Timestamp` type works with UTC times; `DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property will always be `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="9c11f-137">System.Guid</span><span class="sxs-lookup"><span data-stu-id="9c11f-137">System.Guid</span></span>

<span data-ttu-id="9c11f-138">Der <xref:System.Guid> Typ, der als `UUID` auf anderen Plattformen bezeichnet wird, wird nicht direkt von protobuf unterstützt, und es gibt keinen bekannten Typ.</span><span class="sxs-lookup"><span data-stu-id="9c11f-138">The <xref:System.Guid> type, known as `UUID` on other platforms, isn't directly supported by Protobuf and there's no well-known type for it.</span></span> <span data-ttu-id="9c11f-139">Die beste Vorgehensweise besteht darin, `Guid` Werte als `string` Feld mit dem standardmäßigen `8-4-4-4-12` Hexadezimal Format (z. b. `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`) zu verarbeiten, das von allen Sprachen und Plattformen analysiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="9c11f-139">The best approach is to handle `Guid` values as `string` field, using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`), which can be parsed by all languages and platforms.</span></span> <span data-ttu-id="9c11f-140">Verwenden Sie kein `bytes` Feld für `Guid` Werte, da Probleme mit enumerität bei der Interaktion mit anderen Plattformen, wie z. b. Java, zu einem erratischen Verhalten führen können.</span><span class="sxs-lookup"><span data-stu-id="9c11f-140">Don't use a `bytes` field for `Guid` values, as problems with endianness can result in erratic behavior when interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="9c11f-141">Auf NULL festlegbare Typen</span><span class="sxs-lookup"><span data-stu-id="9c11f-141">Nullable types</span></span>

<span data-ttu-id="9c11f-142">Die protobuf-Codegenerierung C# für verwendet die systemeigenen Typen, z. b. `int` für `int32`.</span><span class="sxs-lookup"><span data-stu-id="9c11f-142">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="9c11f-143">Dies bedeutet, dass die Werte immer eingeschlossen werden und nicht NULL sein können.</span><span class="sxs-lookup"><span data-stu-id="9c11f-143">This means that the values are always included and can't be null.</span></span> <span data-ttu-id="9c11f-144">Für Werte, die explizite NULL-Werte erfordern, wie z. C# b. das Verwenden von `int?` in Ihrem Code, enthalten die "bekannten Typen" von protobuf C# Wrapper, die in Werte zulässt-Typen kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="9c11f-144">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="9c11f-145">Wenn Sie diese verwenden möchten, importieren Sie `wrappers.proto` wie folgt in Ihre `.proto` Datei:</span><span class="sxs-lookup"><span data-stu-id="9c11f-145">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="9c11f-146">Protobuf verwendet die einfache `T?` (z. b. `int?`) für die generierte Message-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9c11f-146">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="9c11f-147">In der folgenden Tabelle wird die komplette Liste der Wrapper Typen mit dem C# entsprechenden Typ angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9c11f-147">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="9c11f-148">C#-Typ</span><span class="sxs-lookup"><span data-stu-id="9c11f-148">C# type</span></span>   | <span data-ttu-id="9c11f-149">Bekannter Typwrapper</span><span class="sxs-lookup"><span data-stu-id="9c11f-149">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="9c11f-150">Die bekannten Typen `Timestamp` und `Duration` werden in .net als Klassen dargestellt. es ist also keine Notwendigkeit für eine Version, die NULL-Werte zulässt. es ist jedoch wichtig, bei Eigenschaften dieser Typen auf NULL zu prüfen, wenn Sie in `DateTimeOffset` oder `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="9c11f-150">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version, but it's important to check for null on properties of those types when converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="9c11f-151">Dezimalstellen</span><span class="sxs-lookup"><span data-stu-id="9c11f-151">Decimals</span></span>

<span data-ttu-id="9c11f-152">Protobuf unterstützt nicht den .net-`decimal` Typ, sondern nur `double` und `float`.</span><span class="sxs-lookup"><span data-stu-id="9c11f-152">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="9c11f-153">Im protobuf-Projekt gibt es eine fortlaufende Diskussion über die Möglichkeit, einen standardmäßigen `Decimal` Typ zu den bekannten Typen hinzuzufügen und Platt Form Unterstützung für Sprachen und Frameworks zu erhalten, die es unterstützen, aber es wurde noch nichts implementiert.</span><span class="sxs-lookup"><span data-stu-id="9c11f-153">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it, but nothing has been implemented yet.</span></span>

<span data-ttu-id="9c11f-154">Es ist möglich, eine Nachrichten Definition zu erstellen, die den `decimal` Typ darstellt, der für die sichere Serialisierung zwischen .NET-Clients und-Servern geeignet wäre. Entwickler auf anderen Plattformen müssten jedoch das verwendete Format verstehen und ihre eigene Behandlung implementieren.</span><span class="sxs-lookup"><span data-stu-id="9c11f-154">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers, but developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="9c11f-155">Erstellen eines benutzerdefinierten Dezimal Typs für protobuf</span><span class="sxs-lookup"><span data-stu-id="9c11f-155">Creating a custom Decimal type for Protobuf</span></span>

<span data-ttu-id="9c11f-156">Eine sehr einfache Implementierung könnte dem nicht standardmäßigen `Money` Typs ähneln, der von einigen Google-APIs verwendet wird, ohne das `currency` Feld.</span><span class="sxs-lookup"><span data-stu-id="9c11f-156">A very simple implementation could be similar to the non-standard `Money` type used by some Google APIs, without the `currency` field.</span></span>

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

<span data-ttu-id="9c11f-157">Das `nanos` Feld stellt Werte aus `0.999_999_999` zum `-0.999_999_999`dar.</span><span class="sxs-lookup"><span data-stu-id="9c11f-157">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="9c11f-158">Beispielsweise würde der `decimal` Wert `1.5m` als `{ units = 1, nanos = 500_000_000 }` dargestellt werden (aus diesem Grund wird das `nanos` Feld in diesem Beispiel den `sfixed32`-Typ verwenden, der für größere Werte effizienter als `int32` codiert).</span><span class="sxs-lookup"><span data-stu-id="9c11f-158">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }` (this is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values).</span></span> <span data-ttu-id="9c11f-159">Wenn das `units` Feld negativ ist, sollte das `nanos` Feld ebenfalls negativ sein.</span><span class="sxs-lookup"><span data-stu-id="9c11f-159">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="9c11f-160">Es gibt mehrere andere Algorithmen, um `decimal` Werte als Byte Zeichenfolgen zu codieren, aber diese Nachricht ist viel leichter zu verstehen als Sie, und die Werte werden von *[Byte Reihenfolge](https://en.wikipedia.org/wiki/Endianness)* auf verschiedenen Plattformen nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="9c11f-160">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is much easier to understand than any of them, and the values are not affected by *[endianness](https://en.wikipedia.org/wiki/Endianness)* on different platforms.</span></span>

<span data-ttu-id="9c11f-161">Die Konvertierung zwischen diesem Typ und der BCL-`decimal` Typ könnte in C# wie folgt implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="9c11f-161">Conversion between this type and the BCL `decimal` type could be implemented in C# like this.</span></span>

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
> <span data-ttu-id="9c11f-162">Jedes Mal, wenn Sie benutzerdefinierte Nachrichten Typen für das Hilfsprogramm wie folgt verwenden, **müssen** Sie diese mit Kommentaren in der `.proto` dokumentieren, damit andere Entwickler die Konvertierung in und aus dem entsprechenden Typ in ihrer eigenen Sprache oder Ihrem Framework implementieren können.</span><span class="sxs-lookup"><span data-stu-id="9c11f-162">Whenever you use custom utility message types like this, you **must** document them with comments in the `.proto` so that other developers can implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9c11f-163">[Zurück](protobuf-messages.md)
>[Weiter](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="9c11f-163">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
