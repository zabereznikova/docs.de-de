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
# <a name="protobuf-reserved-fields"></a>Reservierte Protobuf-Felder

Die Abwärtskompatibilitätsgarantien in Protocol Buffer (Protobuf) basieren auf Feldnummern, die immer dasselbe Datenelement darstellen. Wenn ein Feld aus einer Nachricht in einer neuen Version des Dienstes entfernt wird, sollte diese Feldnummer niemals wiederverwendet werden. Sie können dies mit `reserved` dem Schlüsselwort verwenden.

Wenn `displayName` die `marketId` felder aus `Stock` der zuvor definierten Nachricht entfernt wurden, sollten ihre Feldnummern wie im folgenden Beispiel reserviert werden.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

Sie können das `reserved` Schlüsselwort auch als Platzhalter für Felder verwenden, die in Zukunft hinzugefügt werden könnten. Sie können zusammenhängende Feldnummern als Bereich `to` ausdrücken, indem Sie das Schlüsselwort verwenden.

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
>[VorherigeS](protobuf-repeated.md)
>[Weiter](protobuf-any-oneof.md)
