---
title: 'Protobuf-skalare Datentypen: GrpC für WCF-Entwickler'
description: Erfahren Sie mehr über die grundlegenden und bekannten Datentypen, die protobuf und GrpC in .net Core unterstützen.
ms.date: 09/09/2019
ms.openlocfilehash: 5447067b953d257258950d020636e0b38245e20d
ms.sourcegitcommit: 665f8fc55258356f4d2f4a6585b750c974b26675
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2020
ms.locfileid: "91573643"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="e309e-103">Skalare Datentypen für Protobuf</span><span class="sxs-lookup"><span data-stu-id="e309e-103">Protobuf scalar data types</span></span>

<span data-ttu-id="e309e-104">Der Protokollpuffer (protobuf) unterstützt einen Bereich von systemeigenen skalaren Werttypen.</span><span class="sxs-lookup"><span data-stu-id="e309e-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="e309e-105">In der folgenden Tabelle werden alle dieser Typen mit dem entsprechenden C#-Typ aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="e309e-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="e309e-106">Protobuf-Typ</span><span class="sxs-lookup"><span data-stu-id="e309e-106">Protobuf type</span></span> | <span data-ttu-id="e309e-107">C#-Typ</span><span class="sxs-lookup"><span data-stu-id="e309e-107">C# type</span></span>      | <span data-ttu-id="e309e-108">Notizen</span><span class="sxs-lookup"><span data-stu-id="e309e-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="e309e-109">1</span><span class="sxs-lookup"><span data-stu-id="e309e-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="e309e-110">1</span><span class="sxs-lookup"><span data-stu-id="e309e-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="e309e-111">1</span><span class="sxs-lookup"><span data-stu-id="e309e-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="e309e-112">1</span><span class="sxs-lookup"><span data-stu-id="e309e-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="e309e-113">2</span><span class="sxs-lookup"><span data-stu-id="e309e-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="e309e-114">2</span><span class="sxs-lookup"><span data-stu-id="e309e-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="e309e-115">2</span><span class="sxs-lookup"><span data-stu-id="e309e-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="e309e-116">2</span><span class="sxs-lookup"><span data-stu-id="e309e-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="e309e-117">3</span><span class="sxs-lookup"><span data-stu-id="e309e-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="e309e-118">4</span><span class="sxs-lookup"><span data-stu-id="e309e-118">4</span></span>     |

<span data-ttu-id="e309e-119">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="e309e-119">Notes:</span></span>

1. <span data-ttu-id="e309e-120">Die Standard Codierung für `int32` und `int64` ist ineffizient, wenn Sie mit signierten Werten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="e309e-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="e309e-121">Wenn das Feld wahrscheinlich negative Zahlen enthält, verwenden Sie `sint32` stattdessen oder `sint64` .</span><span class="sxs-lookup"><span data-stu-id="e309e-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="e309e-122">Diese Typen werden dem c# `int` - `long` bzw. dem-Typ zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e309e-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="e309e-123">`fixed`In den Feldern wird immer dieselbe Anzahl von Bytes verwendet, unabhängig davon, was der Wert ist.</span><span class="sxs-lookup"><span data-stu-id="e309e-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="e309e-124">Dieses Verhalten macht die Serialisierung und Deserialisierung bei größeren Werten schneller.</span><span class="sxs-lookup"><span data-stu-id="e309e-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="e309e-125">Protobuf-Zeichen folgen sind UTF-8-codiert (oder 7-Bit-ASCII).</span><span class="sxs-lookup"><span data-stu-id="e309e-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="e309e-126">Die codierte Länge darf nicht größer als 2<sup>32</sup>sein.</span><span class="sxs-lookup"><span data-stu-id="e309e-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="e309e-127">Die protobuf-Laufzeit stellt einen `ByteString` Typ bereit, der problemlos und aus c#-Arrays zugeordnet wird `byte[]` .</span><span class="sxs-lookup"><span data-stu-id="e309e-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="e309e-128">Andere .net-primitive Typen</span><span class="sxs-lookup"><span data-stu-id="e309e-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="e309e-129">Datums- und Zeitangaben</span><span class="sxs-lookup"><span data-stu-id="e309e-129">Dates and times</span></span>

<span data-ttu-id="e309e-130">Die nativen skalaren Typen stellen keine Datums-und Uhrzeitwerte bereit, die den c#-,-und-Werten entsprechen <xref:System.DateTimeOffset> <xref:System.DateTime> <xref:System.TimeSpan> .</span><span class="sxs-lookup"><span data-stu-id="e309e-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="e309e-131">Sie können diese Typen mithilfe einiger der "Well Known Types"-Erweiterungen von Google angeben.</span><span class="sxs-lookup"><span data-stu-id="e309e-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="e309e-132">Diese Erweiterungen bieten Codegenerierung und Runtime-Unterstützung für komplexe Feldtypen für die unterstützten Plattformen.</span><span class="sxs-lookup"><span data-stu-id="e309e-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span>

<span data-ttu-id="e309e-133">In der folgenden Tabelle werden die Datums- und Zeittypen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="e309e-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="e309e-134">C#-Typ</span><span class="sxs-lookup"><span data-stu-id="e309e-134">C# type</span></span> | <span data-ttu-id="e309e-135">Bekannter Protobuf-Typ</span><span class="sxs-lookup"><span data-stu-id="e309e-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="e309e-136">Die in der C#-Klasse generierten Eigenschaften sind nicht die Datums- und Zeittypen von .NET.</span><span class="sxs-lookup"><span data-stu-id="e309e-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="e309e-137">Die Eigenschaften nutzen die Klassen `Timestamp` und `Duration` im Namespace `Google.Protobuf.WellKnownTypes`.</span><span class="sxs-lookup"><span data-stu-id="e309e-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="e309e-138">Diese Klassen stellen Methoden zum Konvertieren in und aus `DateTimeOffset`, `DateTime` und `TimeSpan` bereit.</span><span class="sxs-lookup"><span data-stu-id="e309e-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="e309e-139">Der `Timestamp`-Typ kann mit UTC-Zeiten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e309e-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="e309e-140">`DateTimeOffset`-Werte weisen immer ein Offset von 0 (null) auf, und die `DateTime.Kind`-Eigenschaft ist immer `DateTimeKind.Utc`.</span><span class="sxs-lookup"><span data-stu-id="e309e-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="e309e-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="e309e-141">System.Guid</span></span>

<span data-ttu-id="e309e-142">Protobuf unterstützt den <xref:System.Guid> Typ, der als `UUID` auf anderen Plattformen bezeichnet wird, nicht direkt.</span><span class="sxs-lookup"><span data-stu-id="e309e-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="e309e-143">Dafür gibt es keinen bekannten Typ.</span><span class="sxs-lookup"><span data-stu-id="e309e-143">There's no well-known type for it.</span></span>

<span data-ttu-id="e309e-144">Der beste Ansatz besteht darin, `Guid` Werte als Feld zu behandeln `string` , indem Sie das standardmäßige `8-4-4-4-12` Hexadezimal Format (z `45a9fda3-bd01-47a9-8460-c1cd7484b0b3` . b.) verwenden.</span><span class="sxs-lookup"><span data-stu-id="e309e-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="e309e-145">Dieses Format kann von allen Sprachen und Plattformen analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="e309e-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="e309e-146">Verwenden Sie kein `bytes` Feld für- `Guid` Werte.</span><span class="sxs-lookup"><span data-stu-id="e309e-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="e309e-147">Probleme mit *Byte Reihenfolge* ([Wikipedia-Definition](https://en.wikipedia.org/wiki/Endianness)) können zu einem erratischen Verhalten führen, wenn protobuf mit anderen Plattformen wie Java interagiert.</span><span class="sxs-lookup"><span data-stu-id="e309e-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="e309e-148">Nullable-Typen</span><span class="sxs-lookup"><span data-stu-id="e309e-148">Nullable types</span></span>

<span data-ttu-id="e309e-149">Bei der Protobuf-Codegenerierung für C# werden die nativen Typen verwendet, z. B. `int` für `int32`.</span><span class="sxs-lookup"><span data-stu-id="e309e-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="e309e-150">Daher sind die Werte immer enthalten und dürfen nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="e309e-150">So the values are always included and can't be null.</span></span>

<span data-ttu-id="e309e-151">Für Werte, die explizite NULL-Werte erfordern, wie z. `int?` b. die Verwendung von in Ihrem c#-Code, enthalten die "bekannten Typen" von protobuf Wrapper, die in c#-Typen mit Nullwert kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="e309e-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="e309e-152">Importieren Sie Sie wie folgt `wrappers.proto` in die `.proto` Datei:</span><span class="sxs-lookup"><span data-stu-id="e309e-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="e309e-153">Protobuf verwendet das einfache `T?` (z `int?` . b.) für die generierte Message-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e309e-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="e309e-154">In der folgenden Tabelle finden Sie eine vollständige Liste der Wrappertypen mit dem entsprechenden C#-Typ:</span><span class="sxs-lookup"><span data-stu-id="e309e-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="e309e-155">C#-Typ</span><span class="sxs-lookup"><span data-stu-id="e309e-155">C# type</span></span>   | <span data-ttu-id="e309e-156">Well Known Type-Wrapper</span><span class="sxs-lookup"><span data-stu-id="e309e-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="e309e-157">Die bekannten Typen `Timestamp` und `Duration` werden in .net als Klassen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e309e-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes.</span></span> <span data-ttu-id="e309e-158">In c# 8 und höher können Sie Verweis Typen verwenden, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="e309e-158">In C# 8 and beyond, you can use nullable reference types.</span></span> <span data-ttu-id="e309e-159">Es ist jedoch wichtig, bei Eigenschaften dieser Typen auf NULL zu prüfen, wenn Sie eine Umstellung auf oder durchsetzen `DateTimeOffset` `TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="e309e-159">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="e309e-160">Dezimalstellen</span><span class="sxs-lookup"><span data-stu-id="e309e-160">Decimals</span></span>

<span data-ttu-id="e309e-161">Protobuf unterstützt den .NET-Typ `decimal` nicht nativ, nur `double` und `float`.</span><span class="sxs-lookup"><span data-stu-id="e309e-161">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="e309e-162">Im protobuf-Projekt gibt es eine fortlaufende Erörterung der Möglichkeit `Decimal` , den bekannten Typen einen Standardtyp hinzuzufügen, mit Platt Form Unterstützung für Sprachen und Frameworks, die diese unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e309e-162">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="e309e-163">Bisher wurde keine Implementierung vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="e309e-163">Nothing has been implemented yet.</span></span>

<span data-ttu-id="e309e-164">Es ist möglich, eine Nachrichten Definition zu erstellen, die den `decimal` Typ darstellt, der für die sichere Serialisierung zwischen .NET-Clients und-Servern geeignet wäre.</span><span class="sxs-lookup"><span data-stu-id="e309e-164">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="e309e-165">Entwickler anderer Plattformen müssten jedoch das verwendete Format verstehen und ihr eigenes Format implementieren, um dieses zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e309e-165">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="e309e-166">Erstellen eines benutzerdefinierten Dezimaltyps für Protobuf</span><span class="sxs-lookup"><span data-stu-id="e309e-166">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="e309e-167">Eine einfache Implementierung ähnelt möglicherweise dem nicht dem Standard entsprechenden `Money` Typ, der von einigen Google-APIs verwendet wird, ohne das- `currency` Feld.</span><span class="sxs-lookup"><span data-stu-id="e309e-167">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

```protobuf
package CustomTypes;

// Example: 12345.6789 -> { units = 12345, nanos = 678900000 }
message DecimalValue {

    // Whole units part of the amount
    int64 units = 1;

    // Nano units of the amount (10^-9)
    // Must be same sign as units
    sfixed32 nanos = 2;
}
```

<span data-ttu-id="e309e-168">Das `nanos`-Feld stellt Werte von `0.999_999_999` bis `-0.999_999_999` dar.</span><span class="sxs-lookup"><span data-stu-id="e309e-168">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="e309e-169">Beispielsweise würde der `decimal`-Wert `1.5m` als `{ units = 1, nanos = 500_000_000 }` dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e309e-169">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="e309e-170">Aus diesem Grund wird in diesem Beispiel für das `nanos`-Feld der `sfixed32`-Typ verwendet, der bei größeren Werten effizienter als `int32` codiert wird.</span><span class="sxs-lookup"><span data-stu-id="e309e-170">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="e309e-171">Wenn das `units`-Feld negativ ist, sollte auch das `nanos`-Feld negativ sein.</span><span class="sxs-lookup"><span data-stu-id="e309e-171">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="e309e-172">Es gibt mehrere andere Algorithmen zum Codieren von `decimal`-Werten als Bytezeichenfolgen, jedoch ist diese Nachricht leichter zu verstehen, als alle dieser Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="e309e-172">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="e309e-173">Die Werte sind von der enumalität auf verschiedenen Plattformen nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="e309e-173">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="e309e-174">Konvertierungen zwischen diesem Typ und dem BCL-Typ `decimal` können wie folgt in C# implementiert werden:</span><span class="sxs-lookup"><span data-stu-id="e309e-174">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

```csharp
namespace CustomTypes
{
    public partial class DecimalValue
    {
        private const decimal NanoFactor = 1_000_000_000;
        public DecimalValue(long units, int nanos)
        {
            Units = units;
            Nanos = nanos;
        }

        public long Units { get; }
        public int Nanos { get; }

        public static implicit operator decimal(CustomTypes.DecimalValue grpcDecimal)
        {
            return grpcDecimal.Units + grpcDecimal.Nanos / NanoFactor;
        }

        public static implicit operator CustomTypes.DecimalValue(decimal value)
        {
            var units = decimal.ToInt64(value);
            var nanos = decimal.ToInt32((value - units) * NanoFactor);
            return new CustomTypes.DecimalValue(units, nanos);
        }
    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="e309e-175">Wenn Sie benutzerdefinierte Nachrichten Typen wie diese verwenden, *müssen* Sie diese mit Kommentaren in dokumentieren `.proto` .</span><span class="sxs-lookup"><span data-stu-id="e309e-175">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="e309e-176">Andere Entwickler können dann eine Konvertierung in und aus dem entsprechenden Typ in ihrer eigenen Sprache oder in Ihrem eigenen Framework implementieren.</span><span class="sxs-lookup"><span data-stu-id="e309e-176">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e309e-177">[Zurück](protobuf-messages.md)
>[Weiter](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="e309e-177">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
