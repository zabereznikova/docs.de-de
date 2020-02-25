---
title: 'Protobuf any-und oneof-Felder für Variant-Typen: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie Sie mit jedem Typ und dem oneof-Schlüsselwort Variant-Objekttypen in Nachrichten darstellen.
ms.date: 09/09/2019
ms.openlocfilehash: 6fe7acbd1ec35289f7ad6f3acee8509ab934619d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543195"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="f123b-103">Protobuf any-und oneof-Felder für Variant-Typen</span><span class="sxs-lookup"><span data-stu-id="f123b-103">Protobuf Any and Oneof fields for variant types</span></span>

<span data-ttu-id="f123b-104">Die Behandlung dynamischer Eigenschafts Typen (d. h. Eigenschaften vom Typ `object`) in Windows Communication Foundation (WCF) ist kompliziert.</span><span class="sxs-lookup"><span data-stu-id="f123b-104">Handling dynamic property types (that is, properties of type `object`) in Windows Communication Foundation (WCF) is complicated.</span></span> <span data-ttu-id="f123b-105">Beispielsweise müssen Sie serialisierungsinitialisierer angeben und [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) -Attribute angeben.</span><span class="sxs-lookup"><span data-stu-id="f123b-105">For example, you must specify serializers and provide [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes.</span></span>

<span data-ttu-id="f123b-106">Der Protokollpuffer (protobuf) bietet zwei einfachere Optionen für den Umgang mit Werten, die von mehr als einem Typ sein können.</span><span class="sxs-lookup"><span data-stu-id="f123b-106">Protocol Buffer (Protobuf) provides two simpler options for dealing with values that might be of more than one type.</span></span> <span data-ttu-id="f123b-107">Der `Any`-Typ kann jeden bekannten protobuf-Nachrichtentyp darstellen.</span><span class="sxs-lookup"><span data-stu-id="f123b-107">The `Any` type can represent any known Protobuf message type.</span></span> <span data-ttu-id="f123b-108">Und Sie können das `oneof`-Schlüsselwort verwenden, um anzugeben, dass nur einer der Felder in einer beliebigen Nachricht festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f123b-108">And you can use the `oneof` keyword to specify that only one of a range of fields can be set in any message.</span></span>

## <a name="any"></a><span data-ttu-id="f123b-109">Any</span><span class="sxs-lookup"><span data-stu-id="f123b-109">Any</span></span>

<span data-ttu-id="f123b-110">`Any` ist einer der "Well-Known Types" von protobuf: eine Sammlung nützlicher, wiederverwendbarer Nachrichten Typen mit Implementierungen in allen unterstützten Sprachen.</span><span class="sxs-lookup"><span data-stu-id="f123b-110">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="f123b-111">Wenn Sie den `Any`-Typ verwenden möchten, müssen Sie die `google/protobuf/any.proto` Definition importieren.</span><span class="sxs-lookup"><span data-stu-id="f123b-111">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

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

<span data-ttu-id="f123b-112">Im C# Code stellt die `Any`-Klasse Methoden zum Festlegen des Felds, Extrahieren der Nachricht und Überprüfen des Typs bereit.</span><span class="sxs-lookup"><span data-stu-id="f123b-112">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

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

<span data-ttu-id="f123b-113">Der interne Reflektionscode von protobuf verwendet das `Descriptor` static-Feld für jeden generierten Typ, um `Any` Feldtypen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="f123b-113">Protobuf's internal reflection code uses the `Descriptor` static field on each generated type to resolve `Any` field types.</span></span> <span data-ttu-id="f123b-114">Es gibt auch eine `TryUnpack<T>`-Methode, die jedoch eine nicht initialisierte Instanz von `T` erstellt, auch wenn Sie fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="f123b-114">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails.</span></span> <span data-ttu-id="f123b-115">Es ist besser, die `Is`-Methode wie zuvor gezeigt zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f123b-115">It's better to use the `Is` method as shown earlier.</span></span>

## <a name="oneof"></a><span data-ttu-id="f123b-116">Jedes</span><span class="sxs-lookup"><span data-stu-id="f123b-116">Oneof</span></span>

<span data-ttu-id="f123b-117">Oneof-Felder sind ein Sprach Feature: der Compiler verarbeitet beim Generieren der Message-Klasse das `oneof`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="f123b-117">Oneof fields are a language feature: the compiler handles the `oneof` keyword when it generates the message class.</span></span> <span data-ttu-id="f123b-118">Die Verwendung von `oneof`, um die `ChangeNotification` Meldung anzugeben, könnte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="f123b-118">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

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

<span data-ttu-id="f123b-119">Felder innerhalb des `oneof` Satzes müssen in der allgemeinen Nachrichten Deklaration über eindeutige Feldnummern verfügen.</span><span class="sxs-lookup"><span data-stu-id="f123b-119">Fields within the `oneof` set must have unique field numbers in the overall message declaration.</span></span>

<span data-ttu-id="f123b-120">Wenn Sie `oneof`verwenden, enthält der C# generierte Code eine-Enumeration, die angibt, welche der Felder festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="f123b-120">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="f123b-121">Sie können die Enumeration testen, um zu ermitteln, welches Feld festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f123b-121">You can test the enum to find which field is set.</span></span> <span data-ttu-id="f123b-122">Felder, die nicht festgelegt sind, geben `null` oder den Standardwert zurück, anstatt eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="f123b-122">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

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

<span data-ttu-id="f123b-123">Wenn Sie ein Feld festlegen, das Teil eines `oneof` Satzes ist, werden alle anderen Felder in der Gruppe automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f123b-123">Setting any field that's part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="f123b-124">`repeated` können nicht mit `oneof`verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f123b-124">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="f123b-125">Stattdessen können Sie eine Nachricht mit dem wiederholten Feld oder dem `oneof` festlegen, um diese Einschränkung zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="f123b-125">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f123b-126">[Zurück](protobuf-reserved.md)
>[Weiter](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="f123b-126">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>
