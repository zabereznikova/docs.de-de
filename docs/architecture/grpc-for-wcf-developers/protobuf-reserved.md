---
title: Protobuf reservierte Felder - gRPC für WCF-Entwickler
description: Erfahren Sie mehr über reservierte Felder für die versionsübergreifende Kompatibilität.
ms.date: 09/09/2019
ms.openlocfilehash: f89513c4659a02cbc94e1c659baecb9e750acbdc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111035"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="a404b-103">Reservierte Protobuf-Felder</span><span class="sxs-lookup"><span data-stu-id="a404b-103">Protobuf reserved fields</span></span>

<span data-ttu-id="a404b-104">Die Abwärtskompatibilitätsgarantien in Protocol Buffer (Protobuf) basieren auf Feldnummern, die immer dasselbe Datenelement darstellen.</span><span class="sxs-lookup"><span data-stu-id="a404b-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="a404b-105">Wenn ein Feld aus einer Nachricht in einer neuen Version des Dienstes entfernt wird, sollte diese Feldnummer niemals wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a404b-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="a404b-106">Sie können dies `reserved` erzwingen, indem Sie das Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="a404b-106">You can enforce this by using the `reserved` keyword.</span></span>

<span data-ttu-id="a404b-107">Wenn `displayName` die `marketId` felder aus `Stock` der zuvor definierten Nachricht entfernt wurden, sollten ihre Feldnummern wie im folgenden Beispiel reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="a404b-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="a404b-108">Sie können das `reserved` Schlüsselwort auch als Platzhalter für Felder verwenden, die in Zukunft hinzugefügt werden könnten.</span><span class="sxs-lookup"><span data-stu-id="a404b-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="a404b-109">Sie können zusammenhängende Feldnummern als Bereich `to` ausdrücken, indem Sie das Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="a404b-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="a404b-110">[VorherigeS](protobuf-repeated.md)
>[Weiter](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="a404b-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
