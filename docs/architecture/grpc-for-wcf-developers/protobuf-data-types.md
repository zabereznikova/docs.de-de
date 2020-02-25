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
# <a name="protobuf-scalar-data-types"></a>Skalare Datentypen für Protobuf

Der Protokollpuffer (protobuf) unterstützt einen Bereich von systemeigenen skalaren Werttypen. In der folgenden Tabelle sind alle Elemente mit dem C# entsprechenden Typ aufgeführt:

| Protobuf-Typ | C#-Typ      | Notizen |
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

Hinweise:

1. Die Standard Codierung für `int32` und `int64` ist ineffizient, wenn Sie mit signierten Werten arbeiten. Wenn das Feld wahrscheinlich negative Zahlen enthält, verwenden Sie stattdessen `sint32` oder `sint64`. Diese Typen werden den C# `int`-und `long` Typen zugeordnet.
2. Die `fixed` Felder verwenden immer dieselbe Anzahl von Bytes, unabhängig davon, was der Wert ist. Dieses Verhalten macht die Serialisierung und Deserialisierung bei größeren Werten schneller.
3. Protobuf-Zeichen folgen sind UTF-8-codiert (oder 7-Bit-ASCII). Die codierte Länge darf nicht größer als 2<sup>32</sup>sein.
4. Die protobuf-Laufzeit stellt einen `ByteString` Typ bereit, der problemlos C# `byte[]` Arrays zugeordnet ist.

## <a name="other-net-primitive-types"></a>Andere .net-primitive Typen

### <a name="dates-and-times"></a>Datums- und Zeitangaben

Die System C#eigenen skalaren Typen bieten keine Datums-und Uhrzeitwerte, die den <xref:System.DateTimeOffset>, <xref:System.DateTime>und <xref:System.TimeSpan>entsprechen. Sie können diese Typen mithilfe einiger der "Well Known Types"-Erweiterungen von Google angeben. Diese Erweiterungen bieten Codegenerierung und Laufzeitunterstützung für komplexe Feldtypen auf den unterstützten Plattformen. 

In der folgenden Tabelle werden die Datums-und Uhrzeit Typen angezeigt:

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

Die generierten Eigenschaften in der C# -Klasse sind nicht die .net-Datums-und-Uhrzeit Typen. Die Eigenschaften verwenden die Klassen `Timestamp` und `Duration` im `Google.Protobuf.WellKnownTypes` Namespace. Diese Klassen stellen Methoden zum Wechseln in und aus `DateTimeOffset`, `DateTime`und `TimeSpan`bereit.

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
> Der `Timestamp`-Typ funktioniert mit UTC-Zeiten. `DateTimeOffset` Werte haben immer einen Offset von NULL, und die `DateTime.Kind`-Eigenschaft ist immer `DateTimeKind.Utc`.

### <a name="systemguid"></a>System.Guid

Protobuf unterstützt den <xref:System.Guid> Typ, der als `UUID` auf anderen Plattformen bezeichnet wird, nicht direkt. Dafür gibt es keinen bekannten Typ. 

Die beste Vorgehensweise besteht darin, `Guid` Werte als `string` Feld zu behandeln, indem Sie das standardmäßige `8-4-4-4-12` Hexadezimal Format (z. b. `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`) verwenden. Dieses Format kann von allen Sprachen und Plattformen analysiert werden.

Verwenden Sie kein `bytes` Feld für `Guid` Werte. Probleme mit *Byte Reihenfolge* ([Wikipedia-Definition](https://en.wikipedia.org/wiki/Endianness)) können zu einem erratischen Verhalten führen, wenn protobuf mit anderen Plattformen wie Java interagiert.

### <a name="nullable-types"></a>Auf NULL festlegbare Typen

Die protobuf-Codegenerierung C# für verwendet die systemeigenen Typen, z. b. `int` für `int32`. Daher sind die Werte immer enthalten und dürfen nicht NULL sein. 

Für Werte, die explizite NULL-Werte erfordern, wie z. C# b. das Verwenden von `int?` in Ihrem Code, enthalten die "bekannten Typen" von protobuf C# Wrapper, die in Werte zulässt-Typen kompiliert werden. Wenn Sie diese verwenden möchten, importieren Sie `wrappers.proto` wie folgt in Ihre `.proto` Datei:

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

Die bekannten Typen `Timestamp` und `Duration` werden in .net als Klassen dargestellt, sodass keine Version vorhanden ist, die NULL-Werte zulässt. Es ist jedoch wichtig, bei Eigenschaften dieser Typen auf NULL zu prüfen, wenn Sie zu `DateTimeOffset` oder `TimeSpan`wechseln.

## <a name="decimals"></a>Dezimalstellen

Protobuf unterstützt nicht den .net-`decimal` Typ, sondern nur `double` und `float`. Im protobuf-Projekt gibt es eine fortlaufende Diskussion über die Möglichkeit, den bekannten Typen einen Standard `Decimal` Typ hinzuzufügen, mit Platt Form Unterstützung für Sprachen und Frameworks, die diese unterstützen. Es wurde noch nichts implementiert.

Es ist möglich, eine Nachrichten Definition zu erstellen, die den `decimal` Typ darstellt, der für die sichere Serialisierung zwischen .NET-Clients und-Servern geeignet wäre. Entwickler auf anderen Plattformen müssten jedoch das Format verstehen, das verwendet wird, und ihre eigene Behandlung für die Anwendung implementieren.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Erstellen eines benutzerdefinierten Dezimal Typs für protobuf

Eine einfache Implementierung ähnelt möglicherweise dem nicht standardmäßigen `Money`-Typ, den einige Google-APIs verwenden, ohne das `currency` Feld.

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

Das `nanos` Feld stellt Werte aus `0.999_999_999` zum `-0.999_999_999`dar. Beispielsweise wird der `decimal` Wert `1.5m` als `{ units = 1, nanos = 500_000_000 }`dargestellt. Aus diesem Grund verwendet das Feld "`nanos`" in diesem Beispiel den `sfixed32`-Typ, der effizienter als `int32` für größere Werte codiert. Wenn das `units` Feld negativ ist, sollte das `nanos` Feld ebenfalls negativ sein.

> [!NOTE]
> Es gibt mehrere andere Algorithmen zum Codieren von `decimal` Werten als Byte Zeichenfolgen, diese Meldung ist jedoch leichter zu verstehen als alle. Die Werte sind von der enumalität auf verschiedenen Plattformen nicht betroffen.

Die Konvertierung zwischen diesem Typ und der BCL-`decimal` Typs kann in C# wie folgt implementiert werden:

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
> Wenn Sie benutzerdefinierte Nachrichten Typen wie diese verwenden, *müssen* Sie diese mit Kommentaren in `.proto`dokumentieren. Andere Entwickler können dann eine Konvertierung in und aus dem entsprechenden Typ in ihrer eigenen Sprache oder in Ihrem eigenen Framework implementieren.

>[!div class="step-by-step"]
>[Zurück](protobuf-messages.md)
>[Weiter](protobuf-nested-types.md)
