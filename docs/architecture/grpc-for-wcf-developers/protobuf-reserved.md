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
# <a name="protobuf-reserved-fields"></a>Reservierte Protobuf-Felder

Die Abwärtskompatibilität garantiert in Protokollpuffer (protobuf) basiert auf Feldnummern, die immer das gleiche Datenelement darstellen. Wenn ein Feld aus einer Nachricht in einer neuen Dienst Version entfernt wird, sollte diese Feldzahl nie wieder verwendet werden. Sie können dieses Verhalten erzwingen, indem Sie das- `reserved` Schlüsselwort verwenden.

Wenn das `displayName` -Feld und das- `marketId` Feld aus der `Stock` zuvor definierten Nachricht entfernt wurden, sollten die Feldnummern wie im folgenden Beispiel reserviert werden.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

Sie können auch das- `reserved` Schlüsselwort als Platzhalter für Felder verwenden, die möglicherweise in der Zukunft hinzugefügt werden. Sie können zusammenhängende Feld Zahlen als Bereich mit dem- `to` Schlüsselwort Ausdrücken.

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
>[Zurück](protobuf-repeated.md)
>[Weiter](protobuf-any-oneof.md)
