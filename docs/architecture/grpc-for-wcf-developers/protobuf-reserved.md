---
title: 'Reservierte Felder für protobuf: GrpC für WCF-Entwickler'
description: Erfahren Sie mehr über reservierte Felder für die Versions übergreifende Kompatibilität.
ms.date: 09/09/2019
ms.openlocfilehash: 50082a1aab2e7707a1839b9d56455124a9e4a6a1
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542975"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="b1c76-103">Reservierte Protobuf-Felder</span><span class="sxs-lookup"><span data-stu-id="b1c76-103">Protobuf reserved fields</span></span>

<span data-ttu-id="b1c76-104">Die Abwärtskompatibilität garantiert in Protokollpuffer (protobuf) basiert auf Feldnummern, die immer das gleiche Datenelement darstellen.</span><span class="sxs-lookup"><span data-stu-id="b1c76-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="b1c76-105">Wenn ein Feld aus einer Nachricht in einer neuen Dienst Version entfernt wird, sollte diese Feldzahl nie wieder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1c76-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="b1c76-106">Hierfür können Sie das `reserved`-Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1c76-106">You can enfore this by using the `reserved` keyword.</span></span> 

<span data-ttu-id="b1c76-107">Wenn die Felder `displayName` und `marketId` aus der zuvor definierten `Stock` Meldung entfernt wurden, sollten die entsprechenden Feldnummern wie im folgenden Beispiel reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="b1c76-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="b1c76-108">Sie können auch das `reserved`-Schlüsselwort als Platzhalter für Felder verwenden, die möglicherweise in der Zukunft hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b1c76-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="b1c76-109">Sie können zusammenhängende Feld Zahlen als Bereich mit dem `to`-Schlüsselwort Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="b1c76-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="b1c76-110">[Zurück](protobuf-repeated.md)
>[Weiter](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="b1c76-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
