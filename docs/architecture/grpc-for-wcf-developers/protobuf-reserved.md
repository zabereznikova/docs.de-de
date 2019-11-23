---
title: 'Reservierte Felder für protobuf: GrpC für WCF-Entwickler'
description: Erfahren Sie mehr über reservierte Felder für die Versions übergreifende Kompatibilität.
ms.date: 09/09/2019
ms.openlocfilehash: e589cd38a712ce014fa2c4d847fbde359d538dd0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967313"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="de5df-103">Reservierte Protobuf-Felder</span><span class="sxs-lookup"><span data-stu-id="de5df-103">Protobuf reserved fields</span></span>

<span data-ttu-id="de5df-104">Die Abwärtskompatibilität von protobuf basiert darauf, dass Feldnummern immer das gleiche Datenelement darstellen.</span><span class="sxs-lookup"><span data-stu-id="de5df-104">Protobuf's backward-compatibility guarantees rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="de5df-105">Wenn ein Feld aus einer Nachricht in einer neuen Dienst Version entfernt wird, sollte diese Feldzahl nie wieder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="de5df-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="de5df-106">Dies kann mit dem `reserved`-Schlüsselwort erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="de5df-106">This can be enforced using the `reserved` keyword.</span></span> <span data-ttu-id="de5df-107">Wenn die Felder `displayName` und `marketId` aus der zuvor definierten `Stock` Meldung entfernt wurden, sollten die entsprechenden Feldnummern wie im folgenden Beispiel reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="de5df-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="de5df-108">Das `reserved`-Schlüsselwort kann auch als Platzhalter für Felder verwendet werden, die möglicherweise in der Zukunft hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="de5df-108">The `reserved` keyword can also be used as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="de5df-109">Zusammenhängende Feldnummern können mit dem `to`-Schlüsselwort als Bereich ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="de5df-109">Contiguous field numbers can be expressed as a range using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="de5df-110">[Zurück](protobuf-repeated.md)
>[Weiter](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="de5df-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
