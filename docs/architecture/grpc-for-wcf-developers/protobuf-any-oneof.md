---
title: 'Protobuf any-und oneof-Felder für Variant-Typen: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie Sie mit jedem Typ und dem oneof-Schlüsselwort Variant-Objekttypen in Nachrichten darstellen.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 10f55288eb4a6aa603228da5b4850317d6bde614
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841474"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="9eb86-103">Protobuf any-und oneof-Felder für Variant-Typen</span><span class="sxs-lookup"><span data-stu-id="9eb86-103">Protobuf Any and Oneof fields for variant types</span></span>

<span data-ttu-id="9eb86-104">Die Behandlung dynamischer Eigenschafts Typen (d. h. Eigenschaften vom Typ `object`) in WCF ist kompliziert.</span><span class="sxs-lookup"><span data-stu-id="9eb86-104">Handling dynamic property types (that is, properties of type `object`) in WCF is complicated.</span></span> <span data-ttu-id="9eb86-105">Serialisierungsinitialisierer müssen angegeben werden, es müssen [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) -Attribute angegeben werden usw.</span><span class="sxs-lookup"><span data-stu-id="9eb86-105">Serializers must be specified, [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes must be provided, and so on.</span></span>

<span data-ttu-id="9eb86-106">Protobuf bietet zwei einfachere Optionen für den Umgang mit Werten, die mehrere Typen aufweisen können.</span><span class="sxs-lookup"><span data-stu-id="9eb86-106">Protobuf provides two simpler options for dealing with values that may be of more than one type.</span></span> <span data-ttu-id="9eb86-107">Der `Any`-Typ kann jeden bekannten protobuf-Nachrichtentyp darstellen, während das `oneof`-Schlüsselwort Ihnen ermöglicht, anzugeben, dass nur ein Bereich von Feldern in einer beliebigen Nachricht festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9eb86-107">The `Any` type can represent any known Protobuf message type, while the `oneof` keyword allows you to specify that only one of a range of fields can be set in any given message.</span></span>

## <a name="any"></a><span data-ttu-id="9eb86-108">Beliebig</span><span class="sxs-lookup"><span data-stu-id="9eb86-108">Any</span></span>

<span data-ttu-id="9eb86-109">`Any` ist einer der "Well-Known Types" von protobuf: eine Sammlung nützlicher, wiederverwendbarer Nachrichten Typen mit Implementierungen in allen unterstützten Sprachen.</span><span class="sxs-lookup"><span data-stu-id="9eb86-109">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="9eb86-110">Wenn Sie den `Any`-Typ verwenden möchten, müssen Sie die `google/protobuf/any.proto` Definition importieren.</span><span class="sxs-lookup"><span data-stu-id="9eb86-110">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

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

<span data-ttu-id="9eb86-111">Im C# Code stellt die `Any`-Klasse Methoden zum Festlegen des Felds, Extrahieren der Nachricht und Überprüfen des Typs bereit.</span><span class="sxs-lookup"><span data-stu-id="9eb86-111">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

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

<span data-ttu-id="9eb86-112">Das `Descriptor` static-Feld für jeden generierten Typ wird vom internen Reflektionscode von protobuf verwendet, um `Any` Feldtypen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="9eb86-112">The `Descriptor` static field on each generated type is used by Protobuf's internal reflection code to resolve `Any` field types.</span></span> <span data-ttu-id="9eb86-113">Es gibt auch eine `TryUnpack<T>`-Methode, die jedoch eine nicht initialisierte Instanz von `T` auch dann erstellt, wenn Sie fehlschlägt. Daher ist es besser, die `Is`-Methode wie oben gezeigt zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9eb86-113">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails, so it's better to use the `Is` method as shown above.</span></span>

## <a name="oneof"></a><span data-ttu-id="9eb86-114">Jedes</span><span class="sxs-lookup"><span data-stu-id="9eb86-114">Oneof</span></span>

<span data-ttu-id="9eb86-115">Oneof-Felder sind eine Sprachfunktion: das `oneof`-Schlüsselwort wird vom Compiler beim Generieren der Message-Klasse behandelt.</span><span class="sxs-lookup"><span data-stu-id="9eb86-115">Oneof fields are a language feature: the `oneof` keyword is handled by the compiler when it generates the message class.</span></span> <span data-ttu-id="9eb86-116">Die Verwendung von `oneof`, um die `ChangeNotification` Meldung anzugeben, könnte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="9eb86-116">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

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

<span data-ttu-id="9eb86-117">Felder innerhalb des `oneof` Satzes müssen in der allgemeinen Nachrichten Deklaration über eindeutige Feldnummern verfügen.</span><span class="sxs-lookup"><span data-stu-id="9eb86-117">Fields within the `oneof` set must have unique field numbers within the overall message declaration.</span></span>

<span data-ttu-id="9eb86-118">Wenn Sie `oneof`verwenden, enthält der C# generierte Code eine-Enumeration, die angibt, welche der Felder festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="9eb86-118">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="9eb86-119">Sie können die Enumeration testen, um zu ermitteln, welches Feld festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9eb86-119">You can test the enum to find which field is set.</span></span> <span data-ttu-id="9eb86-120">Felder, die nicht festgelegt sind, geben `null` oder den Standardwert zurück, anstatt eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="9eb86-120">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

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

<span data-ttu-id="9eb86-121">Wenn Sie ein Feld festlegen, das Teil eines `oneof` Satzes ist, werden alle anderen Felder in der Gruppe automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9eb86-121">Setting any field that is part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="9eb86-122">`repeated` können nicht mit `oneof`verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9eb86-122">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="9eb86-123">Stattdessen können Sie eine Nachricht mit dem wiederholten Feld oder dem `oneof` festlegen, um diese Einschränkung zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="9eb86-123">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9eb86-124">[Zurück](protobuf-reserved.md)
>[Weiter](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="9eb86-124">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>
