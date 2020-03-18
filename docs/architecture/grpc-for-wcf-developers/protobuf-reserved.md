---
title: Protobuf reservierte Felder - gRPC für WCF-Entwickler
description: Erfahren Sie mehr über reservierte Felder für die versionsübergreifende Kompatibilität.
ms.date: 09/09/2019
ms.openlocfilehash: bde658c671e970b7ec841d71d5b4284eb91195f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147944"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="33d95-103">Reservierte Protobuf-Felder</span><span class="sxs-lookup"><span data-stu-id="33d95-103">Protobuf reserved fields</span></span>

<span data-ttu-id="33d95-104">Die Abwärtskompatibilitätsgarantien in Protocol Buffer (Protobuf) basieren auf Feldnummern, die immer dasselbe Datenelement darstellen.</span><span class="sxs-lookup"><span data-stu-id="33d95-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="33d95-105">Wenn ein Feld aus einer Nachricht in einer neuen Version des Dienstes entfernt wird, sollte diese Feldnummer niemals wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33d95-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="33d95-106">Sie können dies mit `reserved` dem Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="33d95-106">You can enfore this by using the `reserved` keyword.</span></span>

<span data-ttu-id="33d95-107">Wenn `displayName` die `marketId` felder aus `Stock` der zuvor definierten Nachricht entfernt wurden, sollten ihre Feldnummern wie im folgenden Beispiel reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="33d95-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="33d95-108">Sie können das `reserved` Schlüsselwort auch als Platzhalter für Felder verwenden, die in Zukunft hinzugefügt werden könnten.</span><span class="sxs-lookup"><span data-stu-id="33d95-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="33d95-109">Sie können zusammenhängende Feldnummern als Bereich `to` ausdrücken, indem Sie das Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="33d95-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="33d95-110">[VorherigeS](protobuf-repeated.md)
>[Weiter](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="33d95-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
