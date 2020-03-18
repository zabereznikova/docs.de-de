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
# <a name="protobuf-scalar-data-types"></a>Skalare Datentypen für Protobuf

Der Protokollpuffer (Protobuf) unterstützt eine Reihe systemeigener skalarer Werttypen. In der folgenden Tabelle sind sie alle mit dem entsprechenden Typ "C" aufgeführt:

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

1. Die Standardcodierung `int32` für `int64` und ist ineffizient, wenn Sie mit signierten Werten arbeiten. Wenn Ihr Feld wahrscheinlich negative Zahlen `sint32` `sint64` enthält, verwenden Sie oder stattdessen. Diese Typen werden dem `int` `long` C- bzw. den Typen zugeordnet.
2. Die `fixed` Felder verwenden immer die gleiche Anzahl von Bytes, unabhängig vom Wert. Dieses Verhalten beschleunigt die Serialisierung und Deserialisierung für größere Werte.
3. Protobuf-Zeichenfolgen sind UTF-8 (oder 7-Bit ASCII) codiert. Die codierte Länge darf nicht größer als 2<sup>32</sup>sein.
4. Die Protobuf-Laufzeit `ByteString` stellt einen Typ bereit, `byte[]` der einfach den und von C-Arrays zugeordnet wird.

## <a name="other-net-primitive-types"></a>Andere Primitivetypen von .NET

### <a name="dates-and-times"></a>Datums- und Zeitangaben

Die systemeigenen Skalartypen bieten keine Datums- <xref:System.DateTimeOffset>und Uhrzeitwerte, <xref:System.DateTime>die <xref:System.TimeSpan>den C-, - und . Sie können diese Typen angeben, indem Sie einige der Google-Erweiterungen "Well Known Types" verwenden. Diese Erweiterungen bieten Codegenerierungs- und Laufzeitunterstützung für komplexe Feldtypen auf allen unterstützten Plattformen.

Die folgende Tabelle zeigt die Datums- und Uhrzeittypen:

| C#-Typ | Protobuf bekannter Typ |
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

Die generierten Eigenschaften in der C-Klasse sind nicht die .NET-Datums- und -Uhrzeittypen. Die Eigenschaften `Timestamp` verwenden `Duration` die `Google.Protobuf.WellKnownTypes` und-Klassen im Namespace. Diese Klassen stellen Methoden zum `DateTimeOffset`Konvertieren `DateTime`in `TimeSpan`und von , und bereit.

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
> Der `Timestamp` Typ funktioniert mit UTC-Zeiten. `DateTimeOffset`Werte haben immer einen Offset `DateTime.Kind` von Null, und die Eigenschaft ist immer `DateTimeKind.Utc`.

### <a name="systemguid"></a>System.Guid

Protobuf unterstützt den <xref:System.Guid> Typ nicht direkt, der auf `UUID` anderen Plattformen bekannt ist. Es gibt keinen bekannten Typ dafür.

Der beste Ansatz `Guid` besteht darin, Werte `string` als `8-4-4-4-12` Feld zu behandeln, indem `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`sie das standardmäßige hexadezimale Format (z. B. ) verwenden. Alle Sprachen und Plattformen können dieses Format analysieren.

Verwenden Sie kein `bytes` Feld `Guid` für Werte. Probleme mit *der Endianität* ([Wikipedia-Definition](https://en.wikipedia.org/wiki/Endianness)) können zu unregelmäßigem Verhalten führen, wenn Protobuf mit anderen Plattformen wie Java interagiert.

### <a name="nullable-types"></a>Auf NULL festlegbare Typen

Die Protobuf-Codegenerierung für C- verwendet `int` die `int32`systemeigenen Typen, z. B. für . Die Werte sind also immer enthalten und können nicht null sein.

Für Werte, die explizite `int?` NULL erfordern, z. B. die Verwendung in Ihrem C-Code, enthalten die "Well Known Types" von Protobufs Wrapper, die in nullierbare C-Typen kompiliert werden. Um sie zu `wrappers.proto` verwenden, importieren Sie in Ihre `.proto` Datei wie folgt:

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf verwendet die `T?` einfache (z. B. `int?`) für die generierte Nachrichteneigenschaft.

Die folgende Tabelle zeigt die vollständige Liste der Wrappertypen mit dem entsprechenden Typ "C":

| C#-Typ   | Bekannter Typ-Wrapper       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

Die bekannten `Timestamp` Typen, `Duration` die in .NET als Klassen dargestellt werden, sodass keine nullierbare Version erforderlich ist. Es ist jedoch wichtig, beim Konvertieren in `DateTimeOffset` oder `TimeSpan`auf NULL nach Eigenschaften dieser Typen zu suchen.

## <a name="decimals"></a>Dezimalstellen

Protobuf unterstützt nicht nativ den `decimal` .NET-Typ, nur `double` und `float`. Im Protobuf-Projekt wird derzeit über die Möglichkeit diskutiert, den bekannten Typen einen Standardtyp `Decimal` hinzuzufügen, mit Plattformunterstützung für Sprachen und Frameworks, die ihn unterstützen. Es wurde noch nichts umgesetzt.

Es ist möglich, eine Nachrichtendefinition `decimal` zu erstellen, um den Typ darzustellen, der für die sichere Serialisierung zwischen .NET-Clients und Servern verwendet werden würde. Aber Entwickler auf anderen Plattformen müssten das verwendete Format verstehen und ihre eigene Handhabung dafür implementieren.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Erstellen eines benutzerdefinierten Dezimaltyps für Protobuf

Eine einfache Implementierung kann dem `Money` nicht standardmäßigen Typ ähneln, `currency` den einige Google-APIs ohne das Feld verwenden.

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

Das `nanos` Feld stellt `0.999_999_999` `-0.999_999_999`Werte von bis dar. Der `decimal` Wert `1.5m` wird z. `{ units = 1, nanos = 500_000_000 }`B. als dargestellt. Aus diesem `nanos` Grund verwendet das `sfixed32` Feld in diesem Beispiel `int32` den Typ, der effizienter codiert als bei größeren Werten. Wenn `units` das Feld negativ `nanos` ist, sollte das Feld ebenfalls negativ sein.

> [!NOTE]
> Es gibt mehrere andere Algorithmen `decimal` für die Codierung von Werten als Bytezeichenfolgen, aber diese Nachricht ist einfacher zu verstehen als jeder andere. Die Werte werden nicht durch Endianität auf verschiedenen Plattformen beeinflusst.

Die Konvertierung zwischen diesem `decimal` Typ und dem BCL-Typ kann wie folgt in C- implementiert werden:

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
> Wenn Sie benutzerdefinierte Nachrichtentypen *must* wie diesen verwenden, `.proto`müssen Sie diese mit Kommentaren in dokumentieren. Andere Entwickler können dann die Konvertierung in und aus dem entsprechenden Typ in ihrer eigenen Sprache oder ihrem Framework implementieren.

>[!div class="step-by-step"]
>[VorherigeS](protobuf-messages.md)
>[Weiter](protobuf-nested-types.md)
