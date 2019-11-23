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
# <a name="protobuf-scalar-data-types"></a>Skalare Datentypen für Protobuf

Protobuf unterstützt einen Bereich von systemeigenen skalaren Werttypen. In der folgenden Tabelle sind alle Elemente mit dem C# entsprechenden Typ aufgeführt:

| Protobuf-Typ | C#-Typ      | Hinweise |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | 1     |
| `int64`       | `long`       | 1     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | 1     |
| `sint64`      | `long`       | 1     |
| `fixed32`     | `uint`       | 2     |
| `fixed64`     | `ulong`      | 2     |
| `sfixed32`    | `int`        | 2     |
| `sfixed64`    | `long`       | 2     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | 3     |
| `bytes`       | `ByteString` | 4     |

## <a name="notes"></a>Hinweise

1. Beim Arbeiten mit signierten Werten ist die Standard Codierung für `int32` und `int64` ineffizient. Wenn das Feld wahrscheinlich negative Zahlen enthält, verwenden Sie stattdessen `sint32` oder `sint64`. Beide Typen werden den C# Typen `int` und `long` zugeordnet.
2. Die `fixed` Felder verwenden immer dieselbe Anzahl von Bytes, unabhängig davon, was der Wert ist. Dieses Verhalten macht die Serialisierung und Deserialisierung bei größeren Werten schneller.
3. Protobuf-Zeichen folgen sind UTF-8-codiert (oder 7-Bit-ASCII), und die codierte Länge darf nicht größer als 2<sup>32</sup>sein.
4. Die protobuf-Laufzeit stellt einen `ByteString` Typ bereit, der problemlos C# `byte[]` Arrays zugeordnet ist.

## <a name="other-net-primitive-types"></a>Andere .net-primitive Typen

### <a name="dates-and-times"></a>Datums- und Uhrzeitwerte

Die System C#eigenen skalaren Typen bieten keine Datums-und Uhrzeitwerte, die den <xref:System.DateTimeOffset>, <xref:System.DateTime>und <xref:System.TimeSpan>entsprechen. Diese Typen können mithilfe einiger der "Well Known Types"-Erweiterungen von Google angegeben werden, die die Codegenerierung und Laufzeitunterstützung für komplexere Feldtypen auf den unterstützten Plattformen bereitstellen. In der folgenden Tabelle werden die Datums-und Uhrzeit Typen angezeigt:

| C#-Typ | Typ der protobuf-bekannten Typen |
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

Die generierten Eigenschaften in der C# -Klasse sind nicht die .net-Datums-und-Uhrzeit Typen. Die Eigenschaften verwenden die Klassen `Timestamp` und `Duration` im `Google.Protobuf.WellKnownTypes`-Namespace, die Methoden zum Wechseln in und aus `DateTimeOffset`, `DateTime`und `TimeSpan`bereitstellen.

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
> Der `Timestamp` Typ funktioniert mit UTC-Zeiten. `DateTimeOffset` Werte haben immer einen Offset von NULL, und die `DateTime.Kind`-Eigenschaft wird immer `DateTimeKind.Utc`.

### <a name="systemguid"></a>System.Guid

Der <xref:System.Guid> Typ, der als `UUID` auf anderen Plattformen bezeichnet wird, wird nicht direkt von protobuf unterstützt, und es gibt keinen bekannten Typ. Die beste Vorgehensweise besteht darin, `Guid` Werte als `string` Feld mit dem standardmäßigen `8-4-4-4-12` Hexadezimal Format (z. b. `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`) zu verarbeiten, das von allen Sprachen und Plattformen analysiert werden kann. Verwenden Sie kein `bytes` Feld für `Guid` Werte, da Probleme mit enumerität bei der Interaktion mit anderen Plattformen, wie z. b. Java, zu einem erratischen Verhalten führen können.

### <a name="nullable-types"></a>Auf NULL festlegbare Typen

Die protobuf-Codegenerierung C# für verwendet die systemeigenen Typen, z. b. `int` für `int32`. Dies bedeutet, dass die Werte immer eingeschlossen werden und nicht NULL sein können. Für Werte, die explizite NULL-Werte erfordern, wie z. C# b. das Verwenden von `int?` in Ihrem Code, enthalten die "bekannten Typen" von protobuf C# Wrapper, die in Werte zulässt-Typen kompiliert werden. Wenn Sie diese verwenden möchten, importieren Sie `wrappers.proto` wie folgt in Ihre `.proto` Datei:

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf verwendet die einfache `T?` (z. b. `int?`) für die generierte Message-Eigenschaft.

In der folgenden Tabelle wird die komplette Liste der Wrapper Typen mit dem C# entsprechenden Typ angezeigt:

| C#-Typ   | Bekannter Typwrapper       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

Die bekannten Typen `Timestamp` und `Duration` werden in .net als Klassen dargestellt. es ist also keine Notwendigkeit für eine Version, die NULL-Werte zulässt. es ist jedoch wichtig, bei Eigenschaften dieser Typen auf NULL zu prüfen, wenn Sie in `DateTimeOffset` oder `TimeSpan`.

## <a name="decimals"></a>Dezimalstellen

Protobuf unterstützt nicht den .net-`decimal` Typ, sondern nur `double` und `float`. Im protobuf-Projekt gibt es eine fortlaufende Diskussion über die Möglichkeit, einen standardmäßigen `Decimal` Typ zu den bekannten Typen hinzuzufügen und Platt Form Unterstützung für Sprachen und Frameworks zu erhalten, die es unterstützen, aber es wurde noch nichts implementiert.

Es ist möglich, eine Nachrichten Definition zu erstellen, die den `decimal` Typ darstellt, der für die sichere Serialisierung zwischen .NET-Clients und-Servern geeignet wäre. Entwickler auf anderen Plattformen müssten jedoch das verwendete Format verstehen und ihre eigene Behandlung implementieren.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Erstellen eines benutzerdefinierten Dezimal Typs für protobuf

Eine sehr einfache Implementierung könnte dem nicht standardmäßigen `Money` Typs ähneln, der von einigen Google-APIs verwendet wird, ohne das `currency` Feld.

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

Das `nanos` Feld stellt Werte aus `0.999_999_999` zum `-0.999_999_999`dar. Beispielsweise würde der `decimal` Wert `1.5m` als `{ units = 1, nanos = 500_000_000 }` dargestellt werden (aus diesem Grund wird das `nanos` Feld in diesem Beispiel den `sfixed32`-Typ verwenden, der für größere Werte effizienter als `int32` codiert). Wenn das `units` Feld negativ ist, sollte das `nanos` Feld ebenfalls negativ sein.

> [!NOTE]
> Es gibt mehrere andere Algorithmen, um `decimal` Werte als Byte Zeichenfolgen zu codieren, aber diese Nachricht ist viel leichter zu verstehen als Sie, und die Werte werden von *[Byte Reihenfolge](https://en.wikipedia.org/wiki/Endianness)* auf verschiedenen Plattformen nicht beeinträchtigt.

Die Konvertierung zwischen diesem Typ und der BCL-`decimal` Typ könnte in C# wie folgt implementiert werden.

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
> Jedes Mal, wenn Sie benutzerdefinierte Nachrichten Typen für das Hilfsprogramm wie folgt verwenden, **müssen** Sie diese mit Kommentaren in der `.proto` dokumentieren, damit andere Entwickler die Konvertierung in und aus dem entsprechenden Typ in ihrer eigenen Sprache oder Ihrem Framework implementieren können.

>[!div class="step-by-step"]
>[Zurück](protobuf-messages.md)
>[Weiter](protobuf-nested-types.md)
