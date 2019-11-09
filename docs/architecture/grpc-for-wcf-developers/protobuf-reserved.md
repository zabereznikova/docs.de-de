---
title: 'Reservierte Felder für protobuf: GrpC für WCF-Entwickler'
description: Erfahren Sie mehr über reservierte Felder für die Versions übergreifende Kompatibilität.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 34697371299bdc5d9a58c0696c1ce7d19816ca87
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841390"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="f1cf6-103">Reservierte Protobuf-Felder</span><span class="sxs-lookup"><span data-stu-id="f1cf6-103">Protobuf reserved fields</span></span>

<span data-ttu-id="f1cf6-104">Die Abwärtskompatibilität von protobuf basiert darauf, dass Feldnummern immer das gleiche Datenelement darstellen.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-104">Protobuf's backward-compatibility guarantees rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="f1cf6-105">Wenn ein Feld aus einer Nachricht in einer neuen Dienst Version entfernt wird, sollte diese Feldzahl nie wieder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="f1cf6-106">Dies kann mit dem `reserved`-Schlüsselwort erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-106">This can be enforced using the `reserved` keyword.</span></span> <span data-ttu-id="f1cf6-107">Wenn die Felder `displayName` und `marketId` aus der zuvor definierten `Stock` Meldung entfernt wurden, sollten die entsprechenden Feldnummern wie im folgenden Beispiel reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="f1cf6-108">Das `reserved`-Schlüsselwort kann auch als Platzhalter für Felder verwendet werden, die möglicherweise in der Zukunft hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-108">The `reserved` keyword can also be used as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="f1cf6-109">Zusammenhängende Feldnummern können mit dem `to`-Schlüsselwort als Bereich ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="f1cf6-109">Contiguous field numbers can be expressed as a range using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="f1cf6-110">[Zurück](protobuf-repeated.md)
>[Weiter](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="f1cf6-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
