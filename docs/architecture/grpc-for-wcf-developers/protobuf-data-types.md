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
# <a name="protobuf-scalar-data-types"></a>Skalare Datentypen für Protobuf

Der Protokollpuffer (protobuf) unterstützt einen Bereich von systemeigenen skalaren Werttypen. In der folgenden Tabelle werden alle dieser Typen mit dem entsprechenden C#-Typ aufgeführt:

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

1. Die Standard Codierung für `int32` und `int64` ist ineffizient, wenn Sie mit signierten Werten arbeiten. Wenn das Feld wahrscheinlich negative Zahlen enthält, verwenden Sie `sint32` stattdessen oder `sint64` . Diese Typen werden dem c# `int` - `long` bzw. dem-Typ zugeordnet.
2. `fixed`In den Feldern wird immer dieselbe Anzahl von Bytes verwendet, unabhängig davon, was der Wert ist. Dieses Verhalten macht die Serialisierung und Deserialisierung bei größeren Werten schneller.
3. Protobuf-Zeichen folgen sind UTF-8-codiert (oder 7-Bit-ASCII). Die codierte Länge darf nicht größer als 2<sup>32</sup>sein.
4. Die protobuf-Laufzeit stellt einen `ByteString` Typ bereit, der problemlos und aus c#-Arrays zugeordnet wird `byte[]` .

## <a name="other-net-primitive-types"></a>Andere .net-primitive Typen

### <a name="dates-and-times"></a>Datums- und Zeitangaben

Die nativen skalaren Typen stellen keine Datums-und Uhrzeitwerte bereit, die den c#-,-und-Werten entsprechen <xref:System.DateTimeOffset> <xref:System.DateTime> <xref:System.TimeSpan> . Sie können diese Typen mithilfe einiger der "Well Known Types"-Erweiterungen von Google angeben. Diese Erweiterungen bieten Codegenerierung und Runtime-Unterstützung für komplexe Feldtypen für die unterstützten Plattformen.

In der folgenden Tabelle werden die Datums- und Zeittypen aufgeführt:

| C#-Typ | Bekannter Protobuf-Typ |
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

Die in der C#-Klasse generierten Eigenschaften sind nicht die Datums- und Zeittypen von .NET. Die Eigenschaften nutzen die Klassen `Timestamp` und `Duration` im Namespace `Google.Protobuf.WellKnownTypes`. Diese Klassen stellen Methoden zum Konvertieren in und aus `DateTimeOffset`, `DateTime` und `TimeSpan` bereit.

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
> Der `Timestamp`-Typ kann mit UTC-Zeiten verwendet werden. `DateTimeOffset`-Werte weisen immer ein Offset von 0 (null) auf, und die `DateTime.Kind`-Eigenschaft ist immer `DateTimeKind.Utc`.

### <a name="systemguid"></a>System.Guid

Protobuf unterstützt den <xref:System.Guid> Typ, der als `UUID` auf anderen Plattformen bezeichnet wird, nicht direkt. Dafür gibt es keinen bekannten Typ.

Der beste Ansatz besteht darin, `Guid` Werte als Feld zu behandeln `string` , indem Sie das standardmäßige `8-4-4-4-12` Hexadezimal Format (z `45a9fda3-bd01-47a9-8460-c1cd7484b0b3` . b.) verwenden. Dieses Format kann von allen Sprachen und Plattformen analysiert werden.

Verwenden Sie kein `bytes` Feld für- `Guid` Werte. Probleme mit *Byte Reihenfolge* ([Wikipedia-Definition](https://en.wikipedia.org/wiki/Endianness)) können zu einem erratischen Verhalten führen, wenn protobuf mit anderen Plattformen wie Java interagiert.

### <a name="nullable-types"></a>Nullable-Typen

Bei der Protobuf-Codegenerierung für C# werden die nativen Typen verwendet, z. B. `int` für `int32`. Daher sind die Werte immer enthalten und dürfen nicht NULL sein.

Für Werte, die explizite NULL-Werte erfordern, wie z. `int?` b. die Verwendung von in Ihrem c#-Code, enthalten die "bekannten Typen" von protobuf Wrapper, die in c#-Typen mit Nullwert kompiliert werden. Importieren Sie Sie wie folgt `wrappers.proto` in die `.proto` Datei:

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf verwendet das einfache `T?` (z `int?` . b.) für die generierte Message-Eigenschaft.

In der folgenden Tabelle finden Sie eine vollständige Liste der Wrappertypen mit dem entsprechenden C#-Typ:

| C#-Typ   | Well Known Type-Wrapper       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

Die bekannten Typen `Timestamp` und `Duration` werden in .net als Klassen dargestellt. In c# 8 und höher können Sie Verweis Typen verwenden, die NULL-Werte zulassen. Es ist jedoch wichtig, bei Eigenschaften dieser Typen auf NULL zu prüfen, wenn Sie eine Umstellung auf oder durchsetzen `DateTimeOffset` `TimeSpan` .

## <a name="decimals"></a>Dezimalstellen

Protobuf unterstützt den .NET-Typ `decimal` nicht nativ, nur `double` und `float`. Im protobuf-Projekt gibt es eine fortlaufende Erörterung der Möglichkeit `Decimal` , den bekannten Typen einen Standardtyp hinzuzufügen, mit Platt Form Unterstützung für Sprachen und Frameworks, die diese unterstützen. Bisher wurde keine Implementierung vorgenommen.

Es ist möglich, eine Nachrichten Definition zu erstellen, die den `decimal` Typ darstellt, der für die sichere Serialisierung zwischen .NET-Clients und-Servern geeignet wäre. Entwickler anderer Plattformen müssten jedoch das verwendete Format verstehen und ihr eigenes Format implementieren, um dieses zu verarbeiten.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Erstellen eines benutzerdefinierten Dezimaltyps für Protobuf

Eine einfache Implementierung ähnelt möglicherweise dem nicht dem Standard entsprechenden `Money` Typ, der von einigen Google-APIs verwendet wird, ohne das- `currency` Feld.

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

Das `nanos`-Feld stellt Werte von `0.999_999_999` bis `-0.999_999_999` dar. Beispielsweise würde der `decimal`-Wert `1.5m` als `{ units = 1, nanos = 500_000_000 }` dargestellt werden. Aus diesem Grund wird in diesem Beispiel für das `nanos`-Feld der `sfixed32`-Typ verwendet, der bei größeren Werten effizienter als `int32` codiert wird. Wenn das `units`-Feld negativ ist, sollte auch das `nanos`-Feld negativ sein.

> [!NOTE]
> Es gibt mehrere andere Algorithmen zum Codieren von `decimal`-Werten als Bytezeichenfolgen, jedoch ist diese Nachricht leichter zu verstehen, als alle dieser Algorithmen. Die Werte sind von der enumalität auf verschiedenen Plattformen nicht betroffen.

Konvertierungen zwischen diesem Typ und dem BCL-Typ `decimal` können wie folgt in C# implementiert werden:

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
> Wenn Sie benutzerdefinierte Nachrichten Typen wie diese verwenden, *müssen* Sie diese mit Kommentaren in dokumentieren `.proto` . Andere Entwickler können dann eine Konvertierung in und aus dem entsprechenden Typ in ihrer eigenen Sprache oder in Ihrem eigenen Framework implementieren.

>[!div class="step-by-step"]
>[Zurück](protobuf-messages.md)
>[Weiter](protobuf-nested-types.md)
