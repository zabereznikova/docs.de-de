---
title: 'Reservierte Felder für protobuf: GrpC für WCF-Entwickler'
description: Erfahren Sie mehr über reservierte Felder für die Versions übergreifende Kompatibilität.
ms.date: 12/15/2020
ms.openlocfilehash: d82043d619c5b3b81091ae4ea381e4778c1cf6ba
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938519"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="37b9f-103">Reservierte Protobuf-Felder</span><span class="sxs-lookup"><span data-stu-id="37b9f-103">Protobuf reserved fields</span></span>

<span data-ttu-id="37b9f-104">Die Abwärtskompatibilität garantiert in Protokollpuffer (protobuf) basiert auf Feldnummern, die immer das gleiche Datenelement darstellen.</span><span class="sxs-lookup"><span data-stu-id="37b9f-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="37b9f-105">Wenn ein Feld aus einer Nachricht in einer neuen Dienst Version entfernt wird, sollte diese Feldzahl nie wieder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37b9f-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="37b9f-106">Sie können dieses Verhalten erzwingen, indem Sie das- `reserved` Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="37b9f-106">You can enforce this behavior by using the `reserved` keyword.</span></span>

<span data-ttu-id="37b9f-107">Wenn das `displayName` -Feld und das- `marketId` Feld aus der `Stock` zuvor definierten Nachricht entfernt wurden, sollten die Feldnummern wie im folgenden Beispiel reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="37b9f-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="37b9f-108">Sie können auch das- `reserved` Schlüsselwort als Platzhalter für Felder verwenden, die möglicherweise in der Zukunft hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="37b9f-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="37b9f-109">Sie können zusammenhängende Feld Zahlen als Bereich mit dem- `to` Schlüsselwort Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="37b9f-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="37b9f-110">[Zurück](protobuf-repeated.md)
>[Weiter](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="37b9f-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
