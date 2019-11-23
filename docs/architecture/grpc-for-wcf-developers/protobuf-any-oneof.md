---
title: 'Protobuf any-und oneof-Felder für Variant-Typen: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie Sie mit jedem Typ und dem oneof-Schlüsselwort Variant-Objekttypen in Nachrichten darstellen.
ms.date: 09/09/2019
ms.openlocfilehash: af3ba22c238aa80a8c6119f62d5d8914770cad68
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971618"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a>Protobuf any-und oneof-Felder für Variant-Typen

Die Behandlung dynamischer Eigenschafts Typen (d. h. Eigenschaften vom Typ `object`) in WCF ist kompliziert. Serialisierungsinitialisierer müssen angegeben werden, es müssen [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) -Attribute angegeben werden usw.

Protobuf bietet zwei einfachere Optionen für den Umgang mit Werten, die mehrere Typen aufweisen können. Der `Any`-Typ kann jeden bekannten protobuf-Nachrichtentyp darstellen, während das `oneof`-Schlüsselwort Ihnen ermöglicht, anzugeben, dass nur ein Bereich von Feldern in einer beliebigen Nachricht festgelegt werden kann.

## <a name="any"></a>Beliebig

`Any` ist einer der "Well-Known Types" von protobuf: eine Sammlung nützlicher, wiederverwendbarer Nachrichten Typen mit Implementierungen in allen unterstützten Sprachen. Wenn Sie den `Any`-Typ verwenden möchten, müssen Sie die `google/protobuf/any.proto` Definition importieren.

```protobuf
syntax "proto3"

import "google/protobuf/any.proto"

message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
    int32 id = 1;
    google.protobuf.Any instrument = 2;
}
```

Im C# Code stellt die `Any`-Klasse Methoden zum Festlegen des Felds, Extrahieren der Nachricht und Überprüfen des Typs bereit.

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    if (change.Instrument.Is(Stock.Descriptor))
    {
        FormatStock(change.Instrument.Unpack<Stock>());
    }
    else if (change.Instrument.Is(Currency.Descriptor))
    {
        FormatCurrency(change.Instrument.Unpack<Currency>());
    }
    else
    {
        throw new ArgumentException("Unknown instrument type");
    }
}
```

Das `Descriptor` static-Feld für jeden generierten Typ wird vom internen Reflektionscode von protobuf verwendet, um `Any` Feldtypen aufzulösen. Es gibt auch eine `TryUnpack<T>`-Methode, die jedoch eine nicht initialisierte Instanz von `T` auch dann erstellt, wenn Sie fehlschlägt. Daher ist es besser, die `Is`-Methode wie oben gezeigt zu verwenden.

## <a name="oneof"></a>Jedes

Oneof-Felder sind eine Sprachfunktion: das `oneof`-Schlüsselwort wird vom Compiler beim Generieren der Message-Klasse behandelt. Die Verwendung von `oneof`, um die `ChangeNotification` Meldung anzugeben, könnte wie folgt aussehen:

```protobuf
message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
  int32 id = 1;
  oneof instrument {
    Stock stock = 2;
    Currency currency = 3;
  }
}
```

Felder innerhalb des `oneof` Satzes müssen in der allgemeinen Nachrichten Deklaration über eindeutige Feldnummern verfügen.

Wenn Sie `oneof`verwenden, enthält der C# generierte Code eine-Enumeration, die angibt, welche der Felder festgelegt wurde. Sie können die Enumeration testen, um zu ermitteln, welches Feld festgelegt ist. Felder, die nicht festgelegt sind, geben `null` oder den Standardwert zurück, anstatt eine Ausnahme auszulösen.

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    switch (change.InstrumentCase)
    {
        case ChangeNotification.InstrumentOneofCase.None:
            return;
        case ChangeNotification.InstrumentOneofCase.Stock:
            FormatStock(change.Stock);
            break;
        case ChangeNotification.InstrumentOneofCase.Currency:
            FormatCurrency(change.Currency);
            break;
        default:
            throw new ArgumentException("Unknown instrument type");
    }
}
```

Wenn Sie ein Feld festlegen, das Teil eines `oneof` Satzes ist, werden alle anderen Felder in der Gruppe automatisch gelöscht. `repeated` können nicht mit `oneof`verwendet werden. Stattdessen können Sie eine Nachricht mit dem wiederholten Feld oder dem `oneof` festlegen, um diese Einschränkung zu umgehen.

>[!div class="step-by-step"]
>[Zurück](protobuf-reserved.md)
>[Weiter](protobuf-enums.md)
